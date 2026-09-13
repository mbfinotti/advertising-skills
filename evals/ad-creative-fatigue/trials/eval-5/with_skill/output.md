# Ledgerline — Creative Fatigue vs. Audience Saturation Read

Running your LinkedIn ABM numbers through the confounder screen first, because that's where this call gets made — not on impulse from a CTR chart.

## Confounder screen

| Confounder                | Status                     | Note                                                                                                                                                                                                                                                                                                                   |
| ------------------------- | -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Budget/bid change         | pass (assumed)             | No change reported — confirm no bid-strategy step in the last 4 weeks before trusting this line.                                                                                                                                                                                                                       |
| Learning-phase reset      | pass                       | The week-3 ad is a _new launch_, not an edit to the other four; its own decay is data, not noise.                                                                                                                                                                                                                      |
| **Audience saturation**   | **FAIL**                   | Reach flat for a month while impressions climb, frequency 7.8 on a 38k-member cold ABM list, and the discriminating test already ran itself: the ad launched 3 weeks ago fell to the pack's level within 2 weeks _on the same list_. That's Meta's own fatigue-vs-saturation test failing in the saturation direction. |
| Auction CPM inflation     | pass (untested)            | Not the story here — CTR itself is collapsing, not just cost per impression.                                                                                                                                                                                                                                           |
| Seasonality/window mix    | pass                       | Decline is gradual across a month, not a weekend/holiday artifact.                                                                                                                                                                                                                                                     |
| Tracking breakage         | pass (assumed)             | Confirm platform-reported demo requests reconcile against CRM form-fills before trusting the 6→2-3/week drop.                                                                                                                                                                                                          |
| Attribution-window skew   | pass                       | LinkedIn form-fill conversions post near-real-time; low risk here.                                                                                                                                                                                                                                                     |
| Placement/device mix      | pass                       | Sponsored Content is effectively one placement; not a mix-shift story.                                                                                                                                                                                                                                                 |
| Statistical noise         | pass (fails to explain it) | Even at a conservative 20,000 comparison-window impressions, baseline CTR 0.43% has a noise band of roughly 0.34%–0.52% (`0.43% ± 2×√(0.43%×99.57%/20,000)`). Observed 0.29% sits clearly below it. The decline is real, not sampling.                                                                                 |
| Landing page/offer change | pass                       | If it were the landing page, you'd see CTR healthy with CVR collapsing. You have both CTR _and_ click-to-demo sliding together — that's the saturation signature, not the landing-page one.                                                                                                                            |
| Sibling-mix shift         | noted, not causal          | A 5th ad joined 3 weeks ago; the decay predates and outlives that change.                                                                                                                                                                                                                                              |

## Verdict

```
FATIGUE VERDICT - Ledgerline 5-ad LinkedIn ABM set, 2026-09-12
platform      : LinkedIn | funnel stage: cold prospecting (matched ABM account list)
window        : last ~3 weeks vs baseline ~7 weeks prior
volume        : list ~38,000 members, 5 ads, frequency 7.8 (avg over run)

signals
  link CTR              : 0.29% vs 0.43% (-33%)                    [leading]
  reach (rolling)        : flat ~1 month while impressions climb   [leading]
  fresh-ad discriminating test : new ad (wk 3) decayed to pack within 2 weeks on SAME list [leading, decisive]
  frequency              : 7.8, lagging/confirming, all 5 ads converging together [lagging]
  CVR (click->demo)      : degrading ALONGSIDE CTR, not holding    [lagging]
  demo requests           : ~6/wk -> 2-3/wk                        [lagging]

confidence    : medium - demo-request volume (single-digit-to-low-teens weekly) cannot clear
                the conversion floor on its own; call is gated on the leading engagement
                signals (CTR, reach/impressions divergence, the fresh-ad test), which are
                consistent and well outside the noise band
verdict       : saturating (the ABM pool, not the creative)
action        : rung 6, promoted to rung 1 under a `saturating` verdict - expand/refresh the
                matched account list and multi-thread within existing accounts; do NOT
                commission a like-for-like creative batch against this same 38k list - the
                week-3 ad already ran that experiment and it changed nothing.
ruled out     : none stated - no effort-ceiling or sign-off constraint given yet; flag that
                list refresh/expansion for ABM typically needs a lawful-basis check before
                any new upload.
expected      : CTR and click-to-demo recover only as new members enter the pool, not before;
                frequency should fall below ~5-6 once the list grows; if the fresh-ad test is
                repeated on an EXPANDED list and still decays fast, re-open the fatigue case.
re-check      : ~2026-10-10 (one full comparison window after the list refresh lands)
```

## Direct answer: how many new ads, what angles

**Zero, against the current 38,000-member list.** A new creative batch fixes fatigue, not a depleted pool — and you already ran the controlled experiment for this: the ad launched three weeks ago is new copy, new asset, same list, and it decayed to the group average in two weeks. That's the "does a fresh creative recover performance on the same audience" test from Meta's own fatigue research, and it failed. Briefing five more ads into the same list spends the approved budget to reproduce that same result.

**What to actually do with the approved budget:**

1. **Redirect it to list work first, not production.** Refresh/expand the matched account list (new ICP-fit accounts, intent-data adds, lookalikes off closed-won), and check whether you're saturated at the _account_ level or just the _contact_ level within those accounts — multi-threading to untouched buying-committee members inside already-matched accounts is a cheaper expansion than growing the account list itself, and doesn't need a fresh lawful-basis review.
2. **Hold the creative brief until the list actually grows**, then brief a small batch for the _net-new_ segment only — 3-4 ads, in line with LinkedIn's own 4-5-per-campaign delivery guidance, not a full 5-ad replacement of the current set.
3. **Angles for that batch should be top-of-funnel, not a repeat of the current messaging**: category/problem-education and proof-driven positioning for accounts that have never seen Ledgerline, rather than the demo-request-forward angles the current five have already run past this list 7-8 times on average (frequency 7.8). Reusing the current angle set on a still-cold new segment is fine; reusing it on the _same_ saturated list is the mistake you're trying to avoid.
4. Add a frequency cap/exclusion on members who've cleared a high exposure threshold while the list refresh is in flight — near-zero effort, buys relief on the worst-saturated members immediately.

**What would raise confidence further, if you can pull it:** per-ad daily CTR/impressions/reach (not just the blended numbers above), confirmation of no bid/budget changes in the last month, and reconciliation of platform-reported demo requests against CRM. None of it is likely to flip the verdict — the fresh-ad test result is close to definitive on its own — but it would move this from medium to high confidence and sharpen the re-check comparison.
