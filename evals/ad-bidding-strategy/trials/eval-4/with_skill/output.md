Ran your plan against the bidding-strategy skill's Seasonality section and Failure Modes table. Three real problems, not just nitpicks — worth fixing before you touch Google Ads.

## 1. The +200% adjustment is scoped to the wrong window

Seasonality/conversion-rate adjustments are documented for short spikes (roughly 1-7 days), not month-long stretches. Applying +200% across all of November stretches a short-spike tool past its window.

**Fix — split it in two:**
- **BFCM weekend only** (the actual 3-4 day spike): scheduled conversion-rate adjustment, dated to just those days.
- **Rest of November** ("runs hot vs. October" generally): that's a long seasonal pattern, not a spike. Re-derive your bid target from November's own trailing actuals (last year's Nov numbers, or the Oct→Nov delta), then restore the normal target in December. Don't cover it with a stretched adjustment.

## 2. +200% is sized to the wrong thing

Tripling conversions → +200% treats the adjustment field as if it controls conversion **count**. It doesn't — it tells the bidder to expect a shift in conversion **rate** per click. This exact mistake has a documented failure case: a 100% adjustment for an expected doubling of conversions blew a full day's budget by late morning, because rate rose far less than count.

Your 3x is two things stacked together:
- More traffic (more shoppers searching/clicking because it's BFCM) — the auction already absorbs this on its own; you don't need to tell the bidder about it.
- A genuine rate lift (25% off converts a given visitor more often than full price) — this is the only part that belongs in the adjustment.

Feeding it the full 3x double-counts the traffic surge on top of what the auction already sees, and risks the same early-budget-blowout failure. Pull last year's BFCM weekend and compare conversion **rate** (conversions ÷ clicks) against a normal November weekend, not raw conversion volume against a normal day — that ratio is your adjustment input, and it'll land well under 200%.

## 3. The data exclusion is the wrong tool entirely

The skill is explicit: data exclusions are outage tooling, for broken tracking — not for demand swings. "Do not conflate the two; frequent exclusions degrade the bidder."

Your BFCM weekend isn't broken data. It's real, valid conversions from a real (temporary) shift in demand and price. Excluding it throws away exactly the signal you want the bidder to learn from, and repeated exclusions like this degrade it going forward. Drop the exclusion. Let the correctly-scoped rate adjustment (point 1) carry the "expect this to look different" signal, and let the real weekend data flow through normally.

## 4. One thing your plan doesn't mention: the discount hits your margin, not just demand

25% off sitewide isn't just a demand event, it's a temporary economics change. If you're running a cost-goal or return-goal (tCPA/tROAS) strategy, break-even shifts down for the discount window because margin per order shrinks. That's a separate lever from the conversion-rate adjustment:

- **Conversion-rate adjustment** → tells the bidder demand/rate is temporarily different.
- **Target itself** → may need its own temporary move to reflect temporarily thinner margin, then restore after the sale.

Don't ask one tool to cover both jobs.

## Before I can give you exact numbers, I need:

1. **Current strategy**: Target CPA/ROAS, Max Conversions/Value, or manual? (Changes which levers even apply.)
2. **Value tracking**: does the platform get real transacted order value (post-discount, i.e. the $75 actually charged, not $100 list), or a flat/estimated value? If values are wrong during the sale, a return-goal target will chase a distorted number.
3. **Margin structure**: contribution margin rate at full price vs. at 25% off — needed to size how far (if at all) to loosen the target for the sale window.
4. **Last year's BFCM data**: conversion rate that weekend vs. a normal November weekend, so the rate-only adjustment is derived from your actuals, not guessed.

## Net change to your plan

| Piece | Your plan | Fix |
|---|---|---|
| +200% seasonality adj. | All of November | BFCM weekend only, sized to rate lift (not the 3x count) |
| Rest of November | Not addressed | Re-derive target from Nov trailing actuals, restore in December |
| Data exclusion | Over sale weekend | Remove — this isn't broken tracking, don't exclude real demand data |
| 25% discount | Not connected to bidding | Check value tracking reflects real discounted price; consider a separate, temporary target move for margin compression if on tCPA/tROAS |

Also: batch these as one coordinated change going into the weekend rather than editing piecemeal during it — a single relearn beats a chain of resets — and evaluate afterward in conversion cycles (click-to-conversion lag plus reporting delay), not calendar days.