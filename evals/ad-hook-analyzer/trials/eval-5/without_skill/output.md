## Sanity check: Halyard Swim hook evaluation system

I don't have the spreadsheet or the 9-hook batch itself (nothing under that name exists in this repo outside the folder I was told to leave alone), so this is a review of the _system's design_ — the weighting model and the diversity claim — as described. Two real problems, one presentational nit.

### 1. The weighted score is compensatory — and that's the wrong shape for this decision

30/25/15/10/10/5/5 sums to 100, so the arithmetic is fine. The design flaw is that a linear weighted sum lets any dimension buy back any other. A hook that's fast and specific (55% of the score) can coast to a high total even if it's:

- **off-brand** (brand timing 10%) — e.g., tone-deaf during a sponsorship moment or against current messaging
- **misleading** (promise continuity 5%) — sets up a payoff the rest of the ad doesn't deliver
- **wrongly targeted** (audience qualification 10%) — hooks the wrong viewer, burning spend even if the hook itself is great

For a creative production, brand-safety and promise-integrity failures shouldn't be "worth 5-10 points" — they should be gates. **Fix:** split the model into (a) pass/fail gates for brand timing and promise continuity — a hook that fails either doesn't get scored, full stop — and (b) the weighted sum for the remaining tradeable dimensions (time-to-signal, specificity, legibility, audience qualification, placement fit).

A second, quieter issue: time-to-signal (30%) and specificity (25%) are likely correlated in practice — a hook that states the specific benefit fast usually scores well on both. That's not fatal, but it means ~55% of the score may really be one latent factor wearing two hats, not two independent signals. Worth checking with the actual 9 scores: if time-to-signal and specificity move together across the batch, the model is less "7 independent dimensions" than it claims.

**Missing entirely: anchors and a backtest.** The weights say how much each dimension counts, not what a 7 vs. a 9 looks like on "specificity." Without written anchors, the 30% and 25% slots are effectively however the scorer feels that day — and since she built the system, she's also the most likely scorer, which is a conflict of interest worth a second, blind rater. More importantly: has this formula been run against past hooks with known performance (hook rate, 3-second hold, CTR)? If not, this is an untested opinion dressed as a scoring system. Before rollout, backtest it against the last batch or two of hooks with real outcome data and check that high scorers actually outperformed.

### 2. "7 of 8 hook types covered" does not prove diversity — it's close to a mathematical certainty

This is the more important catch, because it's being used as a ship/no-ship justification. Two problems:

**Pigeonhole issue.** 9 openings mapped onto 8 categories means at least one type repeats no matter what. "Covers 7 of 8" is consistent with, say, 3 hooks all being "curiosity gap," 5 other types getting one hook each, and one type getting zero — which is a lopsided batch, not a diverse one. Coverage (did we touch it, yes/no) says nothing about _distribution_ (how concentrated is the batch). The number that actually tells you about diversity is the count per type, not the count of types touched.

**Sample size kills the stated purpose.** If the point of tagging by type is to _learn_ which psychological mechanism performs best for Halyard Swim's audience, most types here have n=1. You can't attribute a hook's performance to its "type" versus its specific wording, visuals, or placement with a sample of one — any read on "curiosity gap beat social proof" from this batch is noise, not signal. Diversity-for-learning requires replicates per type, not maximum type coverage.

**The missing type deserves more scrutiny, not less.** The framing treats the 1 uncovered type as a rounding error ("7 of 8, good enough"). It might instead be the mechanism best suited to this funnel stage or platform (e.g., authority/proof-based hooks for a considered purchase like swim gear) — omitting it could be the actual gap, and "7/8" makes that easy to wave off.

**Fix:** report the count-per-type table (not just covered/uncovered) alongside the total. If it's skewed, redistribute a couple of the batch's 9 slots toward the underrepresented types before calling the batch diverse.

### Bottom line before rollout

- Don't ship the weighted average as pass/fail on its own — gate on brand timing and promise continuity first, then weight the rest.
- Get written scoring anchors per dimension and a second (blind) scorer, or the 30%/25% dimensions are unreliable.
- Backtest the formula against past hooks with known performance before trusting it prospectively.
- Replace "7 of 8 types covered" with a per-type count; investigate the missing type instead of treating coverage as sufficient proof of diversity.
- Don't expect this batch to teach you which hook type wins — n≈1 per type can't support that conclusion, no matter how the total score comes out.
