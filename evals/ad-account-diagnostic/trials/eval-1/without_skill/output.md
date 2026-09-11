## Verdict: reject the fatigue read. This is a broken pixel, not tired creative.

**The tell:** creative fatigue is gradual and creative-specific. It never produces a synchronized, account-wide cliff on a single calendar day across cold, retargeting, and brand simultaneously — those have different creatives, different audiences, different frequencies, and would degrade at different rates. A same-Tuesday drop across the entire account is the signature of a technical/tracking event, not an audience wearing out on an ad.

You have that technical event: **checkout moved to a new subdomain the same week.**

## Why the numbers say tracking, not fatigue

- **Shopify revenue is ~flat (-5%, within normal noise).** If 348→ the real story were fewer people converting, revenue would have cratered along with ROAS. It didn't. Demand didn't collapse — something stopped counting it.
- **The Meta/Shopify order gap blew out from a normal ~8% to ~46%** (348 reported vs. 645 actual). That ~38-point jump in the gap lines up almost exactly with your reported CVR drop of -38%. That's not a coincidence — it's the same number seen two ways: Meta is simply failing to attribute roughly half of real purchases.
- **CPM +3% / CTR -2% are real but secondary**, and this is where the story stays consistent: Meta's delivery and bidding algorithms optimize on the Purchase signal. Feed them a conversion signal that's suddenly missing ~46% of true purchases, and the algorithm reacts as if performance degraded — it drifts toward broader/lower-intent placements and gets noisier, softening CTR and nudging CPM up. That's the algorithm reacting to bad data, not the audience getting bored of your ads.
- **9-week-old creative doesn't cliff-drop on a Tuesday.** Fatigue shows up as a slow bleed correlated with rising frequency per ad, not a step-function across the whole account timed to a checkout migration.

## What almost certainly broke

Checkout domain changes routinely break Meta measurement in one of these ways — check in this order:

1. **Pixel/GTM snippet not ported** to the new checkout subdomain's order-confirmation page (very common — redesigns move the funnel HTML and forget the tracking snippet).
2. **CAPI (Conversions API) still pointed at the old domain's webhook/URL pattern**, or event_id dedup between Pixel and CAPI broke, causing drops or double-count suppression.
3. **fbp/fbc cookie scope** — if those cookies were set on the old checkout domain and not on a shared root domain (e.g. `.veloraskin.com`), the browser won't send them across the new subdomain, breaking click-to-purchase matching.
4. **Domain verification / Aggregated Event Measurement** not updated for the new subdomain in Business Manager — silently affects prioritized event reporting, especially iOS.

## Action plan

1. **Do not touch creatives yet.** Killing or refreshing ads now would (a) burn budget/learning phase on a problem creative isn't causing, and (b) contaminate your read on the *new* creatives, since they'd inherit the same broken tracking and look "bad" too.
2. **Today: fire a real test purchase on the new checkout subdomain** and watch Meta Events Manager > Test Events. Confirm the Purchase event fires, check for cross-domain cookie warnings.
3. **View-source / check GTM container on the new confirmation page** — verify the pixel base code and Purchase event tag actually exist there.
4. **Check CAPI webhook target and event_id dedup** against the new domain.
5. **Check cookie domain setting** (should be root domain, not subdomain-scoped) and domain verification/AEM config in Business Manager for the new subdomain.
6. **Align timestamps, not just days:** pull hourly Events Manager data and hourly Shopify orders around the exact cutover time on that Tuesday. If the Purchase-event drop starts at the exact deploy timestamp, that's your confirmation, full stop.
7. **Loop in whoever owns the migration** — ask directly whether the Meta pixel/CAPI integration was carried over and re-validated post-migration. This is usually a one-line fix, not a rebuild.
8. **Re-run the fatigue analysis only after tracking is confirmed fixed**, and do it per-creative (frequency vs. each ad's own historical CTR baseline), not off account-level CVR — that metric is corrupted for the whole window and tells you nothing about any individual ad.

## On "which ads to kill first"

Don't kill anything off this data — the CVR collapse is an account-wide measurement artifact, not a creative signal, so it can't tell you which ads are actually tired. Once tracking is fixed, triage with metrics tracking didn't corrupt: frequency (kill cold ads pushing frequency >3.5–4, retargeting can run hotter) and CTR trend measured against each ad's own pre-migration baseline. Until then, budget is unchanged and real revenue is basically fine — the urgent risk isn't today's ROAS number, it's Meta's bidding algorithm continuing to optimize on garbage conversion data the longer this stays unfixed.