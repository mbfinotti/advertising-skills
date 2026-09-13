## Ferrostat Systems — LinkedIn Lead-Gen Pacing Check, Monday Sep 14

**Header** — Campaign: Ferrostat Systems LinkedIn lead-gen | Check date: Mon Sep 14, 2026 | Period: calendar month, Sep 1–30 | Budget: $18,000 | Buy type: auction-bought (assumed — confirm it's not a hard IO commitment) | B2B, weekday-skewed delivery, 3 months of history available

Your 14% number is real, but it's the wrong curve. Here's both.

### Metrics: flat vs. weighted (business-day) curve

|                             | Flat (calendar-day)     | Weighted (business-day)              |
| --------------------------- | ----------------------- | ------------------------------------ |
| Elapsed share               | 13/30 days = 43.3%      | 9/22 weekdays = 40.9%                |
| Expected to date            | $7,800.00               | $7,363.64                            |
| **Pacing ratio**            | **0.859 (85.9%)**       | **0.910 (91.0%)**                    |
| Budget utilization          | 37.2%                   | —                                    |
| Projected month-end spend   | $15,461.54              | —                                    |
| Remaining budget            | $11,300 (both)          |                                      |
| Required daily to close gap | $664.71/calendar day    | $869.23/weekday                      |
| **`adjust_spend_by`**       | **+$54.71/day (+9.0%)** | **+~$15/weekday (+1.8%), estimated** |

The 14% figure is `1 − 0.859`, computed against a flat calendar-day curve. That curve assumes every day of the month is worth the same, which is false for an account that "delivers almost entirely on weekdays" — every Monday looks artificially behind on it, purely mechanically. Re-run on business days (skill's standard B2B convention) and the ratio lifts to 91.0%, right at the bottom edge of the normal 0.90–1.10 on-pace band. That's a 5.1pp gap between the two curves — real, but under the 10pp bar that would make it a slam dunk, so treat this as "on pace, no headroom" rather than a comfortable green.

The weekday-only `adjust_spend_by` is an estimate: I inferred your weekday spend rate from the trailing 7-day average ($610/day blended across Sep 7–13, which happens to be a clean 5-weekday/2-weekend week) — $610 × 7/5 ≈ $854/weekday actual rate, against $869/weekday required. That's a ~$15/weekday gap, effectively noise. If you can pull the actual weekday-only spend export, that would replace the estimate with a real number, but it won't change the conclusion by much.

### False-alarm gate

| Check                                  | Result                                                                                                                                                                                                                                                     |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Cumulative vs. single-day allowance    | Judged cumulative — clean                                                                                                                                                                                                                                  |
| First/last partial day                 | Not applicable, mid-flight                                                                                                                                                                                                                                 |
| Trivial denominator                    | 13 days / 9 weekdays elapsed — not trivial, ratio is meaningful                                                                                                                                                                                            |
| Period too young to read               | Spend pacing: fine. **Lead count: fails this check** — see below                                                                                                                                                                                           |
| Recent budget edit / relearning window | Unconfirmed — you didn't mention one; ask before trusting today's number if one happened this week                                                                                                                                                         |
| Intra-day / unrestated figures         | Clean — you gave me Sunday's _finalized_ spend, not today's live number, which is correct. Note LinkedIn's day boundary is midnight UTC, not your local reporting day — worth confirming your $6,700 was pulled on that boundary if precision matters here |

### Status

**ON PACE (borderline) — no alert fires.** The weighted ratio (0.910) sits just inside the band; the estimated required correction (~$15–55/weekday depending on which curve) is small enough that it's within normal day-to-day variance, not a deviation worth reacting to. Because nothing crossed the alert threshold, the full 6-step diagnostic triage (status sweep, edit log, constraint pair, etc.) isn't warranted today — that machinery is for confirmed deviations, and you don't have one.

### On the 4 leads vs. 25-lead plan

Don't read this number yet — it fails gate check 4 (too young to read), specifically the B2B form of it: **pace against the spend trajectory, never against period-to-date conversions, since they're incomplete by construction.** With a ~3-week reporting lag on a 30-day month, you're only 14 days in — most of what will eventually report as "September leads" hasn't had time to surface yet, and the leads generated in roughly the back two-thirds of the month won't be visible in this count even by month-end. 4-vs-25 right now tells you almost nothing about whether the campaign is actually converting. Don't scale bids to chase this number; it'll still look thin next Monday even if everything is working.

### Recommendation

**Don't push bids up today.** Three reasons stack against it:

1. Properly measured, you're not meaningfully behind — the "14% behind" read is a flat-curve artifact.
2. The corrective amount, even taken at face value, is small ($15–55/weekday) — not something that justifies a bid move; raising bids to close a gap this size is the textbook "chasing pacing at the expense of efficiency" failure mode the skill warns against, and it tends to buy worse leads at higher CPL for no real pacing benefit.
3. The lead shortfall can't be diagnosed yet — reacting to it now risks a bid increase justified by a number that was never going to look good this early, regardless of true performance.

**What to actually do:**

- Hold current bids and budget.
- Recompute `adjust_spend_by` daily rather than reacting to today's snapshot — this keeps any real correction small and continuous instead of piling into a late-month scramble.
- Since this is a recurring Monday check-in and you have 3 full months of history (2–3 cycles), it's worth building the account's actual day-of-week weighted index rather than leaning on the business-day approximation used here — that closes the 5.1pp gap with a real number instead of an estimate. I can build that from your daily spend export if you pull it.
- Revisit the lead count in ~3 weeks (once the lag window clears September's early/mid-month leads) rather than week over week. A cleaner checkpoint: look again after Sep 21 for spend pacing, and don't judge lead volume with real confidence until early-to-mid October.
- Flag as open: confirm whether the $18,000 is a hard commitment or an efficiency target (changes whether under-pacing would even matter), and whether any budget edit landed in the last week (would explain volatility separately from all of the above).

**Owner:** whoever runs the daily check on this account (performance marketer / growth lead per your setup) — no handoff needed, since nothing here requires a platform-side diagnostic or a change to execute.
