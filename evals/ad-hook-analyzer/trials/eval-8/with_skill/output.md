## Is the pre-ranking system working? Not something this data can answer yet — and the boss's bar is the wrong bar.

### First problem: the "measured results" for batches 1–3 aren't hook rate at all

Per Meta's own metric definitions, ThruPlays ÷ impressions is not hook rate — it's one of the two **hold-rate** constructions in circulation. ThruPlay counts completion *or* 15+ seconds watched. That's a fundamentally later, different window than the ≈3-second opening the pre-ranking scores.

- Batches 1–3 (old dashboard): `ThruPlays ÷ impressions` → hold rate — reflects pacing, story, and offer across the whole video.
- Batches 4–5 (new dashboard): `3-second plays ÷ impressions` → the actual hook rate — reflects the opening only.

The pre-ranking scores the opening and explicitly stops there ("scope ends at the ranking... editing, pacing, structure beyond the opening is out of scope"). Grading it against a hold rate is grading it on material it never claimed to predict, on top of measuring a different time window entirely. That's not a rounding quirk in the data — it's comparing two different constructs, the exact "two-dashboards trap" that exists precisely because agencies mix these up.

So batches 1–3 can't validate or invalidate the pre-ranking. Only batches 4–5 are a clean test.

### The numbers, for completeness

Top-half check (predicted #1 pick landing in the top half of measured results):

| Batch | Result | Metric used | Top half? | Valid test of the hook ranking? |
|---|---|---|---|---|
| 1 | 1st of 5 | ThruPlay/impressions (hold rate) | Yes | No — wrong construct |
| 2 | 4th of 6 | ThruPlay/impressions (hold rate) | No | No — wrong construct |
| 3 | 2nd of 4 | ThruPlay/impressions (hold rate) | Yes | No — wrong construct |
| 4 | 5th of 5 | 3s-plays/impressions (hook rate) | No | Yes |
| 5 | 3rd of 6 | 3s-plays/impressions (hook rate) | Yes | Yes |

Pooling all five naively gives 3/5 top-half hits, which — for what it's worth — would already *clear* the skill's stated pass bar (≥3 of 5). But that pooled number is built on contaminated data and shouldn't be trusted either way.

Restricted to the only valid comparisons (batches 4–5): 1 of 2 top-half hits. That's not evaluable — the calibration check requires a 5-batch rolling window, and 2 points is not a window, it's an anecdote.

**Verdict: unknown, not failing.** There is no valid 5-batch sample yet. Three of the five "results" measured something the tool was never scored against.

### Second problem: the boss's bar itself is wrong, independent of the data issue

The skill is explicit that the outcome measure is **rank agreement**, not exact-winner accuracy, and sets the pass threshold at "top-ranked pick lands in the top half at least 3 of 5 times" — deliberately modest, calibrated to beat a coin flip, not to be an oracle. Two things back this up:

1. Hook-style attention metrics correlate **-0.19 with ROAS** in the sourced dataset (slightly the wrong direction). A tool built on these dimensions was never going to reliably call the outright winner — that's evidence about the ceiling of what *any* pre-launch attention score can do, not a flaw specific to this account's execution.
2. Roughly 5% of creatives become winners at all. Demanding "the winner, every time" from a 5-candidate-average batch is a near-impossible bar by construction, regardless of tool quality.

So "anything short of the exact winner every time = useless" isn't a fair test of this system; it's a test no shortlisting device — human or model — would pass.

### What to do next

1. **Re-pull batches 1–3 under the new dashboard's definition.** 3-second-play counts are a standard Meta field independent of which dashboard report was used to view them — they should still be sitting in Ads Manager for those historical ads. Re-derive `3-second plays ÷ impressions` for batches 1–3 so all five batches share one construct.
2. **Re-run the 5-batch rolling-window check** on the corrected, consistent numbers. That's the first calibration check that will actually mean something.
3. **Lock the denominator going forward**: one hook-rate definition, written on every scorecard, per the skill's calibration rule — no more silent dashboard switches mid-series.
4. Reframe the target for your boss: the agreed pass bar is "top-ranked pick in the top half, ≥3 of 5 batches" — not "correct winner, 5 of 5." If leadership wants a stricter bar, that's a legitimate call to make explicitly, but it should be set knowing the -0.19 ROAS correlation ceiling on these metrics, not applied retroactively to kill a tool that was never designed to clear it.