# Spend Health Check — Harbor & Pine, November (B2C ecommerce)

## Headline

- **Combined paid media (Meta + Google): WATCH** — rests on rung 1 (break-even). Blended ROAS 2.79 clears break-even 2.38, but the margin is thin, unconfirmed by trend, and CAC already exceeds first-order contribution.
- **The "4.1" figure itself: not usable.** It's platform-reported ROAS summed across two platforms — the wrong variant, and non-additive by construction. Retire it before it drives the December 30% spend decision.

## Definitions record

Model: B2C ecommerce · Window: November, full closed month (settles in days for DTC — treated as lag-mature) · Spend lines: Meta + Google media spend only, as given ($140,000 total) — **not confirmed complete**, ask whether any other paid channel (TikTok, affiliate, retargeting network, agency fees) is missing from that total · New customer = 3,800, order-system-defined, assumed to exclude reactivations/renewals (not explicitly confirmed) · Revenue basis: order-system net revenue, $390,000 (net of refunds — the correct anchor per this skill) · Contribution margin: 42%, source and whether it already reflects Black Friday/Cyber Monday discounting not confirmed — November contains BFCM, which is a real margin-compression risk this figure may or may not capture · History: **0 prior periods supplied** — this is the biggest gap in the run.

Deleted from this run for lack of data: fully-loaded CAC (no salary/agency allocation given), payback and cohort CAC (not a subscription/repeat-cohort business as described), POAS as a standing metric (would need it recomputed every period, not just this one). Promote next period: **own trailing history** (4-8 months, same definition) — right now the verdict cannot distinguish "stable" from "one good/bad month," which is the single highest-value thing to add.

## Metric table

| Metric | Variant | Value | Window | Source |
|---|---|---|---|---|
| Meta-reported ROAS | platform-reported | 3.88 (310,000 ÷ 80,000) | Nov | Meta Ads Manager |
| Google-reported ROAS | platform-reported | 4.42 (265,000 ÷ 60,000) | Nov | Google Ads |
| "Combined" 4.1 | **sum of two platform-reported figures** | 4.11 (575,000 ÷ 140,000) | Nov | Meta + Google, summed |
| Blended ROAS (= MER, no other marketing costs disclosed) | total net revenue ÷ total paid spend | **2.79** | Nov | order system revenue ÷ Meta+Google spend |
| Break-even ROAS | 1 ÷ contribution margin | **2.38** | — | own margin data (0.42) |
| Blended CAC | total paid spend ÷ all new customers | **$36.84** | Nov | finance + order system |
| First-order allowable CAC | AOV × contribution margin | **$32.76** | — | own margin data ($78 × 0.42) |
| Net contribution after paid spend | (net revenue × margin) − spend | **$23,800** | Nov | derived |

## Comparison ladder

**1. Break-even (rung 1) — the number that should drive the December call.**
Break-even ROAS = 1 ÷ 0.42 = **2.38**. Actual blended ROAS = 390,000 ÷ 140,000 = **2.79**. That clears break-even, but the headroom is only ~17% (2.79 vs 2.38) — not the ~72% headroom the 4.1 figure implied (4.1 vs the same 2.38 break-even). Separately, blended CAC ($36.84) sits **above** first-order allowable CAC ($32.76) by $4.08: the first purchase alone doesn't recoup acquisition cost. Profitability on this cohort depends on repeat purchases, and no repeat-rate/LTV data was supplied — this is exactly the contingency this skill flags as something to name explicitly, not assume away.

**2. Own trailing history (rung 2) — not available.**
No prior months were supplied. Without it, "flat or improving trend" — a required condition for a *healthy* verdict — cannot be confirmed. This is the main reason the verdict below is watch, not healthy: the arithmetic clears break-even today, but there's no evidence the account isn't three months into a slide, the way the worked Maple & Loam example (same skill, same shape of numbers: 45% margin, MER 2.5 vs break-even 2.22) turned out to be.

**3. External benchmark (rung 3) — context only, never the verdict.**
Median ecommerce blended ROAS is **2.04** (Triple Whale, 2025, 18,000+ brands, platform-instrumented, vendor-measured). Harbor & Pine's 2.79 sits above that median — mildly reassuring context, nothing more. It does not offset the missing rung 2, and it says nothing about the CAC-vs-first-order-contribution gap.

Separately worth naming, because the coincidence invites confusion: the "4:1 ROAS" figure that shows up everywhere has no traceable author, is not from the Nielsen study it's often pinned to, and is simply break-even at a 25% margin retroactively declared a target (First Page Sage / benchmark-sources.md). Harbor & Pine's real break-even at 42% margin is 2.38, not 4.0 — so even a *correctly computed* 4.1 would have been measuring the wrong threshold.

## Why the 4.1 fails as a health metric — the actual sanity check

1. **Wrong variant.** Meta's $310K and Google's $265K are each platform-attributed — modeled/claimed conversions, not caused ones. Summing them and calling it "combined ROAS" treats two non-additive numbers as additive.
2. **The sum exceeds total company revenue.** $575,000 in combined *paid-attributed* revenue is **47% higher** than the $390,000 in *total* net revenue the order system recorded for the entire month — across every channel, paid and organic combined. Two platforms are jointly claiming credit for more revenue than the business actually did. That's not a rounding issue; it's the exact pattern documented in vendor client audits showing Meta and Google jointly claiming 150–200% of real revenue through double-counted attribution (AdBeacon, vendor client audits — indicative, not an independent audit), and consistent with the direction (if not magnitude) of Gordon, Zettelmeyer, Bhargava & Chapsky's 2019 Marketing Science RCT finding that observational attribution overstates true lift by roughly 7–9x.
3. **The correctly anchored number is 2.79, not 4.1.** Using order-system net revenue over the same $140,000 spend — the money-anchored, non-double-counted figure — gives 2.79. That's 32% lower than the number the December budget increase is being sized against.

## Verdict and evidence gate

Gate: variant established — yes, once corrected to blended ROAS · margin known — yes (42%) · window ≥ lag — yes, full closed month · channels complete — **unconfirmed**, only Meta + Google spend disclosed, ask whether that's the full paid total.

**Verdict: WATCH.** Above break-even (2.79 vs 2.38) on the corrected, order-system-anchored figure, but: (a) no trailing history exists to confirm the trend is flat or improving rather than deteriorating, (b) blended CAC already exceeds first-order contribution, making the result contingent on a repeat-purchase rate nobody has quantified, and (c) November includes Black Friday/Cyber Monday, a period documented to compress per-order contribution margin 40–60% — worth confirming the 42% figure isn't a pre-BFCM number about to look optimistic for a December read that also carries holiday promotions.

Named next question: does the 42% margin hold up when BFCM orders are isolated, and does repeat-purchase revenue close the $4.08 gap between CAC and first-order contribution? Get 4-8 months of blended ROAS/CAC on this same definition before the next check — that alone would very likely move this from watch to a confident healthy or catch a real problem early.

## Handoffs

- Sizing the actual December budget move, and the go/no-go threshold for it, given only a 17% headroom over break-even — not this skill's call: `mbfinotti/advertising-skills@ad-spend-guardrails`.
- Deciding how a +30% increase splits across Meta vs. Google (their marginal, not average, ROAS is what a scale-up actually tests): `mbfinotti/advertising-skills@ad-spend-allocation`.
- Reconciling why Meta + Google jointly claim 147% of total company revenue — a formal attribution reconciliation (incrementality testing, UTM-based dedup) would give a cleaner number than the order-system-total proxy used here: `mbfinotti/advertising-skills@ad-attribution-gap`.