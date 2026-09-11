## Why the three numbers won't ever match — and what to actually fix

**First: your EMQ score is not evidence here.** Event Match Quality (9.1/10) is a Meta Conversions API metric — it scores how well Meta can match your server-side events to a Facebook/Instagram user profile. It says nothing about Google Ads, GA4, or your backend. Being confident about "dedup" because of EMQ is comparing a Meta health metric to a completely different platform's discrepancy. Drop that as a reference point entirely.

## The two gaps are different problems

**Backend (502) → GA4 (486): ~3.2% missing. This one is healthy, don't chase it.**
Causes, roughly in order of likely impact:
- Consent Mode denials (GDPR/CCPA "reject") — no cookies, no GA4 hit, purchase still completes and hits backend. Unfixable by design, and expected.
- Purchases via iOS in-app browsers (Instagram/FB in-app WebView) where gtag often fails to fire.
- Ad blockers / ITP stripping the GA4 tag.
- Backend order set includes phone/manual/admin orders that never had a web session — these shouldn't be in the comparison at all.
- Timezone mismatch between backend DB and the GA4 property (check orders near midnight shifting days).

A 3–5% GA4-to-backend gap is normal for ecommerce. Treat this as noise, not a bug to eliminate.

**GA4 (486) → Google Ads (412): ~15% missing. This is the real problem, and it's fixable.**
This gap is almost never "tracking is broken" — it's usually one of these:

1. **Attribution model mismatch.** If Google Ads imports conversions from GA4, it only imports the subset of GA4 purchases GA4's model actually credited to a Google Ads click. Purchases GA4 attributed to email, direct, or organic never show up in Ads — correctly. Check GA4's Advertising → Attribution report: how many of the 486 purchases were actually credited to Paid Search/PMax?
2. **Consent Mode conversion modeling lag.** For consent-denied users, Google Ads statistically models conversions and backfills them over the following days. Pulling numbers mid- or right-after the soft-launch window catches Ads before modeling completes. Re-pull the same window 3–7 days later before drawing conclusions.
3. **Cross-domain / gclid loss.** If checkout runs on a separate domain (Shopify checkout, Stripe/PayPal-hosted page) and cross-domain linking isn't configured, the click ID dies at the domain boundary. GA4 can still log the purchase (session-based); Ads can't attribute it without the gclid — conversion is silently dropped. This is the single most common cause of exactly this pattern and worth checking first.
4. **Conversion action scope.** Confirm the "Purchase" conversion action in Ads has all relevant campaign types included (Search, PMax, Shopping, Display, YouTube) and isn't excluding a network that drove soft-launch traffic.
5. **Enhanced Conversions for Web** not implemented (or broken) on the order confirmation page — lowers match rate, especially post-iOS14.5/consent-mode traffic.
6. **New/recently-relinked conversion action** — if the Ads conversion tag or GA4 link was set up right before soft-launch, expect under-counting for the first several days from processing lag alone.

## Action plan, in order

1. **Reconcile definitions first.** Confirm the 502 is completed/paid, non-test, web-attributable orders — strip out phone/manual orders before comparing to digital sources.
2. **Check GA4's Attribution report** to see how many of the 486 are actually credited to Google Ads. If it's close to 412 already, the gap is model semantics, not tracking loss — nothing to fix.
3. **Pull a live session through DebugView**: click a real Google Ad, complete a real purchase, and verify the gclid survives every redirect/domain hop to the confirmation page. This single test usually reveals cross-domain breakage immediately.
4. **Check Ads' conversion diagnostics** (Tools → Conversions → diagnostics) for Enhanced Conversions match rate and for "modeled vs observed" split under Consent Mode.
5. **Re-pull the Ads number in 5–7 days** on the same soft-launch window to see how much the gap closes from modeling backfill alone.
6. **Set up Offline Conversion Import** from your backend (matched on gclid + order ID) as a third, independent Ads-side data source. It'll show you the "true" number Ads *can* attribute once cross-domain and consent issues are fixed, and becomes your ongoing reconciliation tool post-launch.

## What to tell your CMO

Perfect 1:1 parity across backend, GA4, and Google Ads is not a realistic bar — it doesn't happen even in mature, well-instrumented ecommerce stacks, because the three systems measure fundamentally different things (server truth vs. client-side session vs. ad-attributed and partly modeled conversions). A 3% backend-to-GA4 gap is healthy. A 15% GA4-to-Ads gap is worth explaining, but the right test isn't "do the numbers match" — it's "can we explain the gap by attribution model + consent modeling, or is it real tracking loss (cross-domain, missing gclid)."

Recommend replacing the "all three match" gate with two concrete checks before scaling:
- GA4 vs. backend stays within ~5%.
- The GA4-to-Ads gap is fully accounted for by (a) GA4's attribution crediting those purchases to non-Ads channels and (b) Consent Mode modeling lag — verified via the DebugView test in step 3, not just assumed.

If the DebugView test in step 3 shows the gclid dying at the checkout domain, that's your actual bug, and it's the one worth fixing before spending is scaled — everything else on this list is expected behavior, not breakage.