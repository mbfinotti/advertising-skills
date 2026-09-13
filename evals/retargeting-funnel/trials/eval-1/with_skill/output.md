# Emberline Retargeting Funnel — Revised Plan

## Diagnosis of your sketch first

Your 5-stage draft has the same shape as a documented failure pattern (uniform 0-30/0-60/0-180 windows regardless of depth): every stage overlaps every other stage (a cart abandoner sits in stages 1, 2 _and_ 3 simultaneously → ad sets bid against themselves), no converter exclusion is stated, and the windows ignore your own lag data. With 86% of purchases landing inside 5 days, a 30-day "all visitors" window spends most of its budget on people who were never going to convert from that visit. That's fixable — here's the corrected version.

## Basis for the windows (no proxy needed — you have real data)

Your GA4 lag report: 58% @ 1 day, 86% @ 5 days, 96% @ 12 days, negligible after 30 days.

- **80th-percentile edge** (interpolating between 58%@1d and 86%@5d) lands at ~day 4 → this is the hot-window boundary.
- The jump to 96% by day 12 sets the warm-window boundary.
- Day 30 is a hard wall — no conversion-ladder stage should run past it. Anything targeting purchase intent beyond day 30 is win-back, not retargeting.

This is a fast, impulse-leaning funnel (closer to your median online session behavior than a considered purchase) — closer to a 4/12/30 structure than the 30/60/180 you sketched.

## Stage table

| Stage                  | Inclusion rule                                                    | Window                            | Message intent / offer                                                                                    | Concepts |
| ---------------------- | ----------------------------------------------------------------- | --------------------------------- | --------------------------------------------------------------------------------------------------------- | -------- |
| **S1 Deep-intent**     | Cart or checkout start, no purchase                               | 0-4 days                          | **Reminder** — dynamic ad of the exact item(s) left behind. No discount.                                  | 3        |
| **S2 Product viewer**  | Viewed a product page, no cart                                    | 0-12 days                         | **Social proof** — reviews, scent-profile UGC, gifting angle                                              | 3        |
| **S3 General visitor** | Any session, no product view                                      | 0-20 days                         | **Objection handling** — shipping cost/threshold, returns, clean-burn/soy-wax claims, burn-time guarantee | 3        |
| **S4 Last-call**       | Union of S1/S2/S3 members aged past their own window, no purchase | Aged-out, capped at day 30 total  | **Incentive + urgency** — the only discount rung                                                          | 3        |
| **S5 Win-back**        | Purchasers                                                        | 45-120 days _after purchase date_ | **Replenishment / new drops / referral** — separate budget, outside the acquisition ladder                | 3        |

Notes on the design:

- **S1 optional split:** if you track checkout-start as a distinct GA4 event, you _can_ split S1 into "Checkout abandoners" (0-3d, reminder + shipping/payment objection — checkout drop-off is usually a cost-surprise or payment-friction problem) and "Cart abandoners, no checkout" (0-4d, pure reminder). Only do this once you've checked the checkout-only pool clears ~1,000 people in a rolling 3-day window on your primary platform — on the volumes you've given me, that pool is plausibly thin (see size check below), so merged is the safer default.
- **S3 starts at day 0, not day 5** — the exclusion map (below), not a delayed start date, is what keeps it from double-targeting people already in S1/S2. Delaying the window just loses reach for no benefit.
- **S5's 45-day start** is deliberate: candles take weeks to burn through, so hitting a buyer with "restock" messaging in week 1 is premature and reads as spammy. 45-120 days is a reasonable first pass — tighten it once you have actual repeat-purchase-interval data from your order history (this is a named assumption, not derived from data you gave me — replace it).

## Exclusion map

Naming convention: `RTG_<depth>_<window>` / `EXCL_<what>_<window>`.

| Stage                     | Excludes                                                                                                                                                  |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `RTG_DEEP_0-4`            | `EXCL_PURCH_90`                                                                                                                                           |
| `RTG_PRODUCT_0-12`        | `RTG_DEEP_0-4` (fresher/deeper), `EXCL_PURCH_90`                                                                                                          |
| `RTG_VISITOR_0-20`        | `RTG_DEEP_0-4`, `RTG_PRODUCT_0-12`, `EXCL_PURCH_90`                                                                                                       |
| `RTG_LASTCALL_AGEDOUT-30` | all three above (their fresh windows), `EXCL_PURCH_90`, `EXCL_REPEAT_ABANDON_2X` (2+ prior last-call exposures with no purchase — stops discount-farming) |
| `RTG_WINBACK_45-120`      | `EXCL_PURCH_45` (a repeat buyer inside 45 days shouldn't get a "come back" ad)                                                                            |

**Converter exclusion window: 90 days**, sized as a candle-repurchase-cycle proxy (sector-typical, not derived from your data — confirm against your own repeat-purchase-interval report if you have one). Too short re-ads recent buyers; too long quietly shrinks your prospecting pool as the buyer list grows.

## Size check (illustrative — replace with your real GA4 funnel report)

I don't have your page-type breakdown, so these are estimates from category-typical rates, flagged as such:

- **S1 (deep-intent, 0-4d):** assuming ~6% add-to-cart rate on 140k sessions ≈ 8.4k/month, a 4-day rolling slice minus purchasers lands in the low hundreds to ~1k. This is close to the practical floor (~1,000 on Meta/Google, 1,000 hard floor on TikTok) — **verify before launch**; if it's under floor, widen to 0-5/0-6 days first (not merge yet — collapse order is widen → broaden trigger → merge → single pool).
- **S2 (product viewer, 0-12d):** comfortably clears every platform floor at your traffic level.
- **S3 (general visitor, 0-20d):** largest pool, no floor risk.
- **S4 (last-call):** inherits from S1-S3, clears floor.
- **S5 (win-back, 45-120d post-purchase):** ~1,900 orders/month × ~2.5 months of rolling window ≈ 4-5k — clears floor easily. Build this as a purchase-event or CRM/email-list audience, not a generic pixel window, so it survives Safari's 7-day cookie cap.

## Cap sheet

| Stage              | Cap / proxy                                                                                                        | Review cadence                                                                   |
| ------------------ | ------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- |
| S1 Deep-intent     | Proxy 6-7/week (Meta has no cap field on conversion objectives) — act on CTR −15-20% or CPM +10% vs 7-day baseline | Every 2-3 days                                                                   |
| S2 Product viewer  | Proxy 4-5/week                                                                                                     | Weekly                                                                           |
| S3 General visitor | Proxy 3-4/week (lightest signal — avoid a "stalking" feel)                                                         | Weekly                                                                           |
| S4 Last-call       | Proxy 4-5/week                                                                                                     | Every 3-4 days (short-lived, discount-bearing — watch negative feedback closely) |
| S5 Win-back        | 1-2/week (paced over months, not days)                                                                             | Monthly                                                                          |

## Measurement plan

- **Per stage:** spend, reach, frequency, CTR, CPM, platform CPA, new-vs-returning share.
- **Blended sanity metric:** monthly revenue ÷ total marketing spend — drops the attribution layer entirely, tracked alongside platform ROAS.
- **Incrementality test:** 15% audience holdout on **S1** and **S4** — the two stages most likely to just intercept people who'd have bought anyway — for **4 weeks** (your whole conversion cycle resolves by day 30, so 4 weeks covers a full cycle plus buffer). If Meta's Experiments tool is available on your account, use its built-in Conversion Lift test instead of a manual holdout — same design, less setup. **Decision rule:** if S1's holdout-measured lift is indistinguishable from zero, fold that budget into prospecting or email regardless of what its platform ROAS says.

## Design gate

- [x] Stage boundaries derived from your own lag data, not defaults.
- [x] Every stage mutually excludes deeper/fresher stages and converters.
- [x] Discount confined to S4 only.
- [x] Cap-proxy with decay signals defined per stage.
- [x] Incrementality test scheduled with design, holdout share, decision rule.
- [ ] **Open — you need to confirm:** tracking on cart-start vs checkout-start as separate events; whether a discount policy actually exists (if not, S4's rung becomes a hard direct ask — e.g. free shipping or a gift-with-purchase instead); real page-type/funnel-step volumes to replace the size-check estimates above; a converter-suppression audience already live on each channel.

## Worth knowing

Byron Sharp's Ehrenberg-Bass position treats heavy retargeting as a ceiling, not a growth lever — at 140k sessions/month most of your volume should still be prospecting, with retargeting spend capped by pool size × frequency ceiling rather than by ambition. Ben Heath's alternative view says skip the 5-stage grid entirely and run one combined warm pool at max window — cheaper to build, and it's the right call if S1 doesn't clear its floor even after widening. Keep the stratified version above as the default; fall back to the single pool only if the size check forces it.

**Handoffs:** actual ad copy for these 3-per-stage concepts → `ad-copy-variants` / `ad-creative-brief`, run any drafted copy through a humanizer pass before it ships; budget split across these stages and prospecting → `ad-spend-allocation`; confirm tracking is actually firing on cart/checkout events before building any audience → `ad-conversion-tracking`.
