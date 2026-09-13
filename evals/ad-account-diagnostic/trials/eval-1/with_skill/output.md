# Diagnosis: this is not creative fatigue — it's a broken purchase signal

Running your numbers through a structured ad-account diagnostic (measurement → structure → targeting → creative → bidding → offer → external, in that fixed order, each layer scored against your own history). Short version: **the fatigue read does not survive the data.** Don't kill any ads yet — you'd be cutting winners based on a broken meter.

## Why "creatives are burnt out" is the wrong read

Three independent pieces of evidence point the same direction, away from creative:

**1. The decomposition doesn't match a fatigue signature.** Fatigue shows up as CTR falling while the auction (CPM) stays put. Yours: CPM +3%, CTR -2% — both essentially flat, auction and click-through both healthy. The entire -44.8% ROAS collapse (2.9 → 1.6) is concentrated in one link: reported CVR, down 38%. CPM/CTR moving that little would only account for roughly a 5% hit to efficiency, not a near-halving of ROAS. Real creative decay also doesn't synchronize — it concentrates in your oldest, highest-frequency units first (retargeting) while fresh or low-exposure ones (brand) hold. Yours broke identically, same day, across cold/retargeting/brand at once. Ads don't age in sync; systems break in sync.

**2. The revenue math doesn't reconcile.** Spend is flat. If ROAS genuinely fell from 2.9 to 1.6, revenue should have fallen ~45% too. It fell ~5%. That ~40-point gap between what the reported numbers imply and what actually landed in the bank is not a rounding error — it's the platform undercounting outcomes that are, in reality, still happening.

**3. The Meta-vs-Shopify gap blew through its normal band, on the exact break date.** Your platform-to-backend gap normally runs ~8%. Right now it's ~46% (645 Shopify-attributed orders vs. 348 Meta-reported — Meta is missing roughly every other real sale). A gap that jumps 6x isn't demand or creative decaying, it's a measurement pipe leaking. And the checkout migration to a new subdomain landed the same week: purchase-tracking (pixel/Conversions API, domain verification, cross-domain cookie continuity) is exactly what a subdomain move breaks, and it breaks uniformly across every campaign feeding that checkout — which is precisely the pattern you're seeing.

Put together: your business didn't slow down. Meta's ability to _see_ your business slowed down.

## The verdict, formally

```
ROOT-CAUSE VERDICT — Velora Skin, 2026-09-12
platform(s)    : Meta | model: B2C/DTC
window         : last 12 days (~Aug 31–Sep 11) vs 60-day baseline (~Jul 3–Aug 30)
volume         : ~$45K spend (unchanged), 348 Meta-reported purchases | reconciliation gap: ~46% vs Shopify order table (your normal baseline gap: ~8%)

decomposition  : reported CVR -38% carries the entire ROAS move; CPM +3% and CTR -2% roughly net out (~+5% CPC) and cannot explain the rest
localisation   : uniform across every campaign type (cold, retargeting, brand), single common start date (the Tuesday of checkout migration)

layer screen
  measurement/tracking : FAIL - reconciliation gap jumped ~8%→46% on the checkout-migration date; revenue -5% vs an implied -45% if the reported numbers were real  [critical, high]
  structure             : pass - no structural change dated to the break; volumes well above learning-gate thresholds                                              [-, high]
  targeting              : pass - decline is account-wide, not concentrated in specific audiences; no overlap/saturation signal cited                              [-, high]
  creative               : pass - CTR essentially flat vs baseline (-2%); no concentration in oldest units; a synced, single-day account-wide break is not a fatigue curve [-, high]
  bidding/budget        : unknown - budget unchanged, no edits logged, but delivery may re-enter learning as fewer real conversions get counted; re-screen after fix [medium, low]
  offer & downstream    : pass, with a caveat - checkout itself is converting fine (Shopify orders and revenue are healthy); the migration broke *measurement* of checkout, not checkout itself [-, high]
  external               : n/a - cannot be claimed while tracking carries an unresolved FAIL, and there's no market/competitor signal offered anyway                 [-, -]

confidence     : high on the layer verdict (three independent lines of evidence - reconciliation swing, revenue-math contradiction, decomposition - all converge). Medium on window comparability: 12-day vs 60-day baseline and exact attribution-lag maturity weren't confirmed, so treat the precise percentages as directionally solid, not exact.
verdict        : measurement/tracking - the purchase event is not reliably firing/matching on the new checkout subdomain
evidence       : reconciliation gap broke from ~8% to ~46% on the migration date; revenue held (~-5%) while reported ROAS/CVR cratered (~-45%/-38%); the drop is synchronized across unrelated campaign types on one date, which fatigue never does
findings       : 1) restore + verify the Purchase event end-to-end on the new subdomain
                    [critical, high, restores every downstream number and puts delivery back on a real signal, ~hours to a day of one developer, owner: whoever owns the checkout deploy + Meta Events Manager access]
                 2) re-screen bidding/delivery once 7-12 lag-mature days have passed on the fixed signal
                    [medium, low-confidence-until-checked, near-zero effort - just wait and look, owner: media buyer]
                 3) creative refresh: real, but re-scoped - run it against clean data, not this data (see below)
                    [unquantified until re-screened, standing job, owner: creative studio]
prediction     : once the purchase event fires correctly, reported CVR recovers toward baseline within one lag-mature window (~7-12 days); ROAS follows back toward ~2.9 without touching budget or creative
handoff        : fix the tracking break first (checklist: verify pixel + Conversions API install on the new subdomain, confirm domain verification in Business Manager covers it, check event deduplication between browser and server events, confirm consent/cookie continuity survived the domain change) → re-run this diagnostic once fixed → only then hand the creative question to a dedicated creative-decay read
re-check       : ~12-14 days after the fix ships, at full attribution-lag maturity
```

## What to do right now (in order)

1. **Trace one real purchase end to end today**: place a test order (or pull a known recent Shopify order) and follow it through — did the browser pixel fire on the new subdomain? Did server-side Conversions API fire? Do they match Meta's expected `event_id` for dedup? Is the new subdomain added and verified in Business Manager? This single trace will almost certainly show you exactly where the event is getting dropped.
2. **Don't touch budget.** Not up, not down. Any meaningful budget edit right now resets learning on top of an already-corrupted signal and makes the next read even harder to trust.
3. **Don't ship new creative yet either.** If you launch new ads into an account whose purchase tracking is broken, the new ads will report exactly as badly as the old ones — you'll burn a production cycle, "confirm" the fatigue story that isn't true, and lose the team's trust in creative testing for nothing.
4. **Fix the event, then wait one lag-mature window (7-12 days)** before reading anything as signal again.

## On "which ads to kill first"

Don't build that list from this data. Every ad's reported ROAS/CVR right now is downstream of the same broken pixel — a "worst performer" ranking pulled from this window would just be ranking noise, and since the break hit every campaign type uniformly, there's no reason to think any single ad's number is more or less corrupted than another's. There's no safe signal to cut from yet.

Once the fix ships and you have a lag-mature clean window, the right way to actually pick which of your 9-week-old ads to sunset is a per-ad differential, not a blanket "everything over 9 weeks goes": look at each ad's CTR against _its own_ baseline (not the account average), check frequency (concern threshold is roughly >3 with declining CTR), and look for decay concentrated in your oldest units while newer ones hold. That's a genuinely different, narrower analysis than this diagnostic, and it's worth running deliberately once you're looking at real numbers — not as triage off a signal you now know is broken.

One thing that _is_ fine to keep planning independent of all this: your instinct that the creative is due for a refresh at 9 weeks is reasonable housekeeping regardless of what caused this specific 12-day dip. Just make that decision on its own timeline, against clean data, not as the emergency fix for a problem it isn't causing.
