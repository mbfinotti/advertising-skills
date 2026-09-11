# Auto-Kill Rule — Underperforming Paid Channels

## Why this needs a different shape than "3x CPA for 3 days"

True CPA (spend ÷ closed-won deals) lags spend by ~75 days — your sales cycle. A 3-day CPA reading isn't CPA, it's noise; you'd be measuring deals that closed from spend placed months ago. The fix isn't to abandon the CMO's instinct — it's to run the rule on a leading proxy (Cost per SQL) translated into an *implied* CPA, so you catch the LinkedIn-style spike in days, not quarters.

## Definitions

1. **Target CPA** — fully-loaded cost to acquire one customer, sized to your LTV:CAC target. Record the number here explicitly: `[Target CPA = $____]`, owner: Finance/RevOps.
2. **SQL→Won rate** — trailing 90-day conversion rate from SQL to closed-won. Recompute quarterly; a stale rate silently breaks the whole rule.
3. **CPSQL (cohort)** — spend ÷ SQLs, matched by *spend date cohort*, not same-day count. Leads convert to SQL over 1–3 weeks; same-day ratios punish yesterday's spend for pipeline that hasn't landed yet.
4. **Implied CPA** = CPSQL (cohort) ÷ SQL→Won rate.

## Trigger condition

1. Compute a **trailing 3-day rolling CPSQL** per channel: `sum(spend, last 3 days) ÷ sum(SQLs from that spend cohort)`. Use a rolling window, not three individually-bad calendar days — daily SQL counts on one channel are low enough that weekends alone can fake a breach.
2. Convert to Implied CPA.
3. Fire only if **both**:
   - Implied CPA > 3× Target CPA
   - Trailing 3-day SQL count ≥ `[floor, e.g. 5]` — below this, one lost SQL swings CPA by 100%+; that's sample noise, not a decision.
4. Require the breach to hold across 3 consecutive rolling checks (day 1, 2, 3 of the rolling average, not 3 isolated daily spikes).

## Action on trigger

1. **Auto-pause** the channel (spend → $0). Not a kill — pausing is reversible in minutes; "shut off" implies teardown you may regret.
2. **Auto-notify** the on-call owner within 1 hour, with the CPSQL trend, spend, and SQL count that caused the trigger.
3. **Human review within 1 business day**: rule out tracking bugs, attribution gaps, or platform outages before treating it as real degradation.
4. **Only a human marks it permanently killed.** Automation's job is to stop the bleeding fast — not to make the budget-cut call unsupervised.

## Reactivation

1. Stay paused until root cause is documented (targeting drift, creative fatigue, auction/CPM shift, tracking break).
2. Reinstate at 25–50% of prior budget for a probation period before returning to full spend.

## Scope

Run this at **channel and campaign level** within LinkedIn, not just channel-blended — a single bad campaign can drag a healthy channel's blended number past 3x and get the whole channel killed for one offender's sake.

## Ownership

- **Rule owner** (sets Target CPA, SQL→Won rate): CMO / Growth lead
- **On-call reviewer** (responds to pause alerts): `[name/rotation]`
- **Review cadence**: revisit thresholds, floor, and SQL→Won rate quarterly, or immediately after any change to your SQL definition.

## Worked example (illustrative — confirm inputs with Finance)

- ACV $24,000 × 62% gross margin = $14,880 gross profit per deal.
- At an illustrative 3:1 LTV:CAC on that single-deal profit: Target CPA ≈ $14,880 ÷ 3 ≈ **$4,960**.
- This ignores renewals/expansion, which you should fold in once you have churn data — treat it as a placeholder, not the number to ship.
- 3x kill threshold on that placeholder ≈ **$14,880 implied CPA**.
- If your SQL→Won rate is, say, 20%, the equivalent CPSQL kill line is **$14,880 × 20% = $2,976** cohort-CPSQL sustained over a rolling 3-day window with ≥5 SQLs in that window.