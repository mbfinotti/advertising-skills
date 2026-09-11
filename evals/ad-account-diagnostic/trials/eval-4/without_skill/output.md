**Bottom line: don't raise the budget 40%. The data says budget isn't the constraint — the drop is an Ad Rank problem, and no budget increase fixes that.**

## The math

Your lost-IS split accounts for the whole gap:

- IS = 54%
- Lost IS (budget) = 4%
- Lost IS (rank) = 42%
- Total = 100% ✓ (consistent)

Of the 46 points of impression share you're losing, **91% (42/46) is rank-based, only 9% (4/46) is budget-based.**

A budget increase can only ever recover the budget-capped slice. Best case, fully fixing budget constraints takes you from 54% → **58%** IS. That's the ceiling — not 71%, not close to it. A 40% spend increase, or a 400% one, cannot touch the 42-point rank loss. Money doesn't buy Ad Rank; bid × Quality Score (expected CTR, ad relevance, landing page experience) does.

## The "11 of 30 days" detail matters more than it looks

If budget were truly the bottleneck, you'd expect to be capped almost every day. Instead, on 37% of days you *aren't even spending the current budget* — meaning on more than a third of days, demand/eligibility doesn't fill what you already have. That's a second independent signal pointing away from "we're outspent" and toward "we're losing auctions on rank even when budget isn't the limiter."

## What's actually happening

Stable CPA ($58) + ballooning Lost IS (rank) is the classic signature of one of these:

1. **Competitors raised bids/quality aggressively** — check Auction Insights over the same 6 weeks for overlap rate and top-of-page rate shifts among competitors. This is the most likely story given a 6-week timeframe.
2. **Automated bidding (tCPA/tROAS/Max Conv) is holding you back defensively** — if the algorithm sees CPA at risk from rising competitor bids, it protects your $58 target by bidding lower/less often, which shows up exactly as rank-based lost IS with flat CPA. Your stable CPA might be stable *because* the bidding system is sacrificing volume to defend it, not despite competition.
3. **Quality Score erosion** — expected CTR, ad relevance, or landing page experience degraded (seasonality in ad copy, LP changes, mobile speed, etc.), raising the bid needed to win the same rank.

## Recommendation

1. **Pull Auction Insights** for the 6-week window — see who gained impression share/overlap rate against you. This will confirm or rule out competitive bid pressure.
2. **Check bid strategy** — if on tCPA/tROAS, look at whether the target is suppressing impressions; consider loosening the CPA target modestly (not the budget) and watching IS response.
3. **Audit Quality Score components** on your top-spend keywords — expected CTR and ad relevance first.
4. **Size any budget increase to ~4–8%**, not 40% — enough to close the actual budget-capped gap (with some margin), sized against the fact that 11/30 days already show slack.
5. **Re-pull lost IS (budget) after the bid/QS fixes**, not before — if you raise budget now while rank is the real problem, you'll likely just spend more on the same rank-limited traffic without recovering IS proportionally, which is the fastest way to make CPA look worse next quarter and hand your boss a "the budget increase didn't work" result that wasn't actually a budget problem to begin with.

Reframe for your boss: **"We're not being outspent on the budget line — we're losing on Ad Rank. A 40% budget increase would fix at most 4 of the 17 points we lost. Let me pull Auction Insights first to show where the other 13+ points are actually going."**