## Verdict

Reject the agency's flat 4x account-wide target. It's wrong on three independent grounds, and stacking a fourth (the size of the jump) turns it into a likely delivery-choking move on top of being the wrong number.

Set two return-goal targets, split by margin band (premium / basics), not one blended target. Use the math below to bound each, and pull each line's own trailing 30-day ROAS to set the live starting point — the blended number you gave hides too much to bid on directly.

## Why 4x is wrong

**1. "4x is industry standard" is folklore, and it happens to fit a business you're not.**
Break-even ROAS = 1 ÷ contribution margin. 4x break-even corresponds to a 25% margin business. You're blended 40%, so your blended break-even is 2.5x, not 4x — the agency's number isn't even derived from your own economics, let alone your profit goal.

**2. One target across two margin bands 55% apart is a structurally meaningless number.**
A premium order and a basics order can produce the _same_ ROAS while one is 2.5x more profitable per dollar of revenue. A shared target lets the bidder treat them as identical, migrate spend on blended signal, and silently drift the mix in either direction — you'd have no way to tell from the ROAS readout alone whether profit is improving or eroding. This is a named failure pattern, not a hypothetical: pooling a high-margin and a low-margin line under one target is exactly the setup that produces it.

**3. It's aspirational, not history-anchored, and the jump size alone risks delivery collapse.**
Trailing 30-day blended is 2.6x. 4x is +54% above that in one move. The standard discipline caps a single target move at ~10-15% and requires a full evaluation window before the next step. A +54% jump is the textbook cause of the most commonly documented bidding failure: reported efficiency looks great while delivery quietly falls off a cliff, because the bidder stops bidding rather than lose money at a target it can't clear.

## The math

|         | Contribution margin | Break-even ROAS      | ROAS for 10% net profit       |
| ------- | ------------------- | -------------------- | ----------------------------- |
| Premium | 55%                 | 1 ÷ 0.55 = **1.82x** | 1 ÷ (0.55 − 0.10) = **2.22x** |
| Basics  | 22%                 | 1 ÷ 0.22 = **4.55x** | 1 ÷ (0.22 − 0.10) = **8.33x** |
| Blended | 40%                 | 1 ÷ 0.40 = **2.5x**  | 1 ÷ (0.40 − 0.10) = **3.33x** |

Formula: `target_ROAS_for_profit = 1 ÷ (contribution_margin − desired_net_margin)`. Evidence tier: documented (standard contribution-margin derivation).

**What your trailing 2.6x actually means right now:** at blended 40% margin, a 2.6x ROAS implies net margin on ad-driven revenue of `0.40 − 1/2.6 ≈ 1.5%`. You're roughly at blended break-even, not anywhere near the founder's 10% goal — which is presumably why the agency conversation is happening. But the fix isn't "bid harder toward one number," it's "stop bidding on one number."

**What the basics line implies.** 8.33x ROAS is an unusually hard target — well above what most accounts clear. Before setting it as a live bidding target, treat this as a flag: if basics can't plausibly reach 8.33x through bidding alone, that's a unit-economics problem (COGS, price, discount depth) on that line, not a bidding problem. The bidding policy shouldn't chase a target that pricing/cost structure makes unreachable.

## Recommendation, ranked

**A. Split into two return-goal policies by product line (premium vs. basics).** Lower effort — it's a campaign/ad-set structure and reporting change, no new data plumbing. Prerequisite: confirm purchase events are (or can be) tagged by line so each gets its own conversion stream and its own target. This is the standard fix for the blended-margin trap and should be the default here.

**B. Pass margin-adjusted (contribution-dollar) value back instead of gross order value, and run one target.** Higher effort (needs per-order COGS/shipping/fees available at the moment the server-side conversion fires) but higher value: once the _value itself_ already encodes margin, a single target works correctly regardless of mix shift, and the bidder naturally reallocates toward whichever line is most profitable rather than needing you to manage two campaigns by hand. Worth scoping as a follow-on once (A) is running and if there's engineering capacity — don't let it block fixing the immediate problem.

Recommend (A) now, revisit (B) as the compounding upgrade once measurement/eng bandwidth allows.

## The two policies

```
BIDDING POLICY  -  account-wide / premium line
Objective        : value-return
Archetype        : return-goal on purchase value, scoped to premium-line campaigns.
                   Why: real server-side values flow; a shared target with basics
                   would average a 55%-margin line into a 22%-margin line and read
                   as meaningless. Runner-up (one blended target) rejected on that
                   basis.
Evidence         : event = purchase, server-side. Value integrity: confirm values
                   are net of refunds/returns (unconfirmed) and differentiated by
                   line (requires line-level tagging - confirm before splitting).
                   Volume/lag: not provided - pull trailing 30-day conversion count
                   and click-to-purchase lag for premium-tagged campaigns alone.
Target           : set at premium line's OWN trailing 30-day ROAS (pull this -
                   blended 2.6x is not a valid proxy for either line individually).
                   Economics ceiling: break-even 1.82x; with 10% net profit goal,
                   2.22x. Never tighten past 2.22x without re-deriving margin.
                   Refresh: re-derive if COGS, pricing, or discounting on premium
                   SKUs changes, and at least quarterly.
Evaluation       : 2 conversion cycles (click-to-purchase lag + reporting delay -
                   pull actual lag; DTC apparel is commonly under a week, don't
                   assume without checking).
Change rules     : ~10-15% per step toward 2.22x, one full evaluation window
                   between steps, never during a promo/sale window. Approver:
                   name the owner in the final policy.
Rollback trigger : delivery falls materially below budget for a full evaluation
                   window after any tighten → revert one step.
Switch triggers  : a holdout/geo test shows material non-incremental buying on
                   premium retargeting → test before scaling further.
```

```
BIDDING POLICY  -  account-wide / basics line
Objective        : value-return
Archetype        : return-goal on purchase value, scoped to basics-line campaigns.
                   Why: same reasoning as premium - different economics, different
                   target, can't share a pool with premium.
Evidence         : event = purchase, server-side. Same value-integrity checks as
                   premium (refund netting, line tagging) apply here.
                   Volume/lag: pull separately for basics-tagged campaigns - a
                   thinner line may sit closer to the volume floor and read
                   noisier at the same evaluation window.
Target           : set at basics line's OWN trailing 30-day ROAS.
                   Economics ceiling: break-even 4.55x; with 10% net profit goal,
                   8.33x. FLAG: if trailing actual is far below 4.55x, tightening
                   bid strategy alone will not close that gap - escalate as a
                   pricing/COGS/discount-depth problem on this line before
                   committing to an 8.33x bidding target.
Evaluation       : 2 conversion cycles (pull actual lag for basics-tagged
                   campaigns).
Change rules     : ~10-15% per step, one evaluation window between steps, batch
                   with premium's pending changes only if truly independent - a
                   confounded change on one line makes both unreadable.
                   Approver: name the owner in the final policy.
Rollback trigger : delivery falls materially below budget for a full evaluation
                   window after any tighten → revert one step.
Switch triggers  : basics trailing actual proves structurally unable to approach
                   4.55x break-even even before the profit goal → stop tightening,
                   route to pricing/margin, not bid strategy.
```

## What to do with the blended number

Keep 3.33x (blended, profit-goal-derived) and 2.5x (blended break-even) as **reporting KPIs** to sanity-check the account in aggregate — never as a live bid target. If the two split targets are working, the blended actual should drift toward 3.33x on its own as the mix improves; if it doesn't, that's the signal to check whether spend is migrating the wrong way between lines, not a reason to reach for one shared target again.

## Before this is final

Four inputs are needed from your data that weren't in the prompt, and none should be guessed:

1. **Per-line trailing 30-day ROAS** for premium and basics separately (the single most important missing number — it sets both starting targets).
2. **Confirmation purchase values are net of refunds/returns**, and that line-of-business can be tagged on the server-side conversion event.
3. **Click-to-purchase lag** (sets the evaluation window in days).
4. **Named approver** for target changes on each line.

Everything else in this policy — the rejection of 4x, the per-line ceilings, the split structure, the step discipline — holds regardless of those four answers.
