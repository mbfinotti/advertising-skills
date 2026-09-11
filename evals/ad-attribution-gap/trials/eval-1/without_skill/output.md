## The real answer: you can't make these three agree — and you shouldn't try

Each system is measuring a different thing by design. Meta's "purchases" is a *modeled attribution estimate*, your analytics tool is a *client-side tracked estimate*, and Shopify is the *ledger of money that actually changed hands*. Forcing them to show one identical number would mean overriding one of them with a fake value. What you actually want is: **one number your CEO can trust, plus a clear explanation of why the other two differ.**

## The number to report

**March: 1,351 orders, $278,000 net revenue.**

- Shopify revenue (excl. tax/shipping): $296,000
- Minus refunds processed in March: −$18,000
- **= $278,000 net revenue**
- Order count: 1,351 paid orders (see caveat below on refunded orders)

Use Shopify as the system of record for the headline revenue/order KPI. It's the only one of the three counting actual completed, paid transactions rather than attributed or tracked events. Report this number up, and stop trying to reconcile Meta or the analytics tool's figures *to* it — reconcile the *gap*, not the number.

## Why Meta shows 1,912 purchases / $412k (not wrong, just a different measurement)

Two separate inflation sources are stacking:

1. **Revenue definition mismatch**: Meta's $412k includes tax and shipping; Shopify's $296k doesn't. That alone accounts for a real chunk of the $116k gap — not a tracking error, just different line items. You can't precisely back this out without your average tax rate and average shipping charge per order, but it's likely $20–40k of the gap on its own.
2. **Purchase count inflation (1,912 vs 1,351, +41%)**: This is the bigger issue and it's structural, not fixable by "cleaning up tracking." Meta's default attribution window (typically 7-day click / 1-day view) credits itself with purchases that:
   - were influenced by another channel (email, organic, direct) but happened to also see or click a Meta ad
   - are double-counted between Pixel and Conversions API if dedup isn't configured correctly
   - fall inside the view-through window from a scroll-past impression, not a real influence
   
   Every ad platform does this — if you added up "purchases" claimed by Meta + Google + TikTok + email, they'd sum to several multiples of your real order count. This is the well-known "attribution isn't additive" problem, not a Maren & Oak-specific bug.

**Action, not reconciliation**: check your Meta attribution setting (Events Manager → Attribution Settings) and Conversions API dedup key. But even fixed, expect Meta to overcount by 15–25% vs. Shopify indefinitely — that's normal for last-touch/multi-touch ad platform reporting.

## Why the analytics tool shows 1,104 purchases (−18% vs Shopify)

This is tracking *loss*, the opposite direction:

- iOS 14.5+ App Tracking Transparency and Safari ITP block a meaningful slice of client-side pixels
- Ad blockers and cookie-consent rejections drop events before they fire
- If the tool is session/cookie-based, purchases from returning customers on a new device or cleared cookies won't tie back to a tracked session

1,104 vs 1,351 real orders (247 missing, ~18%) is a plausible, fairly typical tracking-loss rate for 2026 given privacy changes. This tool is useful for *relative* trends (is traffic/conversion rate up or down week over week) but will always undercount absolute volume against Shopify.

## What to tell your CEO, in one paragraph

> "Shopify is our source of truth: 1,351 orders and $278k net revenue in March, after $18k in refunds. Meta's 1,912/$412k figure overstates both because it includes tax and shipping, and because ad platforms structurally over-attribute purchases influenced by other channels. Our analytics tool's 1,104 undercounts because of iOS/browser tracking restrictions blocking a share of pixel fires. Going forward, I'll report Shopify net revenue as our single revenue KPI, and use blended MER (ad spend ÷ Shopify net revenue) instead of platform-reported ROAS to judge ad performance."

## Two things to verify before you lock this in

1. **Confirm your $296k Shopify figure is gross, not already net of refunds.** If the report you pulled is Shopify's "Net sales" report, refunds may already be subtracted — in that case don't subtract the $18k again (your number would be $296k, not $278k). Pull Shopify Analytics → Reports → Sales → **Net sales report** and check its returns/refunds line to be sure.
2. **Check whether any of the $18k in refunds were full-order refunds/cancellations for March orders.** If so, your 1,351 order count should probably be reduced by that number of cancelled orders too, since those aren't really "sales" anymore. If refunds were mostly partial (returns, discounts, price adjustments), 1,351 stands as-is.