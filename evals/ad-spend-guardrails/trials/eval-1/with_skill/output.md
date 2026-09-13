# SPEND GUARDRAIL POLICY — Maribel Home Goods

**Effective:** 2026-09-12 · **Status:** PROVISIONAL — see Assumptions · **Review:** 2026-12-12 (quarterly)

## The short answer for your CFO

**Don't use 4x.** 4x ROAS is not a benchmark — it's break-even math for a 25%-margin business, retroactively turned into folklore (no traceable author). Maribel runs a 45% contribution margin, so Maribel's break-even is **2.22x ROAS**, not 4x. If you wrote "4x" into the annual plan, you'd be rejecting every dollar of ad spend that returns between 2.22x and 4x — and that dollar is _profitable_. At $60K/month, that's real growth left on the table for no reason grounded in your own economics.

## Inputs

| Input                                                | Value                         | Status                                        |
| ---------------------------------------------------- | ----------------------------- | --------------------------------------------- |
| AOV                                                  | $68                           | measured                                      |
| Contribution margin                                  | 45% (after COGS + shipping)   | measured, but scope-limited — see Assumptions |
| Monthly paid spend                                   | $60K (Meta + Google, blended) | measured                                      |
| Payback target                                       | —                             | **missing**                                   |
| Cash runway / burn                                   | —                             | **missing**                                   |
| Growth stage / funding posture                       | —                             | **missing**                                   |
| Measurement trust (feed reliability, incrementality) | —                             | **missing**                                   |
| Who can pause spend / approve overage                | —                             | **missing**                                   |

## Derivation

Contribution per order = AOV × margin = $68 × 0.45 = **$30.60**

**Break-even ROAS** = 1 ÷ 0.45 = **2.22x**
**Break-even CAC (new-customer)** = **$30.60**

Show your CFO this line directly: at 45% margin, every order acquired for less than $30.60 in ad cost, or returning at least 2.22x, covers its COGS and shipping. Below that line, you're paying to lose money — full stop, regardless of what any benchmark says.

**4x reframed:** a 4x floor implies a 25% margin (1 ÷ 4 = 0.25). Applying it to a 45%-margin brand isn't conservative, it's mismatched — it throttles real, profitable volume.

## Layers

| Layer                    | Value                            | Consequence                                                                |
| ------------------------ | -------------------------------- | -------------------------------------------------------------------------- |
| Break-even floor         | **2.22x ROAS / $30.60 CAC**      | Below this line: spend is destroying value. Stop, always — not negotiable. |
| Target floor             | **Not yet set — see below**      | Below this: investigate, don't panic-stop.                                 |
| Hard floor / kill-switch | **Not yet set — needs cash cap** | Automatic halt + escalation + written restart condition.                   |

### Target floor — three options, pending your input

I can't hand you one "official" target floor number honestly — it depends on how much profit-per-order you need to fund overhead and how fast you need cash back, neither of which I have. What I can give you is the menu, each derived from your own margin, so you and your CFO pick the posture rather than inherit someone else's:

| Posture                               | Target ROAS | Contribution left per order after ad cost* | Fits when                                                                  |
| ------------------------------------- | ----------- | ------------------------------------------ | -------------------------------------------------------------------------- |
| Growth-max                            | 2.5x        | ~$3.44                                     | Cash is not tight, priority is customer count / market share               |
| Balanced (**default recommendation**) | 3.0x        | ~$7.87                                     | Standard annual-plan posture absent other constraints                      |
| Profit-focused                        | 3.5–4.0x    | ~$13–15                                    | Cash-constrained or already profitable, want margin protection over volume |

*Contribution left per order = ($68 × 0.45) − (68 ÷ target ROAS), illustrative only — it doesn't yet net out overhead, returns, or payment processing (see Assumptions).

**Recommendation for the annual plan:** open at **3.0x ROAS / ~$22.67 CAC** as the target floor — comfortably above break-even (35% buffer) to cover the margin gaps flagged below, without adopting a folklore number your own math doesn't support. Confirm against your actual payback tolerance and cash runway once known; this is a starting point, not a locked number.

## Guardrail set (2–3 metrics, each with a counter-metric)

| Guardrail                     | Variant                                           | Window         | Source                                   | Counter-metric               |
| ----------------------------- | ------------------------------------------------- | -------------- | ---------------------------------------- | ---------------------------- |
| MER (blended)                 | platform-agnostic, business revenue ÷ total spend | rolling 7-day  | GA/order platform, not ad-platform ROAS  | New-customer share of orders |
| Contribution margin after ads | CM3 if available, else current CM2                | rolling 14-day | Finance/order data                       | New-customer share of orders |
| New-customer CAC              | first-order, not blended                          | rolling 14-day | Order platform, new vs. returning tagged | Prospecting share of spend   |

Never guardrail platform-reported ROAS directly — Meta/Google report claimed revenue, not caused revenue, and optimizing to it pushes budget into retargeting and branded search that would have converted anyway. Pull MER and CAC from your own order data.

## Kill rules (structure set; exact thresholds need your cash cap)

- **Streak condition:** MER below target floor for 3 consecutive rolling-7-day windows.
- **Rate condition:** ≥25% of monthly budget burned in a rolling 3-day window while MER sits below target floor.
- **Evidence gate:** no kill before $500–$1,000 cumulative spend on a given campaign/ad set (CTC activation floor), and no kill inside the platform's own learning phase.
- **Three outcomes:** Allow / Review / Halt — a single breach routes to review, not automatic pause; only sustained or fast-burning breaches trigger a halt.
- **Pause-duration cap:** if halted, cap the pause at ~7 days where possible — a longer Meta pause resets algorithmic learning and can cost more than the overspend it prevented.
- **Fail closed:** if the conversion feed is missing, stale, or broken, hold spend flat — never scale on unverified data, never treat "no data" as "the number is fine."
- **Restart condition:** MER back above target floor for 2 consecutive windows, approved by [owner — TBD].
- **Hard-dollar cap:** **missing** — needs monthly cash runway to size. Do not finalize the kill-switch without it.

## Governance (placeholders — need names)

- **Threshold owner:** [TBD — must not be the person buying media]
- **Escalation approver (breach → halt):** [TBD]
- **Budget-increase approver:** [TBD]
- **Exception process:** time-boxed, written justification, logged — "seasonality" or "timing" alone is not sufficient justification.
- **Re-baseline:** quarterly, plus immediate re-baseline on any margin change, pricing change, or attribution/tracking change.

## Exemptions

No exploration/testing budget carve-out defined yet. If you want new-channel or new-creative testing held to a looser bar than the production floor, ring-fence a declared % of the $60K with its own rules — otherwise testing dies quietly under the main floor.

## Assumptions — what would invalidate this policy

1. **45% margin scope.** Stated as "after COGS and shipping." If payment processing fees, returns/refunds, discounts, or customer service costs aren't yet netted out, true contribution margin is lower than 45% — which pushes break-even ROAS _above_ 2.22x. Confirm this is fully-loaded CM before locking any floor.
2. **Payback target and cash runway are unknown** — the target-floor menu above is derived from margin alone; it hasn't been checked against how fast you actually need cash back.
3. **Architecture assumed:** this draft uses a tiered-ladder structure (break-even / target / hard floor with escalating response) as the default fit for a $60K/month account past solo-operator scale. If nobody can realistically chair a recurring review of these numbers, collapse to a single break-even floor instead — say so and I'll redraft.
4. **Measurement trust unconfirmed** — if your Meta/Google conversion feed has known gaps (iOS/ATT, cookie loss), the guardrail set above should sit on your order-platform numbers only, which this draft already assumes but hasn't verified with you.
5. Owners and approvers are placeholders — a threshold with no named owner isn't a control.

**Before this is final-plan-ready:** confirm (a) fully-loaded margin, (b) payback/cash constraints to pick a target floor from the menu, (c) monthly cash cap for the kill-switch, (d) real names for owner/approver roles. Everything else in this draft is ready to go once those four are filled in.
