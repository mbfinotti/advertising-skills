## The core problem

"Briefs that produced winners" measures the campaign's outcome, not the brief's quality. At 4 concepts/month, two sprints will give you somewhere between 2 and 8 data points. A metric with that little volume is noise, not signal — and CMO-facing dashboards built on noise produce bad decisions (killing a good process because of bad luck, or greenlighting a bad one because of good luck).

Quick sanity check: if the *true* long-run win rate a good briefing process produces is, say, 25% (a reasonable ballpark for ad testing), then with N=4 concepts, the probability of landing at 0 or 1 winners — i.e., "the process looks broken" — is over 70%, purely from binomial variance. The metric would fail the process almost by default even if it's working perfectly.

So the fix isn't a better metric — it's separating two different things that are currently being conflated into one number.

## Split into leading (process) and lagging (outcome) metrics

**Leading metrics** — measure the brief itself, available same-day, every brief, no volume problem.
**Lagging metrics** — measure what the brief produced, need volume and time before they mean anything, and are confounded by execution and media/audience luck.

A "briefing process" dashboard should be built almost entirely on leading indicators, with the lagging outcome shown transparently but not treated as a gate at N<20-30.

## Leading metrics (day-one, per brief)

- **Brief completeness score** — a checklist (objective, audience, insight, mandatories, success criteria, prior-learnings reference) scored 0-100%, self-scored or reviewed by a lead. This is a direct measure of the process being followed.
- **Clarification cycles** — number of back-and-forths between brief owner and creative team before work starts. Fewer cycles = clearer brief. Track median, not average (outliers skew hard).
- **Time-to-brief-approval** — days from kickoff to a signed-off brief. Process efficiency, independent of creative outcome.
- **Creative team confidence rating** — 1-5 survey immediately after receiving the brief ("Do you have what you need to produce a strong concept?"). This is the single best early proxy for brief quality because it's the direct consumer's judgment, not a downstream proxy three steps removed.
- **Rework rate** — % of concepts sent back for a brief-caused reason (missing insight, wrong audience, unclear success criteria) vs. a creative-execution reason. This isolates brief failures from creative failures, which "win rate" cannot do.

These are all available from concept 1, don't need statistical power, and directly answer "is the process being followed and is it producing clear inputs."

## Lagging metric — done properly

- **Define "winner" rigorously before you track anything**: a fixed, pre-registered threshold (e.g., beats control/baseline by X% on the primary KPI at your test's minimum detectable effect, run for the full planned duration). Without this, "winner" is retroactively negotiable and the whole metric is gameable.
- **Report win rate as a raw count with a confidence interval or a Bayesian posterior, never as a bare percentage**, until N is large enough that the interval is actually informative — realistically 20-30+ concepts, i.e., 5-8 months at your volume. "2/4 winners" and "1/4 winners" should not visually read as "50% vs 25% success rate" on a CMO dashboard; that framing manufactures false confidence in both directions.
- **Track it cumulatively (rolling 6-12 month window), not per sprint.** Per-sprint win rate at this volume is pure noise regardless of process quality.

## What the day-one dashboard should actually show

1. Top row: the 5 leading metrics above, per brief, trending sprint over sprint — this is what "is the process working" actually means at low N.
2. Second row: cumulative win rate since program start, shown as raw counts (e.g., "1 winner / 5 concepts tested") with the confidence interval visibly wide, explicitly labeled as directional until N≈20-30.
3. A correlation view once you have enough data (6+ months): brief completeness score vs. win/loss, to actually test whether the leading indicators predict the lagging one. This is the real validation of the process — not the raw win rate itself.

## What to tell the CMO

Reframe the two-sprint condition, don't fight it: agree to report win/loss transparently every sprint from day one (she'll see it either way), but propose the leading-indicator scorecard as the thing that's actually gated on at 2 sprints, with an explicit commitment to revisit the win-rate threshold at a volume where it's statistically meaningful (~6-8 months / 25-30 concepts). Frame it as "we're not hiding from the outcome metric, we're refusing to let 4 coin flips decide the program's fate" — that's a stronger position with a stats-literate exec than pushback on principle alone.