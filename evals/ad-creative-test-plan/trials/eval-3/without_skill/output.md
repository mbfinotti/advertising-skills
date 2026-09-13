Four things in this plan will quietly poison the read. Here's what I'd change, and why.

## 1. CBO across 3 ads in one ad set ≠ a valid test

CBO is a budget-exploitation algorithm, not a randomized experiment. It reallocates spend toward whichever ad gets early signal — which is often driven by delivery luck, novelty, or accumulated social proof (likes/comments), not true creative quality. Expect it to dump 70-80% of budget into one concept within the first 2-3 days, starving the other two before they generate enough data to judge.

**Fix:** run the 3 concepts in separate ad sets with fixed, equal daily budgets — or use the platform's built-in split-test tool (Meta Experiments / Google Ads experiments), which randomizes audience and controls for exactly this bias. Save CBO for after you've picked a winner.

## 2. AI creative enhancements add an uncontrolled variable

Auto-crop, music, text overlays, generated variants — these apply per-impression, adding noise inside each ad and making it unclear whether a win came from the concept or from what the algorithm auto-generated around it.

**Fix:** disable enhancements during the concept test. Turn them on afterward to optimize the winner — that's a second, separate test.

## 3. The budget doesn't support 3-way significance

$450/day × 14 days = $6,300 total. Split evenly, that's ~$2,100 and ~116 conversions per concept at an $18 CPA — thin but workable. Under CBO, it won't split evenly: 1-2 concepts will likely end the test with <20 conversions each, too few to conclude anything. 🎯 Decide your minimum sample (e.g. ≥100 conversions/arm) before launch, and size budget/timeline to guarantee it under equal-split delivery, not CBO's.

## 4. Q2's $18 CPA is a stale, confounded baseline

Comparing today's result to a number from a different quarter ignores seasonality, CPM shifts, competitive pressure, and platform algorithm changes since then. It's not apples-to-apples.

**Fix:** re-run the champion concurrently as a small live control arm (e.g. $50/day) alongside the 3 new concepts. Compare against that, not the historical number.

## 5. Watch the winner-selection bias

Picking the best of 3 and checking it against a fixed threshold inflates false positives — the more concepts you test, the likelier one beats $18 by chance even if none are actually better. Require the winner to beat the _concurrent_ champion CPA with enough volume and a real margin, not just a nominal edge.

## Recommended structure

- 4 ad sets, fixed equal budgets: 3 new concepts + 1 re-run champion (~$112/day each, or skew slightly more to champion for a tighter control CI).
- No CBO, no auto creative enhancements, during the test.
- Pre-register the decision rule: min. 100 conversions/arm, winner's CPA must beat the concurrent champion's CPA outside overlapping confidence intervals.
- Track ROAS/AOV alongside CPA — a snack brand's repeat-purchase economics can make a slightly higher-CPA concept the better long-term bet.
- 2 weeks is tight for this structure to reach significance on all 4 arms; be ready to extend rather than force a call on thin data.
