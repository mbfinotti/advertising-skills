# Bexley Books — Evergreen Carousel: Diagnosis & Plan

## Verdict first

**This is not fatigue. It's a measurement artifact — don't refresh the creative yet.**

Everything described matches a textbook attribution-lag pattern, not creative wear-out:

| Symptom you reported | What it actually is |
|---|---|
| CPA up ~25% every Monday | Newest days in a trailing window are always under-reported — conversions haven't finished landing yet |
| Gap shrinks by the next pull | Those same days "mature" and backfill conversions a week later — the decline was never real, it just hadn't finished counting |
| Mid-month switch: 7-day click → 1-day click | 1-day click credits far fewer conversions for identical buyer behavior. Any week compared across that switch will show a step-change CPA jump that has nothing to do with the ad |
| CTR (all) stable, so "engagement is fine" | CTR (all) includes likes/comments/shares, not outbound clicks — it can hold steady while actual click-through intent is falling. It doesn't clear the ad; it's just the wrong metric |

A stable ~25% jump that recurs weekly and then partially resolves is the opposite of what real fatigue looks like — real decay compounds or holds, it doesn't shrink itself away three weeks later. Two structural artifacts (trailing-window lag, and comparing across an attribution-setting change) are enough on their own to produce exactly this pattern.

## What NOT to do

Don't brief a refresh off this data. If you ship new creative now and CPA "recovers" next month, you'll credit the new ad for a recovery that was actually the attribution lag catching up — and burn production budget confirming a false positive.

## Fix the measurement, then re-run the read

1. **Re-pull on lag-mature windows.** Compare two windows that are both old enough for attribution to have fully closed (e.g., days 14–20 vs. days 21–27 ago), not "last 7 days," which is guaranteed to look worst.
2. **Standardize the attribution setting across baseline and comparison.** Either:
   - Re-pull the pre-switch weeks under 1-day click (most platforms let you re-run historical reports under a different attribution window), so every week in the trend uses the same yardstick, or
   - Keep 1-day click as the go-forward standard but restart the trend line from the switch date — don't compare across it.
3. **Swap the CTR you're reading.** Pull **link/outbound CTR**, not CTR (all), for the carousel. That's the metric that actually tracks intent.
4. **Pull the rest of the confounder-screen data** before anyone reopens the fatigue conversation:
   - Change log: any budget/bid, audience, or optimization-event edits in the last 6 weeks?
   - CPM trend for this ad set vs. the account average (rules auction inflation in/out)
   - First-time impression ratio and reach trend (rules audience saturation in/out — a book DTC evergreen carousel can plausibly be saturating a mid-size retargeting or lookalike pool)
   - Platform-reported conversions vs. Shopify order count, as a ratio over time (catches tracking breakage / consent-mode drift, which a "switch to be conservative" mid-month sometimes accompanies)
   - Any sibling creatives added/removed in the same ad set in that window

## What I still need from you to close this out

- Platform: assuming Meta (carousel + "CTR (all)" is Meta's own terminology) — confirm.
- Funnel stage: cold prospecting or retargeting? Tolerance for frequency/exposure differs a lot.
- Daily spend and conversion volume on this carousel specifically — decides whether we can even clear a statistical read once the measurement is fixed.
- Any budget, bid, or edit changes to this ad or ad set in the last 6 weeks, besides the attribution-window switch.

## If, after fixing measurement, a real decline still survives

Only then does this become a fatigue question, and the discipline is:
- Require at least two signals (link CTR + one more — spend share, first-card engagement, hold-through-carousel rate) moving together across two-plus lag-mature periods, past the noise floor for your volume.
- Split fatigue from saturation: costs up with conversion rate holding = fatigue; both degrading together with falling first-time-impression ratio = saturation — opposite fixes.
- If it lands on fatigued: start at a **hook/thumbnail swap on the first carousel card**, not a full new concept — cheapest, fastest, and correct if it's the opening card losing pull rather than the whole sequence. Iterate the winning concept only if the swap doesn't hold; reserve a brand-new concept for if iteration stops recovering performance.

## Re-check

Re-pull the corrected, lag-matched trend in **2 weeks** (by 2026-09-26) once the attribution window is standardized. Don't touch the creative before then — you don't have a real signal to react to yet.