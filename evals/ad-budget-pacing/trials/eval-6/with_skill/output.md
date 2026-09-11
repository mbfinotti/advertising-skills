# Bexley Home — October Paid Social Pacing Check

**Header** — Bexley Home paid social · check date Oct 25 · period Oct 1–31 (31 days) · budget $40,000, hard commitment · buy type: auction-bought media under an agency spend commitment (not a guaranteed IO) · curve model: flat (no day-of-week/seasonality history given — see note below)

## The arithmetic (flat curve)

| Metric | Formula | Value |
|---|---|---|
| Days elapsed / in period | 25 / 31 | 0.806 (80.6%) |
| `expected_to_date` | $40,000 × 0.806 | **$32,258** |
| `spend_to_date` | given | $26,000 |
| `pacing_ratio` | 26,000 / 32,258 | **0.806** (actual/expected) |
| `budget_utilization` | 26,000 / 40,000 | 65.0% |
| `remaining_budget` | 40,000 − 26,000 | $14,000 |
| `projected_spend` (run rate) | (26,000/25) × 31 | **$32,240** |
| Days remaining | Oct 26–31 | 6 |
| `required_daily` | 14,000 / 6 | **$2,333.33/day** |
| `adjust_spend_by` | 2,333.33 − 1,050 (trailing 7‑day avg) | **+$1,283.33/day** |

*Weighted curve: not computed. No day-of-week or seasonality history was given, and there's no time to build/validate a 2–3 cycle index before a same-week correction — flat alone is the right call here per the skill's own guidance (a deadline inside the period demotes the weighted curve).*

## Status: **UNDER-PACING, urgent band**

0.806 is below the 0.85 urgent-band floor (practitioner convention, not a platform rule). This isn't a rounding artifact — 65% of budget spent at 80.6% of the period elapsed is a real, material gap.

## Gate check: not suppressed

- Not a single lumpy day — this is a 25-day cumulative read.
- Not a first/last partial day.
- Denominator (25 elapsed days) isn't trivial.
- Period isn't too young — 25/31 days in is mature.
- No recent budget edit mentioned that would put you in a relearning window (this correction hasn't been applied yet).
- One caveat: confirm the $26,000 is finalized/restated spend, not a live dashboard number reading mid-day — reconcile before you commit to the daily figure tomorrow.

This deviation is real and worth acting on.

## Sanity-check on your plan

**Your math is off by ~$400.** $2,400/day × 6 days = $14,400, plus the $26,000 already spent = **$40,400 — $400 (1%) over the $40,000 commitment**, not "almost exactly on $40k."

The number that lands exactly on budget is `required_daily` = **$2,333.33/day**, not $2,400. Small gap, but at a hard-commitment client budget it's worth using the exact figure rather than a rounded one, especially since you'll be recomputing daily anyway (see below).

**The bigger issue isn't the $67/day rounding error — it's the jump itself.** $2,333/day is a **+122% increase** over your trailing 7-day average of $1,050/day. That's not a tweak, it's a step-change, and it creates two real risks:

1. **Relearning-window volatility.** A change of this magnitude is exactly what platforms' delivery systems treat as a significant edit — expect a settle period where delivery is unstable, which eats into the very days you need to close the gap. (Note: the popular "20% budget change resets Meta's learning" figure is folklore, not documented policy — but "large edits risk relearning" is real and undocumented magnitude doesn't mean no risk, it means untested risk.)
2. **You don't yet know if the account can even absorb it.** A trailing pace of $1,050/day sitting at 81% of the flat-curve daily expectation ($1,290/day) could mean several different things, each with a different fix:
   - **Budget-capped** → raising the daily budget is the right lever and will work.
   - **Bid-capped / audience too small / frequency-capped** → raising the daily number alone won't move actual spend; the account simply can't absorb $2,333/day and the shortfall persists no matter what you set the budget to.

You haven't given me platform status data, an edit log, or the impression-share-lost breakdown, so I can't tell you which of these it is — but this is the single highest-value check on the list before you touch the budget tomorrow, and it's near-zero effort:

- **Status sweep** (one screen, each platform): budget-limited vs. learning-limited vs. rank-limited delivery status, any billing issues, any disapprovals.
- **Constraint pair**: impression share lost to *budget* (money's the constraint — raising it works) vs. lost to *rank* (bid/targeting's the constraint — raising budget alone won't close the gap).

If any platform comes back bid- or rank-limited, the fix is loosening that constraint first, not just inflating the budget number — otherwise you'll set $2,333/day, it under-delivers again, and you're back here on Oct 29 with less runway and a bigger last-mile scramble.

## Recommendation (change packet)

| | |
|---|---|
| **Current** | ~$1,050/day (trailing 7-day average across active paid social budgets) |
| **Proposed** | $2,333/day for Oct 26–31, **recomputed daily** rather than set once — recalculate `required_daily` each morning against actual finalized spend from the prior day |
| **Affected objects** | All active Bexley Home paid social campaigns/ad sets carrying October budget — reallocate toward whichever objects the constraint-pair check shows have room, rather than applying a flat +122% to every object uniformly (a uniform lift risks some objects hitting fair-share delivery limits while others merely convert overspend into worse CPMs) |
| **Rationale** | Closes the $14,000 remaining gap exactly over 6 remaining days; current trailing pace projects to $32,240 — a $7,760 shortfall against the $40,000 hard commitment |
| **Expected effect, with uncertainty** | Lands exactly on $40,000 utilization **if** delivery isn't itself the binding constraint. Unconfirmed until the status sweep / constraint-pair check runs — this is the load-bearing unknown in the plan |
| **Owner** | Bexley Home media buyer / account manager |
| **Verification date** | Daily, Oct 27–30 — recheck `pacing_ratio` and `required_daily` against actual (not projected) spend each morning |
| **Rollback trigger** | If actual delivery underdelivers the new daily target for 2 consecutive days, stop pushing the number up further — that's the signature of a delivery constraint, not a budget-setting problem, and needs the constraint-pair fix instead |

## One more thing on execution

Since it's a hard commitment, hitting $40,000 isn't optional either way — but *how* you get there still matters to the client relationship. A single overnight cliff to $2,333/day, held flat for 6 days regardless of what's actually delivering, is the textbook end-of-period spend dump: it tends to buy the worst inventory at the worst prices in the campaign's final stretch. Recomputing daily (as above) keeps the correction continuous instead of letting any shortfall pile into the last 1–2 days, which is the point in the flight with the least room left to recover from a bad one.