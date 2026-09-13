# Verdict: this decay reads as textbook hook fatigue — but "start over with a new concept" is the wrong rung. Here's the diagnosis.

## Quick read

Hook rate falling for three straight weekly reads (24→19→16%) while hold rate at 15s stays flat (9.1% vs 9.4% baseline) is the specific signature of **hook fatigue, not ad fatigue**: the opening is tired, the body still holds attention once people watch. CVR holding at 2.8% while hook/CTR decay is the fatigue signature (people who still click still convert) rather than saturation (where CVR degrades alongside engagement). That argues strongly against needing a whole new concept.

## Confounder screen

| Confounder              | Status                                                                                                                                                                                                             |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Budget/bid change       | pass — none reported                                                                                                                                                                                               |
| Learning-phase reset    | pass, assuming no edits in-window — **confirm last edit date** before closing this                                                                                                                                 |
| Audience saturation     | leans pass (CVR stable is the opposite of the saturation pattern) — **but confirm with first-time-impression ratio / reach trend**, you haven't sent it and it's the one confounder that would flip the whole call |
| Auction CPM inflation   | can't screen without CPM data — **pull CPM for this creative vs the account's other ad sets**; if CPM is flat while CTR fell, that rules this out cleanly                                                          |
| Seasonality/window mix  | pass — weekly reads are naturally day-of-week matched                                                                                                                                                              |
| Tracking breakage       | pass — CVR stability across all three weeks means conversions are being counted consistently                                                                                                                       |
| Attribution-window skew | pass, assuming weekly reads are lag-mature                                                                                                                                                                         |
| Placement/device mix    | not checked — low priority given the rest of the pattern is this consistent                                                                                                                                        |
| Statistical noise       | **FAIL cleared, i.e. real signal.** At ~150k impressions/week, the noise band on a 24% hook rate is roughly ±0.22pp (24%±2×√(0.24×0.76/150000)). A drop to 16% is ~35 standard errors out — nowhere near noise.    |
| Landing page/offer      | pass — none reported, and CVR stable is the opposite of the landing-page-break signature                                                                                                                           |
| Sibling-mix shift       | not checked — **how many creatives are in this ad set, and did any launch/pause recently?**                                                                                                                        |

Three checks are still open (CPM trend, first-time-impression ratio, sibling mix/last edit date). None of them cost more than a dashboard pull, and I'd run them before committing real money — but nothing in what you've sent points toward them flipping the call, and the signal shape (hook down, hold flat, CVR flat) is specific enough to act on this week regardless.

## Confidence gate

- Noise check: cleared with wide margin (above).
- Two-signal rule: hook rate and link CTR, both leading, moving the same direction across 2+ consecutive weekly periods. Cleared.
- Conversion floor: CVR stable at 2.8% on 150k weekly impressions — plenty of volume for a B2C read, no need to lean on engagement-only signals.

**Confidence: high**, pending the three open confounder checks above.

## Fatigue vs. saturation split

Saturation would show CVR degrading alongside engagement and a falling first-time-impression ratio. You have the opposite — CVR flat — which is the fatigue tell, not the saturation tell. I'd still pull first-time-impression ratio to close this out formally, but don't let it block this week's action; nothing about a hook swap makes a saturation problem worse if you're wrong.

## Verdict block

```
FATIGUE VERDICT - "trail-taste-test", 2026-09-12
platform      : Meta | funnel stage: cold prospecting (assumed — not stated, confirm)
window        : trailing 3 weekly reads vs prior baseline
volume        : ~150k impressions/week

signals
  hook rate (3s)  : 16% vs 24% three weeks ago (-33%)   [leading]
  link CTR        : down ~20%                            [leading]
  hold rate (15s) : 9.1% vs 9.4% (flat, within noise)     [leading/secondary]
  CVR             : 2.8% vs 2.8% (stable)                 [lagging]
  hide/report rate: 3x account norm                       [confirming, negative-feedback]

confounder screen
  budget/bid change        : pass
  learning-phase reset     : pass (assumed) - confirm last edit date
  audience saturation      : pass (CVR stable argues against it) - confirm FTI ratio/reach trend
  auction CPM inflation    : NOT CHECKED - pull CPM vs account
  seasonality/window mix   : pass - weekly cadence, matched windows
  tracking breakage        : pass - CVR stable across 3 weeks
  attribution-window skew  : pass (assumed lag-mature)
  placement/device mix     : not checked - low priority given signal strength
  statistical noise        : pass - hook-rate delta ~35 SE outside baseline band
  landing page/offer change: pass - CVR stable is the inverse of this signature
  sibling-mix shift        : NOT CHECKED - confirm ad-set composition/recent changes

confidence    : high - 2 leading signals, 3 consecutive periods, gate cleared with wide margin;
                3 low-cost confounder checks still open, none expected to flip the call
verdict       : fatigued (hook-specific - hook down, hold flat, CVR flat)
action        : rung 1 - new hook/opening on the same body, shipped as a NEW asset ID
                (not an edit) because the elevated hide/report rate means a same-ID swap
                won't clear the algorithmic penalty. In-house editor, this week.
ruled out     : new concept (rung 7) - nothing here shows the CONCEPT is exhausted, only
                the opening. Going straight to a 6-week agency rebuild skips the cheapest,
                fastest rung your own signal pattern points at, and shelves the in-house
                editor's spare capacity for a slower, costlier fix.
expected      : hook rate and link CTR recover toward baseline on the same audience;
                CVR stays flat throughout (it never moved). Recovery on the same audience
                also closes out the saturation question definitively.
re-check      : 2026-09-22 (one full weekly window after the new hook ships), with a second
                confirmatory read 2026-09-29 given nine weeks of prior wear-in history
```

## Direct answer to "sound right?"

No. Two things to change:

1. **Don't retire the creative.** It's still your volume driver at a stable 2.8% CVR — pause nothing, keep it running while the fix ramps.
2. **Use the in-house editor this week, not the agency in six.** Cut a new opening on the same body and ship it as a new ad ID (the tripled hide/report rate means editing the existing ID won't clear the penalty — has to be a fresh upload). That's an hour-or-two job, reversible, and it's precisely what a hook-down/hold-flat/CVR-flat pattern calls for.

If the new hook _doesn't_ recover hook rate and CTR at the next check (Sep 22), that's real evidence to escalate — iterate further (new pacing/format, still same concept) before concluding the concept itself is spent. Only if iteration stops recovering performance across a couple of attempts does a full agency rebuild become the right call, and at that point you'd be briefing it with actual evidence instead of a hunch.

Separately: briefing the agency on a new concept _in parallel_, as a compounding bet for later rather than a replacement for this fix, is reasonable — six weeks is roughly the lead time for that kind of work anyway, and you don't want to be starting cold if trail-taste-test's concept does eventually run out. Just don't frame it as "starting over," since nothing in your data says the concept is the problem.

**Still worth pulling before you finalize either move:** CPM trend for this creative vs. the account average (rules out auction inflation), first-time-impression ratio or reach trend (formally rules out saturation), and the ad set's sibling count/recent changes (rules out mix-shift). All three are near-zero-cost dashboard pulls, and none of them should slow down shipping the new hook this week — but I'd want them closed before you sign off on six weeks of agency spend.
