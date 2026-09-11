# Emberline Retargeting Plan — Refined

## What the time-lag data actually tells you

Your curve (58% / 1 day → 86% / 5 days → 96% / 12 days → ~flat after 30) is a **blended curve across all visitors**, dominated by low-intent traffic. It's the right ceiling for broad audiences (Stages 1–2), but it will mislead you if applied uniformly to cart/checkout abandoners (Stages 3–4) — those visitors are further down the funnel and decay much faster than the blended average. And Stage 5 isn't a "time-to-convert" audience at all — it's a replenishment/LTV play with its own logic (candle burn time), not analytics-lag logic.

Two structural fixes apply to all five stages, independent of window length:

1. **Waterfall exclusions** — each stage must exclude everyone who qualifies for a more advanced stage (product viewer excludes cart abandoner; cart abandoner excludes checkout abandoner; all exclude buyers). Right now your plan has 4 overlapping "0-30 day" pools, meaning a checkout abandoner gets shown all five messages at once — wasted spend and a confusing mixed message.
2. **Front-load budget/frequency to match the decay curve, don't just cap the window.** A flat budget across "0-30 days" spends a third of its money on the ~4% tail after day 12. Weight spend ~70% into days 0–5, ~25% into days 6–12, ~5% as a thin tail beyond.

## Stage-by-stage

**1. All site visitors** (excl. product viewers, abandoners, buyers)
- Window: **0–14 days**, not 30. Day 14 already captures ~97%+ of realistic conversions for cold traffic; days 15–30 buy almost nothing and just fatigue the pixel.
- Budget shape: heavy 0–5, taper 6–14.
- Messaging: brand/category discovery — bestsellers, scent stories, UGC/reviews. No discount — this is cold, low-intent traffic; don't erode margin to buy a click that wasn't close to converting anyway.

**2. Product page viewers** (excl. abandoners, buyers)
- Window: **0–10 days**. More intent than Stage 1, so tighten it further — value is concentrated in days 0–3.
- Messaging: dynamic ads of the *exact* scent viewed, notes/ingredients, reviews for that SKU, "still deciding?" framing. Nudge with free-shipping threshold rather than a % discount — reserve real discounts for higher-funnel stages.

**3. Cart abandoners** (excl. checkout abandoners, buyers)
- Window: **0–7 days**, not 30. Cart recovery behavior decays in days, not weeks — a 30-day window mostly just annoys someone who already decided not to buy.
- Cadence: aggressive multi-touch days 0–3 (no discount yet — lead with trust signals/reviews and shipping-cost transparency, since price surprise is the #1 cart-abandon reason), single touch days 4–7 with a small time-limited incentive (5–10% off) to close out fence-sitters.

**4. Checkout abandoners** (excl. buyers)
- Window: **0–7 days**, cut way down from 60. This is your smallest, highest-intent, highest-value pool — 60 days of exposure just burns frequency on people who already declined at the last step.
- Cadence: hit hard in the first 48 hours across every channel available (retargeting + email/SMS if you have it). Messaging: remove the specific friction (shipping cost, delivery time, payment error), reassurance (secure checkout, easy returns), and a real incentive (10% off or free shipping) since this is the final nudge — you can afford the margin hit here far more than in Stage 1–2.

**5. Past buyers** — reframe from a single "0–180 day" blast into replenishment segments tied to candle burn time (~4–8 weeks of typical use), not the visit-to-purchase curve:
- **21–45 days**: "How's it burning?" check-in + cross-sell a complementary scent. No discount — this is relationship, not rescue.
- **46–90 days**: restock/new-arrivals nudge, loyalty-points reminder if you have a program.
- **91–180 days**: genuine win-back offer (bundle or meaningful discount) + gifting/seasonal angle — "we miss you."
- If you can tag gift purchases vs. self-use, split messaging on that axis too — gifting customers respond to occasion reminders (birthdays, holidays), self-use customers respond to replenishment cues.

## Net changes vs. your draft
- All windows shortened except Stage 5, which is restructured into sub-windows.
- Added mandatory exclusion waterfall so no visitor sees more than one stage's ads at once.
- Discounting pushed later in the funnel (none in Stages 1–2, incentive only kicks in mid-Stage-3 and in Stage 4) to protect margin on your ~1,900 orders/140k sessions (~1.4% conversion) — you don't need to buy back low-intent traffic with discounts it was never going to convert on anyway.