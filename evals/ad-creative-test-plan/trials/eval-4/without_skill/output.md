# Cartelle A/B Testing Program — 6 Months, 6 Variables

## Starting numbers

- Spend: $6,000/month → ~86 conversions/month at $70 CPA (43 per side of a 50/50 split).
- No incremental budget needed. Each test *is* your existing monthly spend, split 50/50 between control and variant.
- Total program: $36,000 over 6 months — your current run rate, restructured, not increased.

## The honest power problem

At 43 conversions per arm, a single 4-week test only reaches 95%-confidence, 80%-power on an effect of **~45% relative CPA change**. Formula (per test, using the conversion-split framework, p₀=0.5):

```
MDE (percentage-point split) = √[(z_α/2 + z_β)² × 0.25 / n]
n = 86 → MDE ≈ 15pp split (≈65/35) → ≈45% relative CPA swing
```

That's fine for variables you expect to move CPA hard (price visibility, CTA wording). It's not enough to reliably catch a 5–15% effect from a headline dash or a font swap. Two fixes, both built into the plan below:

1. **Split the metric by funnel stage.** Pure creative-attention variables (dash, font, background, model direction) act on click decisions, not purchase decisions. Use **CTR** as the primary metric there — thousands of impressions/day, real power to detect small effects in days, not weeks. Use **CPA/CVR as a secondary guardrail** on the same test, so a CTR "winner" that drags in unqualified clicks doesn't get shipped.
2. **Reserve CPA-as-primary for the variables where the whole point is self-selection** — price shown/hidden is exactly this: a CTR-only read would be misleading (hiding price can inflate curiosity clicks that never buy).

I don't have your actual CTR/impression volume, so the CTR side of this is a framework, not a finalized duration — send me your average daily impressions per ad and I'll tighten the "how many days to a CTR read" number. The CPA backbone below works with what you gave me.

## Test order — biggest hypothesized effect first, one exception for seasonality

| # | Variable | Primary metric | Why this slot |
|---|---|---|---|
| 1 | Price shown vs. hidden | CPA (funnel-critical, self-selection) | Largest expected business impact — run first |
| 2 | 'Shop Now' vs. 'Shop the Collection' | CTR, CPA guardrail | Moderate-large, well-documented lever |
| 3 | Model facing left vs. right | CTR, CPA guardrail | Moderate, normal-volume month |
| 4 | Headline with vs. without a dash | CTR, CPA guardrail | Weakest hypothesis — placed in the Dec/holiday slot to exploit the seasonal volume spike for extra power |
| 5 | Beige vs. off-white background | CTR, CPA guardrail | Subtle |
| 6 | Serif vs. sans-serif overlay font | CTR, CPA guardrail | Subtle, brand-perception more than performance — closes the program |

## Schedule (starting Mon Sep 14, 2026)

| Test | Dates | Spend split | Arm A conv. (est.) | Arm B conv. (est.) |
|---|---|---|---|---|
| 1. Price shown/hidden | Sep 14 – Oct 11 | $3,000 / $3,000 | ~43 | ~43 |
| 2. CTA text | Oct 12 – Nov 8 | $3,000 / $3,000 | ~43 | ~43 |
| 3. Model direction | Nov 9 – Dec 6 | $3,000 / $3,000 | ~43 | ~43 |
| 4. Headline dash | Dec 7 – Jan 3 | $3,000 / $3,000 | above baseline (holiday volume) | above baseline |
| 5. Background color | Jan 4 – Jan 31 | $3,000 / $3,000 | ~43 | ~43 |
| 6. Font | Feb 1 – Feb 28 | $3,000 / $3,000 | ~43 | ~43 |

Finishes Feb 28, 2027 — two-week buffer inside your six-month window. If test 1 or 2 wins and you implement it, baseline CPA drops, so later tests get more conversions per $3,000 arm than shown here — treat these as floor estimates.

## Decision rule (drop into a sheet each month)

```
p̂ = conversions_B / (conversions_A + conversions_B)
SE = √[p̂(1−p̂) / n]
95% CI = p̂ ± 1.96 × SE
```

- CI excludes 50/50 → **ship the winner**.
- CI doesn't exclude 50/50 but point estimate is ≥58/42 → **directional lean**, bank it, optionally extend 2 weeks if cheap to confirm.
- CI centered near 50/50 → **documented null**. Write it down, stop debating it internally. A null is a real result, not a failed test.
- No correction needed across the 6 tests — each answers an independent question. Do apply discipline *within* a test: no early stopping on a good-looking week-1 number (optional stopping inflates false positives).

## Guardrails — hold everything else constant

- Same audience, placements, bid strategy, and budget cap type across control/variant.
- Use your platform's native A/B tool (Meta Experiments / Google Ads Experiments), not two manually-built ad sets — it enforces non-overlapping audiences and gives you a built-in significance readout. Manual ad sets risk audience overlap contaminating the comparison.
- No site-wide promos, price changes, or other creative swaps during a test window — if a promo is planned, shift the test.
- Don't touch budget or targeting mid-test — it resets the delivery learning phase and biases results.
- Pre-register the hypothesis and primary metric before launch (you're doing that now, in this schedule) — don't pick the metric after seeing the data.
- Nov–Dec test (headline dash) runs through BFCM/Christmas. The simultaneous A/B design means seasonality hits both arms equally, so the comparison stays valid — just expect the absolute CPA numbers from that window to look seasonally distorted if you look back at them later.

## Learning repository (this is the actual long-term asset)

One row per test, kept forever, independent of whether the test "won":

| Field | Capture |
|---|---|
| Test # / Variable | |
| Hypothesis (stated before launch) | |
| Dates / Spend | |
| Conversions A / B, CTR A / B | |
| Split + 95% CI | |
| Verdict | Ship / Kill / Directional lean / Documented null |
| Confidence tier | Decision-grade / Directional |
| Surprises | anything that contradicts the hypothesis |
| Follow-up flag | re-test later at higher volume? feed into a future multivariate test? |

After all 6, write one summary paragraph: which axis (copy specificity, funnel qualification, visual attention) moved CPA, which didn't, and what that implies about where Cartelle's ad performance actually lives. That summary — not any single winning ad — is the deliverable that compounds.

Two things that would sharpen this further, whenever convenient: your actual daily impression volume (to lock exact CTR-read durations), and confirmation that "price shown/hidden" is an ad-creative change rather than a landing-page change — the guardrails differ slightly if it's the latter.