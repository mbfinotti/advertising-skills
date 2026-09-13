# Fernweh Goods — Holiday Concept A/B/C Test Design

## Flag this before anything else

Your three numbers don't reconcile:

| Relationship     | Math         | Implies                                       |
| ---------------- | ------------ | --------------------------------------------- |
| CPC ÷ stated CVR | $1.25 ÷ 2.5% | $50 CPA (not $20)                             |
| Stated CPA ÷ CPC | $20 ÷ $1.25  | 16 clicks/purchase = **6.25% CVR** (not 2.5%) |

That's a ~2.5x gap. It changes every number below, and it also changes whether "95% confidence in 5 weeks" is realistic or not. Pull the actual trailing 30-day **click-to-purchase rate** for your current best ad from Ads Manager before locking this. I've run the plan under both assumptions so you can drop in whichever is correct.

Second flag: 700 purchases/month at $20 CPA implies ~$14,000/month total current spend on purchase campaigns. Your $15,000/month test budget is roughly **that entire amount again**. You're not adding a small test on top of your account — you're close to doubling spend for 5 weeks. Expect some CPC drift as the extra spend pushes into thinner audience segments; don't assume $1.25 holds exactly. Monitor actual CPC weekly and true up click volumes, not just dollars spent.

## Bottom line

- **Structure:** 3-arm test — Control (current best ad) vs. Packing-Hack vs. Lost-Luggage. Equal budget split. One platform-native split-test object, not three competing campaigns.
- **Metric:** click→purchase conversion rate, tested with a two-proportion z-test, each challenger vs. control, **Bonferroni-corrected** (α = 0.025 per comparison to hold family-wise α = 0.05).
- **Power target:** 80%.
- **What it can actually detect in 5 weeks on $15k/mo:**
  - If true CVR ≈ 2.5%: minimum detectable lift ≈ **40% relative** (2.5% → 3.5%+). That's a blowout, not a typical creative delta.
  - If true CVR ≈ 6.25%: minimum detectable lift ≈ **25% relative** (6.25% → 7.8%+). Plausible for a genuinely stronger concept.
- **Verdict:** the "confident winner at 95%" promise only holds if the real CVR is closer to 6.25%, or if one concept meaningfully outperforms. Tell your marketing lead this caveat now, not at the all-hands.

## Test mechanics

1. **Use the platform's native split-test / experiment tool** (e.g. Meta Experiments), not three parallel ABO campaigns. Native tools randomize at the person level and prevent the three ads from bidding against each other in the same auction (auction overlap would inflate all three CPCs and contaminate the comparison).
2. **Hold everything constant except the concept:** same landing page, same offer, same CTA destination, same audience/placements, same optimization event (Purchase). The only variable that should differ is the creative + hook.
3. **Equal budget split (1/3 each).** I checked a Dunnett-optimized allocation (more budget to control since it's compared twice) — it only improves the detectable MDE by ~1.5% relative. Not worth the operational complexity. Keep it simple: even thirds.
4. **No daily peeking for significance.** Checking a fixed-horizon test repeatedly and stopping early on a good-looking day inflates your false-positive rate well past 5% (the "peeking problem"). Week-1 checks are for **kill-switch QA only** (see below), not for declaring a winner.

## Budget & schedule (5 weeks, Sept 12 → ~Oct 17)

$15,000/mo → **$3,462/week** (15,000 × 12/52) → **$17,308 total test budget**.

| Arm          | Weekly budget | Weekly clicks (@ $1.25 CPC) | Total clicks (5 wk) |
| ------------ | ------------- | --------------------------- | ------------------- |
| Control      | $1,154        | ~923                        | ~4,615              |
| Packing-Hack | $1,154        | ~923                        | ~4,615              |
| Lost-Luggage | $1,154        | ~923                        | ~4,615              |

**Week 1 is a kill-switch gate, not a stats checkpoint:** watch CPC, frequency, CTR, and negative feedback for a genuinely broken creative (wrong aspect ratio, policy flag, thumbnail killing CTR). If one arm is obviously malfunctioning technically, fix or pause it — don't let a production bug eat your statistical power. Otherwise, let all three run untouched through week 5.

## Sample size / detectability tables

Two-proportion z-test, α=0.025 two-sided per comparison (Bonferroni for 2 comparisons), power=80%. Cost = clicks/arm × 3 × $1.25.

**Scenario A — stated CVR = 2.5%**

| Relative lift to detect | Clicks needed/arm | Total test cost           |
| ----------------------- | ----------------- | ------------------------- |
| 20%                     | 20,292            | $76,095                   |
| 30%                     | 9,414             | $35,303                   |
| **40%**                 | **4,613**         | **$17,300 (your budget)** |
| 50%                     | 3,671             | $13,766                   |

**Scenario B — CVR back-solved from CPA/CPC = 6.25%**

| Relative lift to detect | Clicks needed/arm | Total test cost           |
| ----------------------- | ----------------- | ------------------------- |
| 15%                     | 13,524            | $50,715                   |
| 20%                     | 7,768             | $29,130                   |
| **25%**                 | **4,613**         | **$17,300 (your budget)** |
| 30%                     | 3,594             | $13,478                   |

Your $17,300 / 4,615-clicks-per-arm plan sits exactly at the "just barely detectable" line for a 40% lift (Scenario A) or 25% lift (Scenario B). Anything smaller than that line will not read as significant at week 5, even if it's real and would matter commercially.

## What to do about the gap

Pick one, now, before the all-hands gets promised something the budget can't deliver:

1. **Confirm actual CVR** (highest priority — resolves whether you're in Scenario A or B).
2. **If Scenario A holds (2.5% CVR):** either accept the test can only catch a huge winner, or narrow to a **2-arm test** (best challenger vs. control, decided by week-1 directional read) — removes the Bonferroni penalty and doubles per-arm budget, dropping detectable lift from 40% to ~30%. Still not great, but meaningfully better.
3. **Extend past 5 weeks** if the all-hands date can flex — 8 weeks at the same budget gets Scenario A to ~28% detectable lift.
4. **Increase test budget** for this window only — cost scales roughly with 1/lift², so halving the detectable lift needs ~4x the spend.
5. **Reframe the ask to the marketing lead now:** offer a Bayesian "probability concept X is best" readout as a fallback if the frequentist test is inconclusive at week 5. It's honest under a hard deadline and doesn't require the peeking-problem tradeoffs a fixed-horizon frequentist test does. I'd rather you walk into the all-hands with "82% probability X wins" than a p=0.09 dressed up as "95% confidence."

## Analysis at week 5

For each challenger vs. control, with x = purchases, n = clicks per arm:

```
p_pool = (x_challenger + x_control) / (n_challenger + n_control)
z = (p_challenger_hat - p_control_hat) / sqrt(p_pool*(1-p_pool)*(1/n_challenger + 1/n_control))
```

Compare |z| to 2.24 (Bonferroni-adjusted critical value for α=0.05 family-wise, 2 comparisons) — not 1.96, which is the uncorrected single-test threshold and will overstate your confidence if applied to both comparisons.

Pre-register the decision rule now, before you see data: a concept wins only if (a) it clears the adjusted significance bar **and** (b) the CPA improvement is large enough to matter for production planning (set that $ threshold with your marketing lead this week) **and** (c) it didn't degrade guardrails (CTR, frequency, negative feedback) to get there.
