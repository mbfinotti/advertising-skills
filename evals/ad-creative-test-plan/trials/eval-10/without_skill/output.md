## The core problem with your plan

Mixing all three concepts into every ad set feels "fair" but it destroys the one thing a creative test needs: an isolated variable. Two things happen:

1. **Within each ad set, Meta's delivery algorithm doesn't split budget evenly.** It shifts spend to whichever ad gets early signal and starves the rest. With 3 ads per ad set on ~$220/day, you'll effectively be reading 1 ad per ad set, not 3 — the "fairness" is illusory and you lose concept-level signal.
2. **You can't attribute results to a concept.** If ad set 1 outperforms ad set 2, you won't know if it's because "movie night" beats "wake up naturally," or because the algorithm happened to favor a different ad in each set. Randomly distributing types across ad sets is the opposite of a controlled test.

`tindra_final_v2_new1.mp4` is also a dead end — nothing in that name tells you which concept, variation, or version it is once you're staring at a performance report three ads deep.

## Recommended structure

**One ad set per concept**, not one of-each-type per ad set:

| Ad set | Ads | Budget (ABO) |
|---|---|---|
| Movie night | 3 variations | $220/day |
| Wake up naturally | 4 variations | $220/day |
| Security / away mode | 2 variations | $220/day |

Rules to keep it a real test:
- **Same audience, placements, optimization event, and CTA across all three ad sets.** Concept is the only thing that should differ. If you use interest/lookalike targeting, use the *same* audience in all three — don't let ad set 1 target one audience and ad set 3 another, or you're testing audience, not creative.
- **Use ABO (ad set budget), not CBO.** You've already specified $220/day per ad set — stick to that. CBO would let Meta reallocate budget across ad sets mid-test and cannibalize your ability to compare concepts cleanly.
- **Avoid audience overlap between the three ad sets.** If they can bid against each other in the same auction, delivery and CPA get distorted for reasons that have nothing to do with creative quality.
- Treat ad-level results (which of the 3/4/2 variations wins) as **secondary/directional**, not the primary readout — especially in the "wake up naturally" ad set, where 4 ads splitting one ad set's budget means less volume per ad than in the security ad set's 2.

## Does the budget support this?

- $220/day ÷ $24 target CPA ≈ 9.2 conversions/day/ad set → ~64/week, ~128 over the 14-day window.
- Meta's learning phase wants ~50 optimization events/week/ad set — you clear that at the ad-set level, which is why concept-level (not ad-level) should be your primary read.
- Total spend: $220 × 3 × 14 = **$9,240** over the two weeks, ~385 conversions total if CPA holds.
- 128 conversions per concept is enough to spot a real gap (e.g. $18 vs $30 CPA) but not enough to call a close one (e.g. $23 vs $25) with confidence — decide in advance how you'll handle a near-tie (extend the test on that pair rather than force a call at day 14).

## Naming convention

Replace `tindra_final_v2_new1.mp4` with something that survives being seen out of context in Ads Manager or a spreadsheet:

```
tindra_<concept-code>_<variant>_<yyyymmdd>.mp4
```
Examples: `tindra_movienight_v1_20260912.mp4`, `tindra_wakeup_v3_20260912.mp4`, `tindra_security_v2_20260912.mp4`

Concept codes: `movienight`, `wakeup`, `security`. Keep ad names in Ads Manager matching this scheme so a breakdown by ad name doubles as a breakdown by concept — you shouldn't need to open the creative to know what you're looking at.

## During the two weeks

- **Watch frequency** on the ad set with only 2 creatives (security) — least creative rotation, most fatigue risk at this spend level.
- **Don't touch budgets or pause ads mid-test** unless CPA blows past ~2x target with real volume behind it (e.g. >30 conversions) — early noise in the first few days is normal, not a verdict.
- **Log daily CPA per ad set**, not per ad, so your day-14 decision is based on the concept comparison you actually built the structure to answer.

## Day 14 decision rule

- Rank the three ad sets by CPA (and by volume at that CPA — a concept hitting $22 CPA on 40 conversions is a weaker signal than one hitting $24 on 130).
- Kill the clear loser(s), keep the winner, and if two concepts land within noise of each other, run a follow-up test between just those two before committing budget — don't force a single winner out of a marginal gap.
- Once you have a winning concept, that's when it's worth testing its variations against each other individually — not before.