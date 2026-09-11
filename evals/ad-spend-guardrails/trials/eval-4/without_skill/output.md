## Starter guardrails: CAC ceiling & ROAS floor

**Base assumption (deliberately conservative):** contribution margin = **50%** — the bottom of your 50–60% estimate. Use the low end for guardrails; if real margin turns out higher, you're leaving a little on the table, not bleeding cash. Revisit once you actually calculate it precisely.

### The Meta/Shopify gap — fix this first, before trusting any platform number

Meta over-reporting revenue ~40% vs. Shopify is a near-universal pattern since iOS 14.5 — it's Meta's modeled/probabilistic conversions plus view-through attribution crediting purchases that either happened via another channel or didn't happen at all. You don't need to root-cause it to operate safely; you need to stop trusting Meta's dashboard as ground truth.

**Rule: Shopify is the only source of truth for revenue and CAC.** Compute a blended MER instead of reading platform ROAS:

```
Blended MER = Total Shopify Revenue ÷ Total Ad Spend (all channels)
Blended CAC = Total Ad Spend ÷ New Customers in Shopify
```

Do this weekly. Never size budget decisions off the Ads Manager "Purchase ROAS" column alone.

### The two numbers to operate with

| Metric | Breakeven | **Operating floor/ceiling (20% profit buffer)** |
|---|---|---|
| **ROAS floor** (blended, Shopify revenue) | 2.0x | **2.5x** |
| **CAC ceiling** (blended, Shopify revenue) | 50% of AOV | **40% of AOV** |

Math: breakeven ROAS = 1 ÷ CM% = 1 ÷ 0.50 = 2.0x. CAC breakeven = CM% × AOV = 50% of AOV. The buffer (÷1.25) leaves ~20 points of margin above breakeven for overhead and actual profit rather than just covering variable costs.

### If you're eyeballing the Meta Ads Manager dashboard day-to-day

Since Meta shows ~1.4x the revenue Shopify actually books, its dashboard ROAS needs a haircut to mean anything:

- **Meta-dashboard ROAS floor ≈ 3.5x** (= 2.5 true floor × 1.4 inflation factor)

Don't try to correct Meta's reported CPA/CAC the same way — you don't yet know whether the gap comes from inflated conversion *count* (which would make Meta's CPA falsely low) or inflated *order value* (which wouldn't touch CPA at all), and guessing the wrong direction is worse than not adjusting. **For CAC, use the blended Shopify number only; treat Meta's own CPA column as directional noise, not a target.**

### Bottom line to start operating today

- Kill/scale spend on **blended ROAS < 2.5x** or **blended CAC > 40% of AOV**, calculated from Shopify actuals.
- Treat any Meta-dashboard ROAS below ~3.5x as a red flag needing Shopify confirmation.
- Recompute both numbers the moment you have: (1) an actual contribution margin, (2) even a rough repeat-purchase rate — first-order breakeven ceilings like these are always the most conservative version of CAC math, and you're very likely underspending on acquisition relative to true LTV once you have that number.