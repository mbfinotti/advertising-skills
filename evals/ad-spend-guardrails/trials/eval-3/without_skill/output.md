# Meta Scaling Guardrail — Torvale Supplements

## 1. The 1.4 breakeven number is wrong (or at least incomplete)

- 70% gross margin ⇒ 1 / 0.70 = 1.43. That's breakeven on **COGS only**.
- It ignores: payment processing (~2.9% + $0.30), non-recovered shipping cost, discount codes, refunds/returns (supplements often run 5–10%+ due to satisfaction guarantees), customer service cost per order, and the agency's own fee.
- Get finance to compute **CM2** (contribution margin after all variable costs, not just COGS). It's likely 55–62%, not 70%.
- **Real breakeven MER = 1 / CM2**, probably **1.6–1.8**, not 1.4.

## 2. Blended MER hides the decay curve — scale on marginal, not blended

- 2.0 is the *average* return across $110K. The next dollar spent is never as efficient as the first — that's diminishing returns, not a flat line.
- $110K → $150K is a +36% jump. The **marginal MER on that incremental $40K** could easily be 1.0–1.5, even while the blended average still reads "healthy" for weeks.
- Approving off the blended number is approving off the wrong number.

## 3. The guardrail rule

- **Never approve a spend increase unless projected marginal MER on the increment ≥ true breakeven MER × 1.3** (buffer for volatility, seasonality, attribution noise).
  - If true breakeven = 1.7 → minimum acceptable marginal MER = **~2.2**.
- **Scale in steps, not jumps**: max +15–20% week-over-week. Not +36% in one shot.
- After each step, hold 3–5 days, then measure:
  **Marginal MER = (Revenue this week − Revenue last week) / (Spend this week − Spend last week)**
- **Freeze** spend if marginal MER < threshold for 2 consecutive weeks.
- **Roll back immediately** if marginal MER < 1.0 (losing money on the incremental dollar, before even counting overhead).

## 4. Don't trust the attribution at face value

- Meta's reported revenue typically overstates true incrementality by 20–40%, especially with branded search and retargeting soaking up credit for demand that existed anyway.
- Run (or ask the agency to run) a geo holdout / conversion lift test before treating "2.0 blended" as ground truth — quarterly, minimum.
- Watch **frequency and CPM trend** independently of MER: rising frequency + flat/rising CPM at the same spend level = saturation, regardless of what the reported ratio says.

## 5. Check cash and LTV assumptions

- If MER is measured on Day-0 revenue but the model relies on repeat/subscription revenue to be profitable, a healthy blended MER can mask weak first-order economics.
- Confirm you can carry the extra $40K/month in spend for 60–90 days of cash before repeat revenue comes back, independent of whether it's "profitable" on paper.

## 6. This month's decision

- **Don't approve the full jump to $150K.**
- Approve a first step to **~$125–130K** (15–20% increase).
- Require a marginal-MER report after 1 week before authorizing the next step.
- Require the real CM2/breakeven number and one incrementality test result before "2.0 blended, 1.4 breakeven" gets used as a scaling justification again.