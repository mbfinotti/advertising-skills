# Spend Health Check — Ferndale Goods, July 2026

## Headline

- **Blended paid media / overall marketing spend: UNHEALTHY** — rests on rung 1 (break-even) and rung 2 (7-month own history), not rung 3. MER has run below the business's own break-even every month since January and has declined for 7 consecutive months. The 4.6 and "beats industry standard" reads are platform-reported ROAS and folklore respectively — neither is money-anchored, and neither is used to set this verdict.

## Definitions record

Model: B2C/ecommerce · Window: July 2026, monthly (settles within days — no lag-maturity issue for this model) · Spend lines: paid media ($96,000) + agency fees & creative production ($14,000) = $110,000 total marketing spend, media-only spend also tracked separately · New customer / CAC: **not computable this run** — no order count, new-customer count, or AOV was provided, so no CAC variant (blended, new-customer, or paid) could be established · Revenue basis: order system, net (stated as "net revenue," treated as net of refunds/cancellations) · Contribution margin: 38%, after COGS, shipping, and payment fees (this is a CM2-style margin — it does not yet net out marketing spend, which is the correct input for the break-even formula below) · History: 7 periods available (Jan–Jul), same MER definition throughout, no stated methodology change.

Deleted from this run: CAC family (blended/new-customer/paid/fully-loaded) — no customer counts supplied. This is the highest-value variant to promote next period; it's a near-zero-effort pull once new-customer count comes out of the order system, and it would let a real allowable-CAC / payback read sit alongside the MER read.

## Metric table

| Metric | Variant | Value | Window | Source |
|---|---|---|---|---|
| Blended ROAS | net revenue ÷ paid media spend | 240,000 / 96,000 = **2.50** | July 2026 | order system + paid spend |
| MER | net revenue ÷ total marketing spend | 240,000 / 110,000 = **2.18** | July 2026 | order system + finance (media + agency + creative) |
| Break-even ROAS / MER | 1 ÷ contribution-margin rate | 1 / 0.38 = **2.63** | — | own margin data |
| "Combined ROAS" | platform-reported (Meta + Google dashboards, summed) | 4.6 | July 2026 | ad platform dashboards — attributed, not money-anchored |
| CAC (any variant) | — | **not computable** | — | new-customer/order count not provided |

## Comparison ladder

**1. Break-even (rung 1) — MER fails it.** At a 38% contribution margin, break-even MER/ROAS is 2.63. July's MER is 2.18 — about 17% below break-even. Even blended ROAS (2.50, the narrower media-only cut) sits below break-even by ~5%. On the fuller cost base (media + agency + creative) — the one that matters for a scaling decision, since agency/creative is 14.6% of media spend and therefore material enough that MER, not blended ROAS, is the number to act on — Ferndale lost money on paid acquisition in July by arithmetic, not opinion.

**2. Own history (rung 2) — confirms it, doesn't just suggest it.**

| Month | MER | Δ vs prior |
|---|---|---|
| Jan | 2.62 | — |
| Feb | 2.55 | −0.07 |
| Mar | 2.48 | −0.07 |
| Apr | 2.41 | −0.07 |
| May | 2.33 | −0.08 |
| Jun | 2.24 | −0.09 |
| Jul | 2.18 | −0.06 |

Break-even is 2.63. Every single one of these 7 months sits at or below it — January (2.62) was already a hair under water, and the line has fallen every month since with no interruption. This isn't a one-bad-month blip and it isn't a mix-shift artifact you can wave away: no channel-level breakdown was provided to run the mix-shift check, but that check would only explain *why* MER is falling, not change the fact that it's been under break-even for 7 straight months. A sustained deteriorating trend that has been below break-even the whole visible history is exactly the rung-2 condition for "unhealthy," not "watch."

**3. External benchmarks (rung 3) — context only, and both of your cited figures are being misread.**

- Your "combined ROAS 4.6" is **platform-reported ROAS**, summed across Meta and Google. Two problems, not one: (a) platform-reported ROAS is attributed/claimed value, not caused revenue — the RCT literature (Gordon, Zettelmeyer, Bhargava & Chapsky, 2019, *Marketing Science* 38(2), 15 Facebook RCTs) found observational attribution overstating true lift by roughly 7–9.5x; and (b) *summing* two platforms' self-reported ROAS specifically reproduces the double-counting problem documented in vendor client audits (AdBeacon — indicative, not independently audited) where Meta and Google jointly claim 150–200% of real revenue between them. A "4.6 combined" is close to the textbook shape of that artifact. Your money-anchored numbers (order-system revenue ÷ real spend) are 2.50 and 2.18 — less than half the dashboard figure.
- "4:1 industry standard" has no traceable author and is not a Nielsen finding (often misattributed to one). It is simply break-even at a 25% contribution margin, retroactively declared a target. Ferndale's margin is 38%, so the real, business-specific break-even is 2.63 — lower than folklore's 4.0, and Ferndale is *still* under it.
- "Ecommerce median is around 2" is directionally right and traceable: Triple Whale 2025, 18,000+ ecommerce brands, vendor-instrumented, median blended ROAS **2.04**. Ferndale's blended ROAS (2.50) sits above that median — but this is rung 3, the weakest evidence, and it measures blended ROAS, not MER. Being above a published median while sitting below your own break-even for 7 straight months is exactly the trap this method exists to catch: "above median" and "losing money by arithmetic" are not mutually exclusive, and rung 3 never overrides rungs 1–2.

## Verdict and evidence gate

Gate: variant established (y — MER and blended ROAS both defined from order-system revenue and labeled spend totals) · margin known (y — 38%) · window ≥ lag (y — ecommerce, monthly, settles in days) · channels complete (y — paid spend and total marketing spend are already given as single totals, nothing to renormalize).

**Verdict: unhealthy.** Below the business's own break-even (2.63) on MER (2.18) and even on the narrower blended ROAS (2.50), with a 7-consecutive-month deteriorating trend that has never cleared break-even in the available history. This rests on rungs 1 and 2 together, not on the 4.6 dashboard figure or on either folk benchmark you quoted.

## Folklore appendix

- "4:1 ROAS" — no traceable author, often misattributed to a 2016 Nielsen study that makes no such claim. It's simply break-even at a 25% margin, retroactively treated as a target. Ferndale's own break-even, from its actual 38% margin, is **2.63** — use that number, not 4.0.

## Handoffs

- **Do not scale next month on this data.** Setting a floor/kill-switch before any scale decision → `mbfinotti/advertising-skills@ad-spend-guardrails`.
- If guardrails clear it for a smaller test rather than a scale, budget movement between channels/campaigns → `mbfinotti/advertising-skills@ad-spend-allocation`.
- Finding *why* MER has fallen every month for 7 months (creative fatigue, CPMs, funnel mix, audience saturation) → `mbfinotti/advertising-skills@ad-account-diagnostic`.
- Reconciling the 4.6 platform figure against the 2.18 money-anchored MER for any internal reporting/board use → `mbfinotti/advertising-skills@ad-attribution-gap`.
- Next period: pull new-customer counts from the order system to unlock blended CAC and a real payback read — near-zero effort, currently the biggest gap in this analysis.