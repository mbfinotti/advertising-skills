# ROOT-CAUSE VERDICT — Brightside HVAC (Search), 2026-09-12

```
platform(s)    : Search | model: B2C/local-services (lead gen)
window         : trailing 6 weeks vs prior baseline (lag maturity: not confirmed)
volume         : spend/conversion counts not supplied | reconciliation gap: unverified

decomposition  : Volume down (IS 71%→54%), efficiency stable (CPA flat at $58)
                 → "volume down, efficiency stable" pattern → bidding/budget layer, lost-IS split
localisation   : lost IS decomposes to rank 42 / budget 4 (sums to the full 46-point loss:
                 100 - 54 = 46 = 42 + 4) — loss is concentrated in rank, not budget

layer screen
  measurement/tracking : unknown - no reconciliation data supplied                    [n/a, low]
  structure             : unknown - no campaign/ad-group breakdown supplied            [n/a, low]
  targeting              : unknown - no audience/keyword breakdown supplied            [n/a, low]
  creative                : unknown - no CTR/QS component data supplied                [n/a, low]
  bidding/budget         : FAIL - lost-to-rank (42) is 91% of total lost IS,
                            lost-to-budget (4) is 9%; 11/30 days underspend the
                            daily budget while rank loss is the dominant driver     [high sev, medium-high conf]
  offer & downstream      : pass (leading) - CPA flat implies no CVR collapse           [n/a, medium]
  external                : unknown - no auction-insight/competitor data supplied     [n/a, low]

confidence     : medium - the budget-vs-rank arithmetic is internally consistent and
                 sufficient to answer the budget-sizing question; a full account
                 verdict needs the missing layers above
verdict        : the account is rank-constrained, not budget-constrained. Budget is not
                 the failing link - Ad Rank (bid × Quality Score) is.
evidence       : (1) lost-to-rank (42) outweighs lost-to-budget (4) by ~10:1, both against
                 Workshop Digital's decision rule (>50% to one side names the constraint);
                 (2) the account fails to spend its full daily budget on 11 of 30 days -
                 a budget-capped account does not leave money unspent more than a third
                 of the time; (3) CPA holding flat at $58 rules out a "burned budget for
                 worse traffic" story
prediction     : a 40% (or any) budget increase moves search IS by at most ~4 points,
                 and probably less at the margin - it cannot touch the 42-point rank loss
handoff        : mbfinotti/advertising-skills@ad-bidding-strategy (rank/bid fix),
                 mbfinotti/advertising-skills@ad-budget-pacing (confirm the underspend days
                 aren't a separate pacing bug)
re-check       : one full lag-mature window (4-6 weeks) after the bid/rank fix ships
```

## Direct answer

Don't raise the budget — not 40%, not higher. Your boss's diagnosis ("we're being outspent") may be half right, but his prescription is the wrong tool for it.

Here's why the numbers say that, not just a stylistic call: **lost impression share splits into two causes with opposite fixes** — lost-to-budget (delivery stopped because the daily cap ran out) and lost-to-rank (delivery lost the auction on bid × Quality Score, independent of how much money is sitting in the account). Yours is:

- Lost IS (budget): 4 points
- Lost IS (rank): 42 points

That's a ~91/9 split toward rank. The practitioner rule of thumb here is that whichever side clears 50% of the total loss names the constraint — 42 clears it ten times over. More budget can only ever reclaim the 4-point side. It does nothing for the 42-point side, because that impression was never available to you at your current bid/quality position, regardless of daily cap.

Your own data corroborates this independently: **you failed to spend the full daily budget on 11 of the last 30 days.** If the account were genuinely budget-capped, it would burn through the daily budget on nearly every day — money wouldn't be left on the table more than a third of the time. This is the signature of an account that runs out of rank-competitive auctions to bid into before it runs out of dollars, not the other way around. Raising the budget on an account that already isn't spending what it has doesn't buy more impressions; it just raises the ceiling on a tap that isn't the one that's closed.

CPA holding flat at $58 while all this happened also rules out a messier explanation — you're not paying more per conversion for worse traffic, so this isn't a demand-side or landing-page story either. It's cleanly localized to the auction itself.

**So the real question isn't "how much more budget" — it's "why did Ad Rank fall."** Ad Rank = max CPC bid × Quality Score components (expected CTR, ad relevance, landing page experience). Something in that equation moved over the six weeks: a competitor raised bids or improved their own Quality Score, your Quality Score component degraded (ad relevance/expected CTR/LP experience), or your effective bids didn't keep pace in a hotter auction. Any of those reads as "being outspent" from the outside, but the fix is bid/rank-side, not a bigger wallet.

## What to do instead, in order

1. **Pull Quality Score and its three components (expected CTR, ad relevance, landing page experience) per campaign/ad group, compared to six weeks ago.** This localizes whether the rank loss is a bid problem or a quality problem — they have different fixes and this data wasn't in what you pulled.
2. **Pull Auction Insights for the same window.** If competitors' impression share and overlap rate rose while yours fell, that confirms the "outsp­ent" story — but the counter is competitive bidding/rank strategy, not budget.
3. **If Quality Score is intact and it's a straight bid war:** raise max CPC bids (or move to a more aggressive bid strategy) on the specific campaigns/ad groups carrying the rank loss — a targeted bid change, not a blanket daily-budget increase. This is the mechanism that actually touches lost-to-rank; increasing the budget cap does not.
4. **Separately, get someone to check why 11/30 days underspend even the current budget.** That's its own finding worth confirming isn't a pacing/scheduling bug sitting on top of the rank story — don't let a real bug hide behind the rank narrative.
5. Only revisit a genuine budget increase once lost-to-budget itself is a large share of the loss (it isn't, at 4 points) — at that point Impression Share Lost (Budget) and full daily-budget utilization on the days in question are the metrics that justify it, not the topline IS trend.

## What would sharpen this further

To turn this into a full high-confidence verdict rather than a targeted answer to your budget question, get: the edit log (any bid/budget/QS/landing-page changes in the last six weeks, dated), the historical lost-IS split from six weeks ago (to confirm the 42-point rank loss is what actually opened up, versus already being partly present), and conversion volume for the window (to clear the Evidence Gate on the CPA-stability read). None of those change the budget-sizing answer above — the internal arithmetic (4 + 42 = 46 = 100 − 54) and the 11/30 underspend already settle that — but they'd settle *why* rank fell, which is the fix your boss actually needs funded.