# Spend Health Check — Ostrava Systems, Paid channel, April cohort

## Short answer

No — the $30,000 CAC and the comparison to the $239 First Page Sage benchmark are both invalid, for two independent reasons. Don't use either number to decide whether to kill paid before May. What follows is what the numbers _do_ support.

## Headline

- **Paid channel, April lead cohort: insufficient evidence** for a CAC/closed-won verdict — rests on no valid rung. The 1-month window is shorter than the ~4-month sales cycle, which is an explicit evidence-gate trigger regardless of what rung 1/2 would otherwise show.
- **Interim funnel read (CPL, cost/SQL): healthy** — both clear their break-even/context comparators. This is a leading indicator, not a verdict.

## Definitions record

Model: B2B SaaS · Window: April 2026 (single month; sales cycle ~4 months → **window < lag, cohort immature**) · Spend line: paid media + agency ($60,000) — **this is a Paid CAC variant, not blended** (no organic/total marketing spend given) · New customer = closed-won deal — **assumed net-new logo, not renewal/expansion; not confirmed** · Contribution margin: gross margin 75%, used per this skill's B2B convention (allowable CAC = ACV × gross margin) · History: **one summary statistic only** — a historical lead-to-close rate of 1.5%, not a period-by-period paid-CAC/cost-per-SQL series. Rung 2 (4-8 trailing periods, same definition) is not available.

**Named gaps that would unlock a full verdict:**

- Are all 500 April leads paid-attributed, or is this actually a blended figure?
- Do the 2 April closed-won deals exclude renewals/expansions?
- A trailing 4-8 month series of paid CPL and cost-per-SQL, same definition — currently only one aggregate rate exists.
- Cohort tracking by lead-generation month, so April's cohort can be re-measured when it matures (~August, at the ~4-month mark).

## Metric table

| Metric                                                         | Variant                                                         | Value   | Window               | Source                                                      |
| -------------------------------------------------------------- | --------------------------------------------------------------- | ------- | -------------------- | ----------------------------------------------------------- |
| CPL                                                            | paid spend ÷ leads                                              | $120    | April, in-period     | paid platform + CRM                                         |
| Cost per SQL                                                   | paid spend ÷ SQLs                                               | $1,500  | April, in-period     | CRM                                                         |
| Lead→SQL rate                                                  | SQLs ÷ leads                                                    | 8%      | April, in-period     | CRM                                                         |
| In-period "CAC" (invalid, shown for correction)                | paid spend ÷ closed-won _in the same month_                     | $30,000 | April, in-period     | as reported by cofounder                                    |
| Break-even CPL                                                 | ACV × historical lead-to-close (1.5%)                           | $270    | —                    | own economics                                               |
| Allowable CAC (first-year)                                     | ACV × gross margin = $18,000 × 0.75                             | $13,500 | —                    | own economics                                               |
| Projected paid CAC at cohort maturity (estimate, not measured) | paid spend ÷ (leads × historical lead-to-close) = $60,000 ÷ 7.5 | ≈$8,000 | projected to ~August | derived, historical conversion rate applied to April cohort |

## Comparison ladder

1. **Break-even.** CPL $120 sits well under break-even CPL $270 — the top of the April funnel is healthy by arithmetic. The equivalent break-even check for CAC (allowable $13,500) **cannot be run yet**: it needs a closed-won count from *this* cohort, and April's $60,000 hasn't finished buying its outcomes. If the historical 1.5% close rate holds for this cohort, projected CAC (~$8,000) would clear break-even with room to spare — but that's a projection, not rung 1.
2. **Own history.** Only a single aggregate conversion rate (1.5%) is available, not a trailing series of paid CAC or cost-per-SQL on a consistent definition. Direction and volatility — the things rung 2 actually tests — can't be assessed from one number.
3. **External.** The $239 figure is First Page Sage, B2B SaaS, agency client analytics, Jan 2022–Aug 2025, self-disclosed as **75% organic / 25% paid weighted**. It's a *combined* organic+paid number; the same dataset's paid-only figure is $341, not $239. Ostrava's spend is 100% paid. Comparing a paid-only in-period figure to a mostly-organic combined agency benchmark is a variant mismatch on top of the window mismatch — it doesn't tell you anything about Ostrava's paid channel. (Context only, even the corrected $341: same source's cost-per-SQL figure, $1,357, is at least the right variant — Ostrava's $1,500 sits close to it, unremarkable either way.)

## Verdict and evidence gate

Gate: variant established (yes, paid CPL/cost-per-SQL) · margin known (yes, 75% gross margin) · **window ≥ lag: no — 1 month vs ~4-month sales cycle** · trailing history available: no (one summary stat, not a series)

**Verdict: insufficient evidence** for any CAC or closed-won-based judgment this period. The window-shorter-than-sales-cycle condition alone forces this, independent of the other gaps. What's withheld: whether paid is actually profitable, because the 2 deals that closed in April almost certainly came from leads generated ~4 months earlier (around December), not from the $60,000 spent in April. April's spend cohort won't finish closing until roughly August. Dividing this month's spend by this month's closed-won count mixes two unrelated cohorts and produces a number that describes neither — this is the exact failure the skill's own worked example (Quorline) exists to catch, down to the "First Page Sage says X, kill paid" framing.

**What is defensible right now:** CPL ($120) and cost-per-SQL ($1,500) are legitimate interim reads for the April cohort, and CPL clears its break-even ($270) comfortably. That's a leading indicator the top of the funnel isn't the problem — it says nothing about whether those leads convert to revenue at a rate that pays back the spend, which is exactly the open question.

## Handoffs

- Deciding a hard rule for _when_ to pause or scale paid (a CAC ceiling, a kill-switch trigger) is policy, not this check → `mbfinotti/advertising-skills@ad-spend-guardrails`.
- If, once the April cohort matures, the verdict comes back unhealthy and the question becomes _why_ → `mbfinotti/advertising-skills@ad-account-diagnostic`.
- If the decision is to shift budget rather than cut it entirely → `mbfinotti/advertising-skills@ad-spend-allocation`.

## Bottom line for the cofounder conversation

Both anchors behind "kill paid" are broken: the $30,000 figure mixes April's spend with a cohort of leads generated months earlier, and the $239 benchmark measures a different, mostly-organic mix from a different company's clients — even its own paid-only number is $341, not $239. The one thing this data _can_ say is that April's top-of-funnel cost (CPL $120 vs. a $270 break-even) looks fine. The real answer on whether $60,000 in April paid spend was worth it won't exist until that cohort finishes closing, around August. If a decision is needed before then, it has to be made explicitly as a bet under uncertainty, not as a read of numbers that aren't ready yet — and the two figures being waved around currently don't support "catastrophe" any more than they'd support "healthy."
