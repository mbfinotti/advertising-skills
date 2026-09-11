# LinkedIn Ad Angle Test: CFO Cost-Cutting vs. Automation Time-Saving

## ⚠️ Bottom line first

**The brief as stated is not statistically achievable.** $9k/month split across two arms for 3 weeks gives you ~26 form fills per arm (~52 total). At that sample size, the minimum lift you could detect at 95% confidence / 80% power is a **~120% relative difference** — one angle would need to more than *double* the other's fill rate to register as "significant." Real creative-angle deltas in mature B2B accounts run 10–40%. You will almost certainly end the 3 weeks with a "winner" that is pure noise.

## The math

Two-arm, equal-split, comparing fill-generation rate per dollar spent (Poisson rate-ratio test, α=0.05 two-sided, 80% power):

| Relative lift to detect | Fills needed (total) | Time needed at $9k/mo | OR budget needed to hit it in 3 weeks |
|---|---|---|---|
| 20% | ~945 | 12.6 months | ~$162k/mo (18x) |
| 30% | ~456 | 6.1 months | ~$78k/mo (8.7x) |
| 50% | ~191 | 2.5 months | ~$33k/mo (3.6x) |
| 75% | ~100 | 5.7 weeks | ~$17k/mo (1.9x) |
| 100%+ | ~66 | 3.7 weeks | current budget, ~1 extra week |

**Take this to your CRO as the actual trade-off**: 3 weeks and $9k/month buys you a coin-flip on anything short of a doubling. A realistic, decision-useful read (30% lift) costs either 6x the time or 9x the budget.

## It's worse than the fill-count math alone shows

- At 26 fills/arm, only ~8 SQL-accepted leads/arm (30% rate) — nowhere near enough to say anything about lead *quality* by angle.
- $45k ACV, 4-month cycle: even a clean fill-count winner tells you nothing about which angle produces revenue. You won't know that until ~Q1 2027.
- Optimizing to "form fills" risks rewarding an angle that attracts curious-but-unqualified clickers (a classic CFO-budget-anxiety hook can do this) while looking like a win on the metric you report upward.

## Recommendation: reframe the ask, don't fake the rigor

Don't run a test that produces a false "statistically significant" claim on 3-week noise. Two honest paths — pick one with the CRO:

**Option A — Real test.** Commit ~10 weeks (50% MDE) or ~6 months (30% MDE) at current budget, primary metric = fills, guardrail metric = SQL-accept rate. Report interim directional trend at week 3, label it explicitly as *directional, not significant*.

**Option B — Fast + honest.** Run 3 weeks as a **sequential/interim-look test**, not a fixed 3-week endpoint. Use an always-valid p-value / alpha-spending approach so you can legitimately peek at week 3 without inflating false-positive risk, then keep the clock running past week 3 if inconclusive (expected case) instead of forcing a call. This is the only way to give the CRO a checkpoint at week 3 that isn't statistically dishonest.

**My call: Option B.** It gives leadership a checkpoint on schedule and preserves the option to reach real significance without restarting the test or burning extra budget re-litigating the setup.

## Concrete design to run starting now

1. **Split**: 50/50 budget, $4,500/mo each angle, same LinkedIn objective/bid strategy, same targeting/audience, same landing page — only the ad creative + primary text change.
2. **Randomization**: LinkedIn's own delivery within each campaign; don't manually rotate — keep both live simultaneously to control for day-of-week/seasonality.
3. **Primary metric**: form fills per $1,000 spent (CPL), tracked as a running Poisson rate-ratio test.
4. **Guardrail metric**: SQL-accepted rate per angle — flag (don't auto-kill) if either angle's guardrail drops >10pp below the other, since volume here (~8 SQLs/arm at week 3) is too thin for a hard kill rule.
5. **Decision rule, pre-registered before you look**:
   - Week 3 checkpoint: report the interim rate-ratio and its confidence interval, explicitly labeled "directional — not yet significant" unless it happens to have cleared the ~120% bar.
   - Continue running past week 3 if inconclusive; re-check at 6-week and 10-week marks.
   - Call a winner only when the interim-corrected CI excludes RR=1.
6. **What to tell the CRO now** (short version): *"3 weeks at current budget only catches a >2x difference between angles — not a realistic outcome. I'm running it as a rolling test with a week-3 directional checkpoint, and we'll have an honest, decision-grade read by week 10 unless you want to 3–9x the test budget to compress the timeline."*