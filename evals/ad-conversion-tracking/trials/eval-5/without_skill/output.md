# Duneport Legal Software — Tracking Fix Order (9 days to launch)

**Ground rule:** activate the internal traffic filter before touching anything else, so your own QA over the next 9 days doesn't recontaminate the data you're trying to clean.

## Fix order

**0. Activate the internal traffic filter — Day 1, first thing** 🔴
- Flip GA4's filter from "Testing" to "Active."
- "Testing" only tags internal traffic, it doesn't exclude it. Every test submission you make while fixing items 1–5 will otherwise land in real reporting.
- No developer needed (GA4 admin UI). 5 minutes.

**1. Cap conversion counting to "One" per click — Day 1** 🔴
- Google Ads conversion action: change Count from "Every" to "One."
- This doesn't fix the root cause below, but it's a one-line, zero-risk circuit breaker that caps the damage from bug (a) while you fix it properly. Do it immediately, don't wait for a maintenance window.
- No developer needed. 2 minutes.

**2. Fix the conversion tag trigger — Day 1–2** 🔴 — root cause of (a)+(b)'s combined damage
- Change the GTM trigger from "All Pages" to the actual form-submission event (or thank-you-page-with-referrer check).
- This is your single most damaging bug: every page view is currently logged as a lead. Left running even a few more days, it poisons Smart Bidding's signal and burns spend chasing pageviews, not leads.
- No developer needed (GTM). Verify with GTM Preview + a real test submission (now safely excluded by step 0).

**3. Escalate the gclid-stripping redirect — start Day 1, resolve by Day 5–6** 🟠 — likely needs the unavailable developer
- Without gclid reaching the landing page, `gtag.js` never sets `_gcl_aw`, so **no conversion — real or fake — can ever be attributed to a campaign/keyword/ad**, no matter how clean the rest of the pipeline is.
- This is the one item most likely to require actual code changes (redirect service/server logic), which is your real timeline risk given the developer is out. Start sourcing help today (contractor, agency partner, or the redirect tool's vendor support) — don't let it sit until day 7.
- Until fixed, Ads reporting will show near-zero conversions regardless of how well items 0–2 and 4 are done — so you can't fully validate the rest of the pipeline until this lands.

**4. Add a shared event ID for browser/server dedup — Day 3–5** 🟠
- Pass the same `event_id` (Meta CAPI) / same transaction/lead ID (GA4 Measurement Protocol) on both the browser pixel and the server event.
- Without it, every real lead is counted twice — a flat 2x inflation on top of whatever (a)/(b) were adding.
- Coordinate with whoever handles item 3 — same tracking layer, worth batching if it's the same vendor/contractor.

**5. Resolve the consent-banner blocking — parallel track, Day 2 start, close by Day 7** 🟢
- Traffic is US-only: GDPR-style opt-in blocking isn't the applicable standard. Most US state laws (CCPA/CPRA and similar) are notice-and-opt-out, not opt-in-required.
- Get legal/privacy sign-off on switching to a default-allow + Google Consent Mode / opt-out model instead of blocking the tag outright on decline — this recovers volume without adding real compliance risk, but it's a legal call, not an engineering one, so don't let engineering make it unilaterally.
- Lowest urgency of the six: it undercounts, it doesn't corrupt bidding with false signal. Fine to land last.

## Why this order, not severity order alone

- (a) is the worst bug, but (1) and (0) are near-free and should be done in the same sitting to stop the bleeding immediately, before the "proper" trigger fix is even deployed.
- (f) is structurally upstream of everything: fixing (a)/(b)/(d) is unverifiable in Google Ads reporting until gclid actually reaches the page. Start it earliest despite listing it 3rd, because it has the longest lead time (dev-dependent) — sequence by *when you start*, not just *when it lands*.
- (e) is decision-gated by legal, not effort-gated — run it in parallel so it doesn't block the engineering-side fixes.

## Day 8–9: freeze and verify

- Submit real test leads (now excluded from reporting by step 0).
- Confirm: gclid persists into `_gcl_aw` → exactly one conversion in GA4 and one in Ads per real submission → browser and server events collapse into a single deduplicated event → internal filter still active → consent behavior matches whatever legal confirmed.
- Code freeze 24–48h before launch — no further tracking changes once QA passes.