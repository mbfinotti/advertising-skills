## Verdict up front

Don't tighten the ladder. Sooner and bigger discounts is the wrong direction — it will push abandonment past 79%, not below it. Here's why, and what to build instead.

## What's actually happening

Your ladder puts a discount on **every** stage (10% / 15% / 20%), triggered purely by elapsed time since abandonment, same audience, same message, just a bigger number. That's the exact failure pattern known as **discount-trained abandonment**:

> Customers learn that abandoning a cart reliably produces a coupon within 24 hours. So they start abandoning on purpose, wait for the email/ad, and buy at a discount they'd have paid full price for anyway.

Your timeline confirms it: abandonment was 74% before the ladder, and has climbed to 79% over the three months the ladder has been running — while "the coupon ads convert great." Both facts are consistent with the same mechanism: you're not recovering carts, you're teaching shoppers to create carts they intend to abandon, and the platform is reporting those redemptions as wins. Retargeting is the case most prone to this — it targets exactly the people most likely to buy anyway, and observational lift numbers for it have been shown to overstate true incremental lift by roughly 7–9.5x (Gordon, Zettelmeyer et al., 2019, 15 large-scale RCTs). "Converts great" on platform-reported numbers is not evidence it's converting anyone who wouldn't have bought regardless.

Making the first discount bigger and faster doesn't fix this — it shortens the training loop and raises the reward, which should accelerate the trend you're already seeing, not reverse it.

## The rule you're breaking

A discount ladder should have **exactly one** discount rung, on the **last** stage only. Every earlier touch should do a different job — reminder, then proof/objection-handling — so a shopper who's going to buy without a discount gets the chance to, before you ever offer one. Re-showing the same offer louder is the weakest possible stage design: if they saw it and didn't act, the angle was wrong, not the size of the number.

## Data gap, named as the skill requires

I don't have your time-to-conversion lag distribution, so I can't derive exact day boundaries from your own converters — the right move, not a guess. Pending that export (GA4/Shopify "time to purchase after cart" report), I'm using a **named proxy**: general DTC e-commerce lag curves (Baymard-style benchmarks) where the bulk of recoverable carts convert in 24–72 hours and the tail is mostly dead by ~3 weeks. **Treat every window below as provisional until you pull the real report.**

## The corrected ladder

| Stage           | Trigger                                | Window (proxy)         | Message intent / offer                                                                                                  | Concepts |
| --------------- | -------------------------------------- | ---------------------- | ----------------------------------------------------------------------------------------------------------------------- | -------- |
| S1 Reminder     | Cart/checkout start, no purchase       | 0–2 d                  | Dynamic ad, exact item, **no discount**                                                                                 | 3        |
| S2 Objection    | S1 aged out, still no purchase         | 3–7 d                  | Shipping/returns/guarantee, materials/quality proof (cookware-specific: induction-compatible, oven-safe temp, warranty) | 3        |
| S3 Social proof | S1/S2 aged out, still no purchase      | 8–14 d                 | Reviews, UGC, before/after cooking content                                                                              | 3        |
| S4 Last-call    | Any above, aged out, still no purchase | 15–21 d                | **The only discount rung** — one offer, not an escalating one (e.g. flat 15%), plus urgency                             | 3        |
| Win-back        | Purchasers                             | 30–90+ d post-purchase | Replenishment/complementary cross-sell — separate budget, not part of this ladder                                       | 3        |

Notes:

- Collapse to fewer stages if your real lag data shows 80%+ of converters buy inside 7 days (likely, for cookware) — you may only need Reminder → Objection → Last-call.
- Vary the S4 offer over time (e.g. rotate between % off, free shipping, a bundled accessory) so it isn't a fixed, learnable trigger.

## Exclusion map (this is likely your other gap)

Check now whether your current ladder has this — if it doesn't, that's independently inflating your CPMs regardless of the discount question:

- `RTG_S1_0-2` excludes `EXCL_PURCH_180`
- `RTG_S2_3-7` excludes `RTG_S1_0-2`, `EXCL_PURCH_180`
- `RTG_S3_8-14` excludes `RTG_S1/S2`, `EXCL_PURCH_180`
- `RTG_S4_15-21` excludes all above, `EXCL_PURCH_180`, **and `EXCL_REPEAT_ABANDON`** (3+ abandonments/90d, no purchase) — this is the specific fix for people farming the coupon
- Converter exclusion window: 180 days

If your current 10/15/20 ladder doesn't already exclude purchasers, some share of your "great converting" ads are showing discounts to people who already bought at full price — pure margin waste on top of the training problem.

## Cap sheet

Meta/Google don't expose a hard cap field on conversion objectives — use decay proxies against a 7-day rolling baseline:

- S1–S3: act at >5–6/week per person, or CTR down 15–20%+, or CPM up 10%+
- S4: tighter, 3–4/week — it's the smallest, most fatigue-prone pool

## Measurement — do this before touching the ladder further

1. **Run an audience holdout now, before redesigning**: withhold 15–20% of S4 (your current 20%-off stage) from all coupon ads for 4–6 weeks. If purchase rate in the holdout is close to the exposed group, that stage's platform ROAS is fiction — you're paying margin to intercept sales that were coming anyway. This tells you how much of "the coupon ads convert great" is real.
2. Track abandonment rate, new-vs-returning purchaser mix, and repeat-abandoner count monthly — repeat-abandoner count is your direct read on whether training is happening.
3. Expect **a quarter**, not a week, to un-train behavior once the single-discount-rung version launches. Behavior that took three months to teach doesn't reverse in the next billing cycle.

## Before you build any of this

- Confirm cart/checkout-start and purchase events are both firing cleanly — retargeting audiences are worthless without it.
- Pull the real time-to-conversion export and re-derive the windows above against your own converters, not the proxy.
- Route the actual ad copy for S1–S4 through your ad-copy/creative-brief process — this plan sets intent per stage, not the words.
- Route total retargeting-vs-prospecting budget split separately; don't just pour the S1–S3 budget (net new, since today it's all discount) into more discounting.

**Bottom line**: your instinct — sooner, bigger — optimizes the exact lever that's causing the problem. The fix is fewer discount touches, not more: one discount, last stage, varied and capped, with real work (reminder, objection-handling, proof) done in the stages before it.
