# Brightpath Legal — Google Ads Search Pacing Report

**Short answer: no, don't raise the daily budget to $1,100.** Your impression-share data already tells you budget isn't what's holding you back — Rank is. Raising the cap adds unused headroom on top of headroom you're already not using.

---

## The gate check first

Before trusting the "behind" read at all:

| Gate check | Result |
|---|---|
| 1. Single-day overdelivery allowance | N/A — this is a cumulative 18-day read, not a single day vs. daily cap |
| 2. First/last partial day | No — day 18 of 30 |
| 3. Trivial denominator | No — 18 elapsed days is a real sample |
| 4. Too young to read | No — account has run since spring, well past any cold-start window |
| 5. Inside a post-edit relearning window | No — nothing touched in 2+ weeks |
| 6. Intra-day / unrestated figures | No — you're reading yesterday's finalized numbers |

**Passes all six. This is a real deviation, worth acting on — not noise.**

## The arithmetic

Calendar month, Sept 1–30 (30 days), day 18 elapsed, 12 remaining.

| Metric | Flat curve | Weighted curve |
|---|---|---|
| Expected to date | $14,400 | $14,400 |
| Spend to date | $10,800 | $10,800 |
| Pacing ratio | **0.75** | **0.75** |
| Budget utilization | 45% | 45% |
| Projected period spend | $18,000 | $18,000 |
| Remaining budget | $13,200 | $13,200 |
| Required daily (remaining) | $1,100 | $1,100 |
| Trailing 7-day avg | $560 | $560 |
| **Adjust spend by** | **+$540/day** | **+$540/day** |

The two curves converge here — no daily reweighting needed. Normally a B2B account gets paced on business days (weekday skew), but you've told me delivery is empirically even across weekday/weekend with no seasonality over a full spring-to-fall history, so the flat calendar-day curve isn't an approximation error in this case — it's confirmed by the account's own delivery shape.

**Status: UNDER-PACING, urgent.** 0.75 sits below the 0.85 urgent-band floor (0.90–1.10 is on-pace, both bands practitioner convention, not a platform rule — recalibrate against this account's own history rather than trusting the default).

**Suppression: none.** Gate passed clean (see above).

## Diagnosis — this is the part that changes your answer

Here's the trap in "raise $800 → $1,100": that $1,100 required-daily figure is *arithmetically* correct — it's what you'd need to spend, on average, over the next 12 days to land on $24,000. But **required_daily is a spend target, not a budget-cap recommendation.** Whether raising the cap actually produces that spend depends entirely on what's constraining delivery today, and your own numbers already answer that:

- **Impression share lost to rank: 38%** — high
- **Impression share lost to budget: 2%** — low

That's the single highest-value check in the whole diagnostic (it's the only one that separates bid-side from budget-side), and it points squarely at **bid-capped / target too tight**, not budget-capped. Corroborating evidence: your trailing 7-day average ($560) is already **30% under the existing $800 cap**. You're not exhausting the budget you have — the auction is shutting you out before you get the chance to spend it. A $300 bump to that cap just raises a ceiling nothing is hitting.

The edit-log answer ("nobody's touched settings in 2+ weeks") also rules out relearning-window volatility and conflicting-controller oscillation as the cause — this is a steady-state read, not edit noise.

## What to change instead

Ranked by the skill's remedy order — fix the binding constraint before inflating total spend:

1. **Pull the bidding strategy.** If it's Target CPA/ROAS, the target is very likely set tighter than the current auction will clear at — loosen it a modest step (~10%), one variable, and let it resettle before judging (an edit itself triggers a relearning window, so don't stack this with anything else). If it's manual/Max CPC, check whether your bid caps sit below what's needed to clear Ad Rank on your priority keywords.
2. **Check Quality Score components** (expected CTR, ad relevance, landing page experience) on the keywords driving the rank loss. Ad Rank is bid × quality × auction-time factors — if QS is the drag, a bid increase alone won't fully close 38%, and the fix is creative/landing-page, not budget.
3. **If 1–2 don't fully explain it, run the auction-cost read**: has CPC/CPM trended up across the flight with no edit on your side? That would point to a new competitor entering the auction rather than anything wrong on the account — a market move, not a setting to fix.

**Only after that fix lands and holds a few days** — recheck lost-to-budget. If it starts climbing as delivery improves, *that's* the trigger to raise the cap, and even then, step it modestly (e.g. toward $900–950) rather than jumping straight to $1,100 — the smallest reversible change, not the number the shortfall math happened to produce.

One more thing worth naming explicitly: this is a **target, not a hard commitment**, on **auction-bought performance media**. Under-utilizing $24k isn't inherently a problem here — efficiency outranks utilization on a target budget. The real finding isn't "you're $3,600 short of the goal," it's "you're being priced/quality-scored out of auctions you'd otherwise win," which is a lead-volume problem worth fixing on its own merits — not something a budget-cap edit touches. And whatever you do, don't let the last 12 days turn into a spend dump to hit $24k on the nose — that buys the worst inventory at the worst prices and is the specific failure mode this kind of pacing gap invites.

## Change packet

| | |
|---|---|
| **Current → proposed** | Daily budget stays $800 (not the constraint); Target CPA/ROAS or Max CPC loosened ~10% (pending strategy check) |
| **Affected objects** | The campaign's bid strategy / bid settings — not the daily budget field |
| **Rationale** | Lost-to-rank 38% vs. lost-to-budget 2%; trailing spend already 30% under existing cap |
| **Expected effect** | Delivery should climb toward the $800 cap before that cap itself becomes binding; uncertain how much of the 38% is bid vs. QS until step 2 is checked |
| **Owner** | You (paid search lead) |
| **Verification date** | 3–5 days after the bid change settles, before judging |
| **Rollback trigger** | CPL rises materially with no lift in delivery — revert the target change |

**Next check:** tomorrow's daily pacing review, recomputing `required_daily` / `adjust_spend_by` against fresh finalized numbers rather than waiting for another mid-month checkpoint — small daily corrections beat one large one at the end.