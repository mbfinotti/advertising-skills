# Spend Health Check — Bramblewick, October (B2C/ecommerce)

## Headline

- **Blended paid channels (Meta + Google + TikTok): WATCH, leaning UNHEALTHY** — rests on rung 1 (break-even) and rung 2 (own history). The MER you were handed ($0 TikTok) reads *healthy*; the moment TikTok's real spend is put back in, it reads *below break-even and accelerating downward*. The gap between those two readings is the actual finding.

## Why the $0 TikTok number can't be used as-is

A zero-filled channel is not a conservative placeholder — it silently deflates the spend denominator and inflates every ratio built on it. TikTok didn't stop costing money because the API token expired; the reporting pipe broke, not the ad account. Treating "no reporting" as "no spend" is the exact failure mode this method exists to catch.

The fix that actually resolves this — cheaper than anything below — is a finance/billing pull, not a benchmark estimate: **ask finance or pull the TikTok Ads billing/invoice record (or the card/payment-processor statement) for October.** That number exists independently of the reporting API token; the token only broke the performance-breakdown feed, not the charge. That's a same-day fix, not a modeling exercise. Everything below is the best defensible estimate *until that actual figure lands* — treat it as an interim read, not the final word.

## Definitions record

Model: B2C/ecommerce · Window: October, full month, ecommerce data settles within days so no lag-maturity issue · Spend lines: paid media only — Meta + Google + TikTok (no agency/tooling/creative spend given, so not included; flag this if Bramblewick's usual MER denominator has ever included those) · Revenue basis: order-system net revenue, $520,000 — correct basis per this method, not platform-attributed · Contribution margin: 44%, source and scope (CM before or after marketing costs) not confirmed — assumed to be the margin used for break-even math (CM2-style, pre-marketing), flag if it's actually CM3 · History: 6 prior periods (Apr–Sep), assumed same MER definition throughout — not confirmed, but no indication of a definition change.

**Missing data:** TikTok spend absent for the reporting window (token expired last 3 weeks of Oct; analyst zero-filled the full month). Channel size is known historically (~8% of paid spend) and is small relative to the whole, so it qualifies for renormalization rather than withholding — but this is an *estimate*, not a measured actual.

## Metric table

| Metric | Variant | Value | Window | Source |
|---|---|---|---|---|
| MER, as reported (zero-filled) | total revenue ÷ (Meta+Google+TikTok spend, TikTok=$0) | **2.31x** | October | order system + ad platforms, TikTok forced to $0 |
| MER, renormalized (TikTok ≈8% of paid spend) | total revenue ÷ (Meta+Google+ imputed TikTok) | **~2.13x** (range 2.08–2.17x for a 6–10% TikTok share) | October | order system + Meta/Google actuals + historical TikTok share |
| Break-even MER | 1 ÷ contribution margin = 1 ÷ 0.44 | **2.27x** | — | own contribution-margin data |
| MER, Apr–Sep (trailing) | same variant, monthly | 2.35 → 2.31 → 2.34 → 2.30 → 2.28 → 2.26 | Apr–Sep | order system + ad platforms |

## Comparison ladder

1. **Break-even — 2.27x.** The zero-filled reading (2.31x) clears it. The renormalized reading (~2.13x, full plausible range 2.08–2.17x) does not — every point in the range sits below break-even. This is arithmetic, not a judgment call: if TikTok spent anywhere near its usual share, October lost money on the marginal ad dollar.
2. **Own history — Apr–Sep.** Already deteriorating for 3 straight months before October: 2.30 → 2.28 → 2.26 (Jul–Sep). Mix-shift check: nothing in the Apr–Sep series suggests a channel-mix explanation for that decline — it reads as a genuine efficiency drift, not reallocation. The zero-filled October figure (2.31) would *break* that trend upward, which is itself a tell, since nothing changed operationally to explain a reversal — the only thing that changed is that a real cost got dropped from the math. The renormalized figure (~2.13) *extends and steepens* the decline: it's a larger single-month drop (~-0.13 to -0.18) than any month in the trailing six (largest prior move was -0.04).
3. **External benchmark — not used to set this verdict.** For context only: median ecommerce ROAS 2.04, TikTok-specific ROAS running ~1.4–2.25x (Varos/Billo 2025–2026, platform-instrumented). Not comparable variant-for-variant to MER and not needed here — rungs 1 and 2 already settle it.

## Verdict and evidence gate

Gate: variant established (yes, MER) · margin known (yes, 44%) · window ≥ lag (yes, ecommerce settles fast) · channels complete (**no — TikTok missing, renormalized rather than withheld, which is defensible since the channel is small and its historical size is known**).

**Verdict: Watch, with a strong lean toward Unhealthy pending the real TikTok number.** The reported figure (2.31x) clears break-even; the renormalized best estimate (2.08–2.17x) does not, and it lands on top of a trend that was already deteriorating for three consecutive months. Don't ship the zero-filled 2.31x as "healthy" to anyone — it's an artifact of missing a real cost line, not an improvement. Downtrend: **real, and understated by the sheet you were given.**

Next-period question, named explicitly: does actual TikTok spend (pulled from billing, not estimated) land inside the 2.08–2.17x range or outside it? That answer converts this from Watch to a hard Unhealthy-or-not call.

## Handoffs

- Get the actual October TikTok spend from billing/invoices (independent of the broken API token) and rerun this check with real numbers — that alone resolves the gate, no skill needed.
- If the actual number confirms MER below 2.27x break-even → `mbfinotti/advertising-skills@ad-account-diagnostic` to find out why Meta/Google efficiency has been sliding for three straight months even before TikTok is added back.
- If a pause/reallocation decision follows from that diagnosis → `mbfinotti/advertising-skills@ad-spend-guardrails` (thresholds) and `mbfinotti/advertising-skills@ad-spend-allocation` (where the budget moves), not this check.