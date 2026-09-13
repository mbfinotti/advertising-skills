## The math finance is missing

- Expected value per demo = 4% × $3,500 = **$140**. That's breakeven — the most you can pay per demo without losing money on it.
- Trailing 60-day actual: $240/demo → losing ~$100 per demo.
- Best month _ever_: $210/demo → still losing money, even at your historical peak.
- New target: $95/demo → **32% below breakeven**, and **55% below the best result you've ever produced**, from a channel that has apparently never once beaten breakeven.

So $95 isn't an optimization target, it's a number nobody has evidence the channel can hit. That's the root cause of everything downstream.

## Why the "beautiful $102 CPA" is fake evidence

Target CPA bidding algorithms don't find $95 demos — they throttle. When you drop the target that far below historical performance, the algorithm stops bidding on almost all auctions it previously won, because it predicts most of them won't clear $95. What's left is a handful of the cheapest, easiest, most-likely-to-convert impressions — not a repeatable $95 audience, a sliver of the distribution's left tail.

The $102 you're seeing is:

- **A tiny sample** — near-zero spend means single-digit or low-double-digit conversions. Standard error at that volume is enormous; $102 could easily swing to $180+ with three more data points.
- **Survivorship-biased** — it's the cheapest fraction of what used to be a much bigger, more representative pool.
- **Possibly conversion-lag-inflated** — recent conversions often haven't fully attributed yet, making very recent CPA look artificially good regardless of target.

Finance is reading noise from a starved algorithm as if it were a stable new equilibrium. It isn't one — it's what a bidding system does right before volume goes to zero.

## What to actually do

1. **Revert the target now.** Every day at near-zero spend is demo volume — and future pipeline — that doesn't come back. Go back to $240, or whatever the last stable target was, to stop the bleeding while you fix the plan.
2. **Never move a tCPA target 60%+ in one step.** Platform guidance (Google/Meta) is ~10–20% per change, then a full learning period (roughly 2 weeks or ~50 conversions) before the next move. A cliff-edge cut is what caused the collapse.
3. **Set the real target using the unit economics, not a finance guess.** Breakeven is $140. A sane target is below that with a margin buffer — something like $110–125 — not a number nobody has ever hit.
4. **Question whether the channel is viable at all before optimizing further.** If $210 is the best month on record and breakeven is $140, this channel has never been profitable on contribution alone. Before chasing a lower CPA, figure out if that gap is closable (landing page, targeting, offer, sales follow-up speed) or if search just isn't a profitable acquisition channel at your current price/conversion economics — in which case the conversation with finance should be about the channel, not the bid.
5. **Watch conversion quality, not just cost.** Aggressive CPA cuts often "succeed" by buying worse leads that convert below 4%. If you tighten CPA, track downstream demo→close rate for a full sales cycle before declaring a win — a cheaper demo that converts at 2% instead of 4% is worse, not better.
6. **Reframe the metric for finance.** Sell them on a CPA ceiling ($125, say) *plus* a volume floor. A target CPA with collapsed volume isn't a plan — you need enough demos for the 4% × $3,500 math to hold at scale, not a boutique trickle of lucky auctions.

**Bottom line:** revert the target today, set the next one relative to your actual $140 breakeven and $210 historical ceiling — not a number pulled from thin air — and step down gradually with real volume at each stage. The $102 CPA is not a result; it's what an algorithm looks like right before it stops finding anyone to bid on.
