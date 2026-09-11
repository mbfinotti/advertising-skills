# Landing Page & Attribution Audit — Veldscript Google Ads Funnel

## You didn't actually paste the URL or the ad

Your message says "I'll paste the live URL and our top ad" but neither showed up in this message. I can't run the live technical checks (redirect headers, headline-swap behavior, tag firing) without them — send them and I'll finish the technical half below. Everything below is what the numbers you *did* give me already tell me, and it's bad news independent of the page itself.

## Stop reporting 324. It isn't a number — it's an artifact of averaging two unrelated measurements.

Google Ads (412) and GA4 (236) are not two noisy samples of the same underlying event. They are two different instruments measuring two different things, using two different clocks, through a redirect that sits between them. Averaging them doesn't cancel noise — it just produces a number with no defined meaning, and you've reported it to leadership as ground truth for a month. The 74% gap between the two sources is the finding. Papering over it with an average is the opposite of an audit.

## Why they diverge — ranked by likelihood given your setup

🔴 **Cross-domain tracking break at `go.veldscript.com`.** A redirect domain sitting between the ad click and the landing page is the single most common cause of exactly this pattern. If GA4's cross-domain linker isn't configured for `go.veldscript.com → veldscript.com` (or whatever the landing domain is), GA4 starts a *new* session on arrival and can lose the click ID / UTM parameters entirely — traffic falls into `(direct)/(none)` and GA4 stops crediting it as paid, even though a real ad click happened. Google Ads still counts the conversion because its click-to-conversion link doesn't depend on GA4's session model at all.

🔴 **The redirect may not forward `utm_term` (or any query string) to the destination.** This is the headline-swap logic's single point of failure. If the tracking template on `go.veldscript.com` strips the query string on redirect, every single ad click lands on the fallback/default headline — not the personalized one the contractor built. You opening the bare URL directly and thinking "looks great" tells you nothing, because you never went through the redirect with a real `utm_term` attached. You may have been QA-ing the fallback state this whole time, never the actual personalization.

🟠 **Conversion definition mismatch.** Confirm the Ads conversion action and the GA4 conversion event are literally the same user action (e.g. both firing on the same form-submit event), not Ads counting something upstream (a call click, a different button) that GA4 doesn't track, or vice versa.

🟠 **Client-side tag loss.** If the headline-swap script is doing something heavy or broken client-side, it can delay or block GA4's `gtag.js` from firing (script order, JS error, slow personalization logic) while Google Ads' click-time crediting is already locked in before the page even renders. Consent banners, ad blockers, and Safari ITP hit GA4 harder than Ads conversion tracking too, for the same reason.

🟠 **The 41,000-session denominator is itself suspect.** If cross-domain tracking is broken, GA4 sessions for this page are likely undercounted the same way conversions are — meaning your 0.8% rate could be wrong in the denominator *and* the numerator simultaneously, in ways that don't cancel out.

## What "the page looks great to me" does not verify

Opening the URL directly with no `utm_term`, no redirect hop, and (presumably) as a logged-in employee whose browser isn't blocking your own analytics tags checks none of the following, all of which matter more than visual polish:
- Whether `utm_term` survives the `go.veldscript.com` hop
- Whether the headline swap fires correctly for the actual keyword terms in your top ad
- What happens when `utm_term` is absent or malformed (contractor may not have built a safe fallback)
- Whether GA4's tag fires before/after/independent of the swap logic
- Whether cross-domain measurement is even configured

## Checklist once you paste the URL + ad

1. `curl -sI` the ad's destination URL through `go.veldscript.com` — confirm redirect status code and whether the full query string (including `utm_term`) is present in the `Location` header.
2. Re-run with 2-3 different `utm_term` values matching real keywords in the ad group — confirm the headline actually changes.
3. Run once with no `utm_term` at all — confirm there's a sane fallback, not a broken/blank state.
4. Check the landing page's GA4 config for cross-domain linking domains — confirm `go.veldscript.com` is listed.
5. Compare the GA4 event name/trigger against the Google Ads conversion action's source — confirm they're the same event, not two different ones.
6. Check GA4 DebugView against a live test click to see if/when the conversion event fires relative to the redirect and the headline swap.

## What to tell leadership in the meantime

Retract the 324 average. Report both real numbers (412 Ads / 236 GA4) with a one-line note that they diverge because of a suspected tracking break at the `go.veldscript.com` redirect, and that a fixed number is coming once the redirect and cross-domain config are audited. Reporting a blended number that neither system produced is worse than reporting an honest "we don't trust either number yet."

Paste the URL and the ad and I'll run the actual technical checks.