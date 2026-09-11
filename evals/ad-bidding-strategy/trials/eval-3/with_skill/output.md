## Diagnosis: this is textbook delivery choke, not a working target

Run the diagnostic before touching anything else: **"Target too aggressive → delivery choke"** — under-delivery (spend near zero), not genuine efficiency, with reported cost sitting at or below an implausibly low target. That's exactly what you're describing. A $102 CPA that shows up only after spend collapses to a trickle is not the campaign getting more efficient — it's the bidder finding the handful of cheapest auctions that clear a floor no account of yours has ever sustained, and refusing to bid on everything else. The "beautiful" number is a survivorship artifact of a tiny, biased sample, not evidence the target works.

Finance is reading the one metric an aggressive target is guaranteed to produce (a great-looking average on a starved sample) as proof of success. It isn't. **Revert the target now** — this is the single most documented failure mode in bid-strategy targets, and every hour it stays at $95 is spend, pipeline, and signal you don't get back.

## Why $95 was never going to work: the economics don't support it either

Two derivations, both required, and they disagree with Finance's plan:

**From economics (the affordable ceiling):**
```
break-even CPA = contribution per closed deal × demo-to-close rate
               = $3,500 × 4%
               = $140
```

**From history (the achievable start):**
- Trailing 60-day actual: $240/demo
- Best month ever: $210/demo

**These two numbers are irreconcilable.** Break-even is $140. The account has never once, in its best month, gotten below $210. A $95 target isn't just "below trailing actual" (already the classic choke setup) — it's *32% below break-even itself*. There is no bidding policy that hits $95 profitably right now; the platform can't bid its way to an economic condition the account has never demonstrated it can reach. This is a unit-economics problem — offer, funnel, targeting, or the demo→close rate — not a bidding-target problem, and no amount of target-tuning fixes it.

## What to actually do

**1. Revert the target immediately, as the smallest reversible change.**
Set it back to at/near trailing actual — **$240**, not $95, not even $210. The rule is directional: for a cost target, start at or slightly *above* trailing actual, never at the aspirational number. If your platform has a bid-strategy experiment/simulation tool, use it for the next attempt instead of a hard cutover — it isolates the target's effect instead of confounding it with a fresh learning reset.

**2. Don't re-tighten from panic.** Every edit restarts a learning/exploration period; editing daily "when CPA looks high" is the loop that causes the instability that then justifies the next edit. Wait a full evaluation window — **1-2 conversion cycles** (click-to-demo lag plus reporting delay for this account) — before any further move, and batch any other pending fixes into that single change rather than layering edits.

**3. Take the real gap to Finance as a funnel problem, framed in their own numbers:**

| | CPA |
|---|---|
| Break-even (zero margin) | $140 |
| Best month ever achieved | $210 |
| Trailing 60-day actual | $240 |
| Finance's plan target | $95 |

$95 isn't a bidding target, it's a wish. If the plan needs to hold, the $95-vs-$210 gap has to close through:
- **Contribution per deal or close rate** — the break-even math is the lever with the most headroom: raising demo-to-close from 4% to 6% moves break-even from $140 to $210 on its own, no acquisition change needed. Same for average deal size.
- **Everything upstream of the bidder** — landing page, offer, targeting, creative, demo-show-up rate. Bid strategy is a late lever; changing it when the campaign is already the most efficient it's ever been ($210 best month) masks a symptom, it doesn't fix a cause. Push this to an account-level diagnostic before touching the target again.
- **A revised plan number** — if none of the above moves fast enough, the honest planning input is something derived from $210-240 with a margin buffer under $140, not $95.

**4. Set a real target only once you have room.** If close rate or deal size improves and break-even actually clears above current trailing performance, tighten from trailing actual toward the new economic boundary in small steps (~10-15% per step is practitioner convergent, not vendor-documented — derive step size from this account's own variance if you can), one full evaluation window per step. Never jump straight to the economic ceiling.

**5. Rollback trigger for next time, written down so this doesn't repeat:** spend falling materially below budget for a full evaluation window, combined with impression share lost to rank, reverts the target to trailing actual automatically — don't wait for someone to notice the CPA "looks great."

**Bottom line for Finance:** the $102 CPA is not the target working, it's the target failing in a way that looks like success. The plan's $95 number was never reachable on this account's demonstrated economics ($140 break-even, $210 best-ever) — the fix is closing that gap through funnel economics, not asking the bidder to do something it structurally cannot do without shutting the campaign down.