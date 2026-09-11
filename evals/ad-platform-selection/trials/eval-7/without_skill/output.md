## The consultant's plan has a scale problem and a technique problem — fix both before spending anything

**⚠️ Geo-lift holdout testing does not pair with retargeting, and it does not pair with your current traffic.** Worth unpacking before the budget breakdown, because it changes how you should spend the $6K.

### Why geo-lift + retargeting is the wrong combination

Geo-lift works by turning ads off in some regions (DMAs) and comparing sales trends against regions where ads stay on. It's designed for channels you can independently control *by geography and reach broadly* — prospecting, YouTube, podcast, OOH, direct mail. Retargeting doesn't fit that shape: it targets a specific pool of people who already visited your site (via pixel/cookie match), not a geography. You can't meaningfully "hold out a region" from a pixel-matched audience — the audience *is* the targeting logic, not the map. The standard incrementality method for retargeting is a **user-level holdout** (a % of the pixel-matched audience gets no ads, or gets PSA/ghost ads), not a geo experiment. Meta calls this a Conversion Lift study; it's the tool for this job, not geo-lift.

### Why geo-lift doesn't work yet regardless of channel

Geo experiments need statistical power, and power comes from volume. Rule of thumb in the ad-tech world: you want tens of thousands of dollars a month in test spend, split across enough matched geo pairs, sustained for weeks, to detect a lift signal above natural noise. At $6K/month total, splitting that across geo cells leaves every cell underpowered — you'd get a number, but not a trustworthy one.

The traffic side is worse. 900 visits/month is roughly 600-700 unique visitors. After stripping instant-bounces, your realistically remarketable pool is maybe **300-500 people**, and cart-abandoners are probably **10-30/month**. Ad platforms recommend 1,000+ people in an audience for stable delivery — below that you get high frequency, fast creative fatigue, and unreliable optimization. Layer a holdout split on top of a pool that small and each arm has essentially no statistical power. Even a simple retargeting holdout, done correctly, won't give you a readable signal for months at this volume.

**The honest sequencing is: grow traffic and pixel pool first, retarget lightly and cheaply while that happens, structure the holdout now so data accumulates, and don't expect a statistically meaningful readout — retargeting or geo — for 6-12 months.**

### Budget split for $6K/month

| Bucket | $/mo | Why |
|---|---|---|
| Prospecting (Meta + Google, broad/interest/lookalike) | $4,000 (67%) | At this traffic level, growing the top of funnel *is* the retargeting strategy — it's what grows the pool you'll retarget later. |
| Paid retargeting (Meta DPA + Google Display/YouTube remarketing) | $1,000 (17%) | More than this is wasted — you don't have enough people to absorb it without frequency fatigue. |
| Creative production / testing reserve | $600 (10%) | Small pool = creative burns out fast; budget to refresh it monthly. |
| Pinterest test | $400 (7%) | Handmade lighting is a visually-led, high-intent-shopping niche; Pinterest CPMs are typically cheap here and it doubles as prospecting + retargeting. Worth a real test, not just Meta/Google by default. |

Email/SMS (Klaviyo or similar) isn't in the media budget but is the highest-leverage "retargeting" channel you have at this scale — it's nearly free, isn't capped by minimum audience thresholds, and directly reaches cart-abandoners. Set up before any paid retargeting: welcome flow, browse-abandon, cart-abandon, post-purchase/replenishment. This will outperform paid retargeting per dollar until your pixel pool is much bigger.

### Retargeting setup (once prospecting is live and feeding the pixel)

1. **Segments**: viewed-product-no-cart, added-to-cart-no-purchase, purchased (for cross-sell/upsell) — three creative sets, not one blanket audience.
2. **Frequency cap**: 3-4 impressions/week/user. With a pool this small you will fatigue it in days without a hard cap.
3. **Window**: 30-day rolling for cart-abandoners, 60-90 day for browse-only — widen the window to keep the pool above the platform's efficient-delivery minimum.
4. **Catalog-based dynamic ads** (Meta DPA, Google Display remarketing) so creative refreshes itself against whichever SKU they viewed — reduces your creative-production burden against a small budget.
5. **Server-side tracking now, not later**: Meta CAPI + Google Enhanced Conversions. Your pool is already thin; losing more of it to iOS ATT/cookie loss is not affordable at this scale.
6. **Structural holdout**: carve out 10% of the retargeting audience as a permanent exclusion (PSA/no-ads group) from day one, even though you won't have enough conversions to read it for months. Setting it up now means you have clean, uncontaminated trend data whenever volume catches up — rather than trying to retrofit a control group later.

### Measurement, staged to your actual scale

- **Now – month 3**: GA4 + UTMs + CAPI as the tracking foundation. No formal lift test yet — track assisted conversions, view-through vs. click-through, and whether branded search/direct traffic trends up (early proxy signal that retargeting isn't just capturing people who'd have converted anyway).
- **Month 3-6**: revisit budget split once traffic is 3-5x current (aim ~3-5K visits/month). Retargeting budget can grow in proportion to pool size — not before.
- **Month 6-12**: once you're consistently clearing 50-100+ orders/month, the retargeting holdout (already running structurally) starts producing a readable lift number.
- **12+ months, or whenever monthly spend is meaningfully larger (think 5-10x today's $6K)**: geo-lift becomes viable, and at that point it should be tested against **prospecting**, not retargeting.

### The one-line version to send back to the consultant

Retargeting as a starting channel is defensible given your AOV and margin. Geo-lift as the measurement method for it, on day one, at $6K/month, is not — wrong tool for a pixel-based channel, and underpowered for your traffic regardless. Structural holdout now, real lift reads in 6-12 months, geo-lift once you're testing prospecting at real scale.