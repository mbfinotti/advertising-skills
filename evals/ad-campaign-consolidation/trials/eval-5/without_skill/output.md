## The numbers first

| Campaign               | 30-day spend | Purchases | CPA         | vs. target                                    |
| ---------------------- | ------------ | --------- | ----------- | --------------------------------------------- |
| Broad prospecting      | $5,400       | 41        | **$131.71** | 3.3x over $40                                 |
| Interest stack 2023    | $1,350       | 6         | **$225.00** | unreliable — see below                        |
| Premium tier           | $2,100       | 11        | **$190.91** | 1.6x over its real target of $120 (3x margin) |
| Spring 2024 launch     | $750         | 0         | undefined   | —                                             |
| Podcast listeners test | $90          | 0         | undefined   | —                                             |

**Important context you should know before acting on the merge question:** none of these are anywhere near $40 CPA — even your best-performing campaign (Broad prospecting) is 3.3x over target. Consolidation will help, but it won't close a gap that size by itself. That's a creative/offer/landing-page problem, not a structure problem, and needs to be worked separately.

## Verdicts

🟢 **Keep as the base: Broad prospecting.** Best volume, but still needs creative/offer work to get anywhere near $40.

🔴 **Merge into Broad prospecting: Interest stack 2023 and Podcast listeners test.**

- Both almost certainly overlap with Broad's audience — "broad" by definition includes interest-stack and podcast-listener users, so these campaigns are likely bidding against your own Broad prospecting in the same auction, inflating everyone's cost.
- Interest Stack's $225 CPA isn't trustworthy as-is: switching from 7-day click to 1-day click 12 days into the window mechanically undercounts attributed purchases for the back half of the period. Adjusted for that, its 6 purchases are statistically consistent with performing at Broad's rate (~10 expected) — there's no real evidence it's worse, just an artifact of the measurement change. Don't compare it further until attribution is made consistent; merge it now and let it ride on the pooled data.
- Podcast's zero purchases on $90 spend is not evidence of failure — at Broad's rate you'd only expect ~0.7 purchases from that spend, so a zero is a coin flip, not a signal. Too small to ever reach significance on its own; fold it in rather than keep testing it in isolation.
- Bonus: none of your campaigns individually hit Meta's ~50 conversions/week threshold to exit the learning phase (Broad ≈9.6/wk, Interest stack ≈1.4/wk, Premium ≈2.6/wk). Pooling conversion signal into fewer campaigns is necessary, not just tidy.

⚫ **Kill, don't merge: Spring 2024 launch.** This is the one genuine negative signal in the set. At Broad's CPA, $750 of spend should have produced ~5–6 purchases; getting exactly zero has under a 1% chance of being random noise. That's real underperformance, and merging it in would mean feeding a demonstrated non-converting audience/creative into a healthy campaign. Cut the budget instead — reallocate the $25/day to Broad.

🟡 **Keep separate: Premium tier.** Different product economics mean a different target CPA (~$120, not $40, given 3x margin). Merging it with standard-margin campaigns would mix conversion events with different values into one optimization signal, confusing Meta's bidding. At $190.91 it's still ~1.6x over its _own_ correct target, so it needs work — but structurally it stays its own campaign (or moves to value-based/ROAS bidding later, which is a separate, bigger decision).

## Net action

- Merge: Interest stack 2023 + Podcast listeners test → Broad prospecting. Combined budget: $228/day.
- Kill: Spring 2024 launch. Reallocate its $25/day into the merged Broad campaign.
- Keep separate: Premium tier, evaluated against a $120 CPA target, not $40.
- Before finalizing the Interest stack merge, ask your buyer to re-pull its data on one consistent attribution window — you're making this call on a number that's currently an apples-to-oranges blend.
- Flag to the team: even after cleanup, Broad prospecting itself is >3x over target CPA. Structure fixes the fragmentation; it won't fix that gap.
