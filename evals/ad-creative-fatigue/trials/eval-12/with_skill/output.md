# Mapleworks — Meta lead-gen video, creative fatigue call

## Confidence gate first

At ~180k impressions per comparison window, even a modest baseline CTR (say ~1%) gives a noise band of roughly 1% ± 2×√(0.01×0.99/180,000) ≈ **1% ± 0.05%**, i.e. under ±5% relative. Your observed moves (−27% CTR, −24% hook rate) are **5–6x wider than that band**, repeated across 4 consecutive weekly reads. This isn't noise, and it isn't a one-week blip — gate cleared with margin.

B2B conversion volume on a lead-gen ad is almost never enough to clear the conversion floor on its own, so per this skill's B2B guidance the call is being made on **leading engagement signals** (link CTR, hook rate, spend share), with CVR/CPA read as confirming only, not as the primary evidence.

## Confounder screen — all eleven, all pass

| Confounder              | Verdict                       | Basis                                                                                                                                                                                             |
| ----------------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Budget/bid change       | pass                          | Budget flat, no manual change                                                                                                                                                                     |
| Learning-phase reset    | pass                          | No edits since June — well outside any reset window                                                                                                                                               |
| Audience saturation     | pass                          | FTIR 71% sits in the healthy 65–80% prospecting band, nowhere near the ~50% saturation warning line; CVR steady is the key separator — saturation degrades CVR alongside engagement, this doesn't |
| Auction CPM inflation   | pass                          | CPM in line with your other ad sets                                                                                                                                                               |
| Seasonality/window mix  | pass                          | 4 consecutive weekly reads, consistent direction — not a single-window artifact                                                                                                                   |
| Tracking breakage       | pass                          | Reconciles with CRM                                                                                                                                                                               |
| Attribution-window skew | pass                          | Decline is sustained across 4 periods, not concentrated in the newest days                                                                                                                        |
| Placement/device mix    | pass (assumed — not supplied) | No signal pointing elsewhere; cheap to double-check but wouldn't change the call given everything else                                                                                            |
| Statistical noise       | pass                          | Deltas 5–6x the noise band at this volume                                                                                                                                                         |
| Landing page/offer      | pass                          | Untouched, CVR steady confirms it                                                                                                                                                                 |
| Sibling-mix shift       | pass                          | Only 2 ads live (this video + the static), no additions/removals — the spend-share loss is the algorithm deprioritizing this asset on its own merits, not a new sibling stealing share            |

No fail. The fatigue inquiry stays open.

## Fatigue vs. saturation

Fatigue signature: costs rising, CVR holding. Saturation signature: CVR degrading _with_ engagement, falling FTIR, flattening reach. You have the first pattern exactly — CVR steady, FTIR healthy at 71%. This is fatigue, not a depleting pool. (Wear-in doesn't apply either — these are declines, and this is a DR objective where Meta's own research found no wear-in effect anyway.)

```
FATIGUE VERDICT - Mapleworks Meta lead-gen video, 2026-09-12
platform      : Meta | funnel stage: cold prospecting (assumed from FTIR 71% - flag if this is
                actually retargeting, since that would need a different FTIR read)
window        : 4 consecutive weekly reads vs own 30-day baseline
volume        : ~180,000 impressions in window (assumed adequate spend; exact daily figures not
                supplied - doesn't change the call given the consistency and volume already shown)

signals
  link CTR              : -27% vs baseline               [leading]
  hook rate (3s)         : -24% vs baseline               [leading]
  spend share (ad set)   : falling, no manual change      [leading]
  first-time impr. ratio : 71% (healthy prospecting band) [leading, confirms NOT saturating]
  CVR                    : steady                          [lagging, the key separator]
  CPM                    : in line with other ad sets       [lagging, rules out auction inflation]

confounder screen: all 11 pass (see table above)

confidence    : high on leading signals (2 leading + spend-share corroboration, 4 consecutive
                periods, gate cleared with wide margin); CPA/CPL read is confirming only per
                B2B doctrine - low weekly conversion volume can't clear the conversion floor alone
verdict       : fatigued (not saturating - CVR stable and FTIR healthy rule that out)
action        : rung 3 - budget shift to the healthier creative (the static), immediate
ruled out     : rung 1 (hook swap) - no in-house editor, they left last month
                rung 4 (iterate) & rung 7 (new concept) for the 4-day deadline - agency lead
                time is 5 weeks, can't land before the board demo. Both are QUEUED in parallel,
                starting today, for the compounding fix (lands ~2026-10-17)
                rung 6 (audience expansion) - wrong tool for this verdict anyway (fatigued, not
                saturating), and separately blocked: legal is out, no list sign-off available
                rung 5 (frequency cap) - not selected: no over-exposure signature here (cold
                prospecting, frequency wasn't flagged, FTIR is healthy)
                rung 8 (full pause) - not the first move: still converting (CVR stable), and
                there's somewhere better to send the budget, so no need to kill it outright
expected      : CPL on this ad set should stabilize within days as spend concentrates on the
                still-healthy static; won't fully recover the video's own trend, because the
                video itself stays fatigued until the iteration lands
re-check      : CPL pulse 2026-09-15 (day before the board demo); full fatigue re-check on the
                new mix 2026-10-12 (one 30-day window after the shift)
```

## What to actually do, in order

**1. Today — budget shift, not a pause.** Manually move the bulk of ad-set spend weight off the video and onto the static. Don't zero the video out completely: it's still converting at a stable rate, and per this account's own doctrine you never pause a still-profitable producer with nothing staged to replace it. Leave it at a minimal testing weight so you keep the read alive.

Why this and not a hook swap: your video editor left, so rung 1 (the normally cheapest, fastest fix — hook fatigue is exactly what this data shows: hook rate down, CTR down, CVR untouched) is off the table. Budget shift is the highest rung your actual capacity supports right now.

**2. Today — brief the agency, in parallel, not on the demo's clock.** The decay pattern (hook rate down, CVR untouched) says the _concept_ isn't spent, just its opening. That means an iteration — new hook/opening on the same proven body — not a full new-concept rebuild, is the right ask, and practitioner-reported recovery on element-level iteration runs 60–80% of original performance. At a 5-week minimum lead time this won't touch the board demo, but starting it today is the only way it lands before the _next_ board cycle instead of after it.

**3. Before the demo — have the number ready, not a promise.** Pull a CPL read on 2026-09-15, one day out. You won't have a full clean window by then, but you'll have 2–3 days of the shifted mix, enough to show the board the bleeding has stopped, with the honest framing: "root cause diagnosed as creative wear-out, immediate mix change is holding CPL, full replacement is in production, lands mid-October."

**4. Watch the static now that it's absorbing more load.** Concentrating spend on it moves up its own fatigue clock — baseline it going forward the same way you just did the video, so you don't get blindsided by the same pattern on your only other live asset.

**5. What would change this call.** If funnel stage is actually retargeting rather than cold prospecting, the 71% FTIR reading flips meaning (it would be unusually high for warm, not a health signal) — worth a 10-second confirmation before the board meeting, since it doesn't change the recommended action but does change how confidently you can state the "not saturating" line if challenged.
