Neither. Open a ticket and you'll get told exactly what's below, and switching to Bid Cap reactively off three data points is a bigger, riskier move than the problem calls for.

## What's actually happening

"Cost Per Result Goal" on Meta (this setting was literally called **Cost Cap** until the rename) is an **average-based cost goal**, not a hard per-result ceiling. Meta's own bidder is explicitly allowed to let individual auctions cost more than your target as long as the *campaign average* lands near it. A hard per-auction ceiling that never bids above $28 on any single result is a *different* tool — Meta calls that one **Bid Cap**.

Your numbers confirm the strategy is doing what it's designed to do, not malfunctioning:

- Goal: $28
- Campaign average after 3 weeks: **$29.50** — about 5% over target, which is normal noise for an average-control strategy, not a breach.
- The $47 and $63 purchases are individual auctions where competition was higher that day — expected under an average-based control, especially in a DTC candle account where auction pressure swings with time of day, day of week, and who else is bidding on similar audiences.

The confusion "my cost cap was exceeded on this conversion" is common enough that it's a documented misreading, not an edge case — people hear "cap" in the setting's old name and expect a ceiling, but average-based and hard-ceiling are genuinely different mechanisms wearing similar-sounding labels.

## Why a support ticket won't help

There's nothing to report. Meta support will tell you the same thing: the campaign is meeting its target on average, which is the contract of this bidding archetype. You'd be spending a ticket to confirm the setting is working as specified.

## Why Bid Cap isn't the fix, at least not yet

Switching to Bid Cap *would* stop any individual purchase from costing more than $28 — that's the honest trade a hard ceiling gives you. But it's not a free correction to "make Meta respect the number," it's a **different archetype with its own costs**:

- Hard ceilings carry the highest under-delivery risk of any bidding mode — Meta positions Bid Cap as expert-only for exactly this reason. If the auction clears above $28 for a chunk of your audience, the bidder simply won't compete for those results, and volume can drop sharply rather than cost coming down cleanly.
- It's a real bid-strategy change, not a tweak: it restarts the campaign's learning phase, and you'd want at least 1-2 full conversion cycles of clean data afterward before judging it — with a fast e-commerce purchase lag that's probably days, not weeks, but it's still a deliberate evaluation window, not a snap verdict.
- It should be evaluated against your own trailing purchase volume at that price point, not decided from three outlier line items. If $28 is near or below what the account has actually been clearing, a hard ceiling can choke delivery close to zero.

## What I'd actually do

1. **Leave the bidding archetype alone.** Average $29.50 against a $28 goal, three weeks in, is the strategy working within its normal variance band — not a failure state.
2. **Watch the trend, not the outliers.** Track the trailing average weekly. If it holds near $28-30, that's healthy. If it keeps climbing with no seasonal or promotional explanation, that's the actual signal to act — and the fix is upstream of the bidder (creative fatigue, audience saturation, rising competition in your niche), not a different bid setting. Bid strategy is a late lever; it rarely fixes a cost problem whose root cause is elsewhere.
3. **If you genuinely want a hard ceiling anyway** — because volume matters less to you than never seeing a $47 purchase again — treat it as a deliberate archetype switch: check your trailing purchase volume can support $28 as a real per-auction ceiling (not just an average), use Meta's A/B test tool to read the switch cleanly instead of a blind cutover, and set a rollback trigger (e.g., "revert if purchase volume drops X% and stays down for a full evaluation window") before you flip it.