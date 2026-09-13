# Verdana Home — $80K/mo Media Allocation, Next Cycle

Before the split: your draft plan matches, almost line for line, the canonical _"tempting plan that fails review"_ pattern — average ROAS instead of marginal, platform-reported brand-search ROAS treated as ground truth, a 100% step on brand search, and a bounded test killed before its decision date. I'm not running it as written. Here's what actually clears the gates, and why.

## Gates

| Gate                        | Result                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Affordability (payback)** | ⚠️ Not computable — no CAC, LTV, or retention data given. Used break-even ROAS = 1 ÷ 0.52 = **1.92x** as a stand-in. All five lines clear 1.92x on _reported_ numbers — including Meta prospecting at 2.0x, which is why "cut it, it's only 2x" doesn't hold up.                                                                                                                                                                                                           |
| **Measurement maturity**    | ⚠️ Not scored (no interview data on dashboards/tracking/attribution). Proceeding on directional proxies only, whole plan labeled **provisional**.                                                                                                                                                                                                                                                                                                                          |
| **Funding floor**           | ✅ All five lines clear their floor at current or proposed spend (smallest, TikTok at $8K/mo ≈ $267/day, is well above the ~$50/day automated-channel floor). No channel is eliminated by size.                                                                                                                                                                                                                                                                            |
| **Data basis**              | ❌ **Every number in your prompt is platform-reported.** Platform ROAS overstates true return 1.75–2.97x, and brand search specifically is the textbook offender — one published test saw a brand-search ROAS collapse from 19x to 5.7x under incrementality testing. Google's 12x is not evidence "it's clearly our best performer"; it's the single least trustworthy number in your account. This gate fails for Google brand and caps how much weight I give it below. |

**No incrementality tests or MMM exist**, so nothing here is measured — every marginal call below is a directional proxy. Say so on the finance slide too.

## Approach picked

- **Split approach:** Incremental reweighting (bounded moves, ranked by marginal signal) — not a from-zero rebuild, since you have a working mix and no trigger (inherited split, high measurement maturity, or annual review) that would justify one.
- **Estimate method:** Directional proxies on every line — penetration band for Meta, impression-share headroom for Google. Zero effort to gather (you already have these numbers), but they buy direction and headroom only, never magnitude. Flagging Google brand as large enough ($12K/mo, ~$36K/quarter) and distorted enough (12x reported) to justify commissioning a proper incrementality holdout starting this cycle — see Experiments.

## The strongest case against my own biggest move

Cutting Google brand 20% assumes most of that 12x is non-incremental. It might not all be — some branded search is comparison shoppers who'd click a competitor's ad if you're not there, and that portion is real. I don't have a test result to confirm the split, so this cut is a hedge sized to the uncertainty (capped at the standard 20% step, not a kill), not a confident verdict. The holdout test below is what turns this from a hedge into a number.

## Finalized split

| Line                 | Current     | Proposed    | Δ          | Rationale (marginal evidence, proxy-labeled)                                                                                                                                                                                                                                                                                                                 | Uncertainty                                                                      | Rollback threshold                                             | Verify                                                                         |
| -------------------- | ----------- | ----------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| **Meta prospecting** | $30,000     | **$32,600** | +8.7%      | Penetration 410K/2.4M ≈ **17%** — under the 25% headroom band, real room to scale. Sized below the 15–20% default step: capped by what the two cuts below actually freed, not by weak evidence — see Constraints.                                                                                                                                            | Medium (reach-based proxy; platform ROAS may overstate true return by up to ~3x) | Blended MER falls, or CPA > 1.3x current, for 2 straight weeks | Day 30                                                                         |
| **Google non-brand** | $14,000     | **$16,200** | +15.7%     | Lost impression share to budget = **44%**, well under the 60–80% ceiling where more budget stops helping. Cleanest, best-evidenced proxy in this account.                                                                                                                                                                                                    | Low–medium                                                                       | CPA > 1.3x target for 2 weeks                                  | Day 30                                                                         |
| **Meta retargeting** | $16,000     | **$13,600** | −15%       | At 16/(30+16) = 35% of Meta spend, not yet over the ~40% caution line, but its 4.9x is partly credit for conversions prospecting created. Trimmed as a funding source for prospecting's growth — not because 4.9x < 2.0x is a valid reason to shrink it further.                                                                                             | Medium                                                                           | New-customer order share drops >10% (pool-refill risk)         | Day 30                                                                         |
| **Google brand**     | $12,000     | **$9,600**  | −20% (cap) | 12x is platform-reported and brand search is the known near-non-incremental line (data-basis gate fail). Trimmed at the maximum single-cycle step, not killed — see counter-case above. Funds the holdout test design this cycle.                                                                                                                            | High — this is exactly why the test exists                                       | Tracked branded-search revenue falls >10%                      | Day 30, retest at holdout readout                                              |
| **TikTok test**      | $8,000      | **$8,000**  | 0%         | Bounded experiment, week 5 of a pre-set 8-week run with a **day-60 decision date**. "Hasn't beaten Meta's 2.0x" compares it to Meta's _average_, not marginal, ROAS, and no stop condition was declared up front — killing it now breaks its own test design on a below-floor sample. Holding flat, not scaling either, since it hasn't cleared the bar yet. | High, bounded by design                                                          | None before day 60 — that's the point of a decision date       | **Day 60**, ~Oct 10, 2026 (confirm exact date against the original test start) |
| **Total**            | **$80,000** | **$80,000** | —          | Sums exactly to the fixed budget                                                                                                                                                                                                                                                                                                                             | —                                                                                | —                                                              | —                                                                              |

## Experiments

**TikTok:** hold $8,000/mo unchanged to day 60. Before that date, write down the stop condition that was missing from the original design — e.g. _"kill if CPA doesn't close within 1.5x Meta prospecting's marginal CPA by day 60."_ Judge it then, against Meta's marginal line (the last dollars you'd actually pull from it), not Meta's blended average.

**Google brand search holdout (new, starts this cycle):** design a geo or ad-scheduling holdout on brand search — smallest test that would still move a $12K/mo, likely-overstated line from "provisional" to "measured." This is the single highest-value thing this account can buy right now: a $12K/mo line reported at 12x, if actually closer to the 5.7x seen in comparable published tests, is a meaningfully different number to plan around next quarter.

## Constraints that blocked otherwise-correct moves

- **Fixed total.** Prospecting's headroom proxy alone would support the full 15–20% step (+$4,500–6,000), but the two funding sources (retargeting −15%, brand −20%, both at their bound) only freed $4,800 combined, split between prospecting and non-brand. Prospecting's increase is capped by _available cash_, not by weak evidence — flag this honestly to whoever approves the plan.
- **No creative-supply or fatigue data given** for Meta or TikTok — didn't scale any line past what the data supports; ask before a larger step next cycle.
- **No CAC/order-volume data given**, so I'm not putting a fabricated "+X orders/month" number on any line, unlike a typical change packet. Get me baseline AOV and order counts per line and I'll turn "direction" into "magnitude" next cycle.

## Governance

- Retargeting (−15%) and Google brand (−20%) both exceed the 10%-of-channel-budget line → route through your standard approval workflow before executing.
- None of the five moves exceed 25% of channel budget, so no joint marketing/finance sign-off is triggered by size alone — though I'd still loop finance in on the brand-search holdout given what's riding on the result.

## Revisit

- **Monthly reweight**, rolling 60-day read windows, next check-in **day 30 (~Oct 12, 2026)** for the four reweighted lines.
- **TikTok decision: day 60 (~Oct 10, 2026)** — independent of the monthly cycle, don't let the monthly reweight override its own decision date early.
- **Quarterly:** fold the brand-search holdout readout into the next full resplit; that's also the point to zero-base the whole mix if this account's evidence quality has improved.

## Open questions (would change this plan)

1. CAC, LTV/retention, or a discounted-payback figure per line — needed to actually run the affordability gate instead of the break-even proxy.
2. ROAS/CPA for Google non-brand and TikTok were never given — only penetration/impression-share signals. I can't build a blended-MER forecast without them, and I'm not inventing one.
3. Measurement-maturity score (dashboards, tracking, attribution) — under 6/15 and this whole exercise should pause for tracking work before the next cycle, not just get labeled provisional.
4. Exact TikTok test start date, to confirm day-60 falls where "week 5 of 8" implies.
5. Is 52% margin blended across the whole catalogue, or does it vary meaningfully by SKU mix across channels? If it varies, break-even ROAS isn't one number across these five lines.

## On the "4x ROAS" target

Drop it as a blanket bar. Your break-even is **1.92x** (1 ÷ 0.52), not 4x — 4x is a folk benchmark, not derived from your margin. Worse, applying one number across funnel stages is a category error: prospecting will always run closer to breakeven than retargeting (which inherits credit for conversions prospecting created) or brand (which converts demand that mostly already existed). Judge the portfolio on blended MER against a target finance sets from your actual overhead and profit goals, not 4x — and judge each line on marginal contribution, not whether it clears a uniform ROAS bar.

---

Nothing above executes until you approve it — this is a proposal, not a change log. Tell me which sections you want adjusted, and separately, whether you want me to spec the brand-search holdout test now (hypothesis, geo split, MDE, read window) — that's the one piece of this plan that turns next cycle's numbers from proxies into evidence.
