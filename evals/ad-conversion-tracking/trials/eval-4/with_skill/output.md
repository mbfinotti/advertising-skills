# Corvasse — Conversion Setup Review (pre budget-double gate)

**Scope note:** I don't have access to your Google Ads account, GTM container, or Salesforce instance in this session, so I can't trace a live test conversion or check dedup/payload data directly. What follows is a full configuration-level review based on what you described, plus the two B2B-specific checks (attribution window vs. sales cycle, and volume threshold for the optimization target). The items I can't verify without hands-on access are called out explicitly — they're the ones you or whoever owns the Ads/Salesforce integration should trace before trusting this for real budget.

## Findings, in fix order

**🔴 Critical — 5 conversion actions marked primary dilutes "optimize to Closed Won."**
Smart Bidding optimizes across *every* primary action as one blended pool, not toward whichever one you care about most. Right now "optimize to Closed Won" isn't actually configured — the algorithm is chasing Form Fill, Demo Booked, Newsletter Signup, Pricing Page View, and Closed Won together. Pricing Page View and Newsletter Signup in particular are engagement signals, not sales outcomes, and shouldn't be feeding bids at all. Fix: demote both to secondary. One toggle each in the Ads UI, reversible instantly.

**🔴 Critical — 7 Closed Won/month is far below what Smart Bidding needs to learn from.**
Even after fixing the primary-action list, Closed Won alone won't clear it. Google documents ~30 conversions in 30 days as the minimum for Target CPA to function; Closed Won is running at roughly a quarter of that. Optimizing directly to it leaves the algorithm making bid decisions on a handful of data points a month — it won't exit learning, or it'll exit on noise.

Recommendation: keep Closed Won as your north star for reporting, but make the sole bid-driving primary action the deepest stage that actually clears volume — most likely **Demo Booked** (confirm its monthly count). Assign it a calculated value: (Demo Booked → Closed Won rate) × $15k ACV. If roughly 1 in 12 booked demos closes, that's ~$1,250 of value per Demo Booked — bid on that with value-based Smart Bidding today, and revisit moving Closed Won itself to primary once its volume grows.

**🟠 High — click-through window (30 days) is shorter than your sales cycle (45 days).**
By definition, something close to half your deals will close after the 30-day window has expired from the original click — Google Ads simply won't attribute them, undercounting Closed Won and understating what paid search is actually driving. And 45 days is the *sales* cycle from lead, not from ad click, so real click-to-close time is likely longer still. Fix: extend the click-through conversion window to 90 days (Google Ads' max). Same-day settings change.

**🟠 High — "Every" counting on lead-gen actions.**
Form Fill, Demo Booked, and Newsletter Signup are one-time-per-prospect actions. "Every" lets a resubmitted form or a rescheduled demo count as a second conversion, inflating exactly the signals you're about to rely on for bidding. Switch these to "One" per click/interaction. Also worth a check with whoever owns the Salesforce export: if an Opportunity re-syncs, does Closed Won risk importing twice on "Every"? A single $15k deal double-counting would meaningfully skew a 7/month sample.

**⚠️ Needs verification — does the click ID actually survive the whole journey?**
This is the load-bearing question behind your entire ask. For Closed Won to mean anything to Smart Bidding, the GCLID has to be captured on the Form Fill, persist onto the Salesforce Lead, survive conversion to an Opportunity, and still be present on the record Salesforce exports back as Closed Won. If that chain breaks anywhere, Closed Won imports can't be matched to the click that produced them, and no amount of primary/counting fixes will make them a usable optimization signal. I can't check this without access — have whoever owns the integration trace one real deal end-to-end before treating this as trustworthy for the quarters ahead, not just this campaign.

**⚠️ Needs verification — is Closed Won importing real deal value or a placeholder?**
For value-based bidding (now on Demo Booked, later potentially on Closed Won itself) to work, the imported value needs to be the actual Salesforce Amount, not a flat number. Check the field mapping in the connector.

## Not evaluated this pass

Consent banner / regulated-traffic handling — no information given on audience regions; worth a separate check if any EU traffic is in the mix, since that's where signal silently disappears on the reject path.

## Decision: **NO-GO on doubling budget as configured**

Doubling spend into a bidding target that's both diluted by noise actions and too thin on volume to learn from doesn't fix the signal quality — it just buys more of the wrong data, faster. That's the exact failure mode this kind of audit exists to catch.

**Fix order (ship as one batch, let Smart Bidding relearn once — serial fixes reset learning each time):**
1. Demote Pricing Page View and Newsletter Signup to secondary
2. Set Form Fill and Demo Booked counting to "One"
3. Extend click-through window to 90 days
4. Confirm Closed Won's imported value is real deal amount, not placeholder
5. Trace the GCLID chain end-to-end (Form Fill → Salesforce Lead → Opportunity → Closed Won export)
6. Set Demo Booked (pending its own volume check) as the sole primary, bid-driving action with a calculated value; keep Closed Won as secondary/import for reporting and future recalibration
7. Let Smart Bidding relearn (~24-48h), soak a few days of real performance
8. Only then — and only if Demo Booked volume/CPA look sound — double the budget

**Deferred:** consent-path check (no region data given; revisit if EU traffic is material).
**Re-verify:** once items 1-6 ship, confirm Demo Booked is clearing enough volume and that a traced deal shows GCLID intact through Closed Won, before scaling spend.