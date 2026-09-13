# Merrow & Finch — 4-Cell Concept Test: Redesigned Plan

## Bottom line

"Run it 10 weeks instead of 4" doesn't fix your actual problem. It trades one blind spot (not enough budget) for another (not enough _purchase_ events, no matter how long you run it). The add-to-cart event you mentioned almost as an afterthought — "not sure that matters" — is the thing that actually makes this test work. Here's the math and the fix.

## The math nobody ran

$500/day ÷ 4 cells = **$125/day/cell**.

| Metric       | Rate     | Volume/day/cell | 4 weeks (28d)         | 10 weeks (70d)        |
| ------------ | -------- | --------------- | --------------------- | --------------------- |
| Purchases    | $180 CPA | 0.69            | **19 purchases/cell** | **49 purchases/cell** |
| Add-to-carts | $12/ATC  | 10.4            | **292 ATC/cell**      | **729 ATC/cell**      |

Standard practice for a reliable read on a binary conversion event (used by every CRO platform — Optimizely, VWO, CXL): **~100 conversions/arm is the bare floor**, below which you can't distinguish signal from noise except for huge effects; **250–400/arm** is where you get a defensible read on a realistic 15–25% lift.

Run the purchase-level math forward at $125/day/cell:

| Target purchases/cell | Days needed | Time needed   |
| --------------------- | ----------- | ------------- |
| 100 (bare floor)      | 144         | **~21 weeks** |
| 200 (workable)        | 288         | **~41 weeks** |
| 350 (robust)          | 504         | **~72 weeks** |

Ten weeks gets you 49 purchases/cell — still below the bare floor. **You could triple your proposed timeline and still not have a real purchase-CPA read.** This isn't a duration problem, it's a starved-metric problem: at this spend level, "purchase" as the read metric doesn't work at any reasonable timeline.

Now run the same math on add-to-cart:

| Target ATC/cell  | Days needed | Time needed   |
| ---------------- | ----------- | ------------- |
| 100 (bare floor) | 9.6         | **1.4 weeks** |
| 250 (workable)   | 24          | **3.4 weeks** |
| 350 (robust)     | 33.6        | **~5 weeks**  |

That's the whole plan in one line: **swap your primary decision metric from purchase to add-to-cart, and you get a robust, statistically defensible read in 5 weeks instead of never.**

## The design: two phases, same $500/day, no ask to Finance

### Phase 1 — Diagnostic (5 weeks, ~Sep 14 – Oct 18)

- **Split:** 25/25/25/25 across Control / A / B / C, run **simultaneously** (not sequential — see guardrails).
- **Primary metric:** add-to-cart rate (cost per ATC vs. control). This is what you formally test and act on.
- **Secondary/guardrail metric:** ATC→purchase conversion rate per cell. Purpose: catch a concept that pumps ATC with "browsers, not buyers" (great ad, bad landing/product fit) — high top-of-funnel but a collapsing downstream rate.
- **Reported but not decisioned on:** raw purchase CPA per cell. At ~19-24 purchases/cell it's directional color only — report it with a wide confidence interval, don't let anyone (including you) read it as a verdict.
- **Statistical test:** two-proportion z-test, each concept vs. control, on ATC rate.
- **Multiple comparisons correction:** 3 pairwise tests → Bonferroni-adjusted α = 0.05/3 ≈ **0.017** (or Benjamini-Hochberg FDR if you want less conservatism).
- **One formal read-out, at week 5.** Monitor dashboards weekly if you want, but don't act on interim numbers — no stopping/killing before the pre-committed checkpoint. Peeking and reacting early is how you talk yourself into noise.
- **Decision rule at week 5:**
  - Kill a concept only if it's _significantly worse_ than control (p < 0.017). Don't kill on "not significant" — 5 weeks isn't enough to safely conclude a concept that's merely inconclusive is actually bad (false-negative risk).
  - Flag anything with a materially lower ATC→purchase rate than control, even if ATC itself is up.

### Phase 2 — Confirmatory (4–5 weeks, ~Oct 19 – Nov 15ish)

- **Reallocate the same $500/day** to control + whatever survived Phase 1. Fewer cells, same budget → more $/cell → more purchase volume per cell than the diffuse 4-way split ever gave you.
- If **1 concept survives**: 50/50 split, $250/day/cell → 1.39 purchases/day → ~39 purchases/cell over 4 weeks (vs. 19 in the original 4-cell design). Combined with a statistically significant Phase 1 ATC lift and a stable downstream conversion rate, that's a defensible basis to ship — not classical p<0.05 on CPA, but a coherent, data-backed story.
- If **0 concepts beat control**: stop here. You've saved 4–5 weeks versus blindly running the full 10, and you have a clean, statistically sound "none of the three worked" result.
- If **2 concepts tie**: three-way split (control + 2), ~$167/day/cell, weaker but still better than Phase 1's diffuse read; pick based on secondary criteria (production cost, creative fatigue risk) if stats don't separate them.

**Total wall-clock: ~9–10 weeks — same ballpark as your original workaround, but front-loaded, with an early-kill option, and it actually produces a metric you can act on by week 5 instead of a purchase count that's still underpowered at week 10.**

## Guardrails

- **Run all cells concurrently for the entire test.** Never sequence cells one after another — that lets seasonality/day-of-week/platform drift masquerade as a concept effect. (I considered a sequential/switchback design to concentrate spend — it doesn't actually buy more total conversions per concept for the same total budget-days, and daily/weekly budget or creative swaps retrigger ad-platform learning phase, which tanks delivery efficiency for 3–7 days each time. Not worth it here.)
- **Novelty effect:** new creative often over-indexes in week 1 just from being unseen. Don't read week 1 alone; require the signal to hold through week 3+.
- **Attribution consistency:** same attribution window/model across all 4 cells for the whole test; check nothing platform-side (iOS ATT changes, algorithm updates) is scheduled to shift mid-test.
- **Creative fatigue:** watch week-over-week decay within a cell, not just cell-vs-cell. A concept that's strong in week 1 and fading by week 4 is a real signal, not noise — factor it into the Phase 2 decision.

## What you'll actually be able to say at the end

A statistically significant, Bonferroni-corrected winner (or non-winner) on add-to-cart efficiency by week 5, with a directionally consistent — but explicitly labeled non-significant — purchase CPA estimate by week 9–10. Be upfront with whoever reads this that "significant on purchase CPA" was never achievable at $500/day/4-cells in any timeframe short of ~9 months, so don't let the final readout get oversold as more definitive than the data supports.

Side benefit: this gives you a much better Finance conversation next quarter than a vague budget ask — "we validated concept X on add-to-cart at p<0.017 with zero incremental spend; closing the loop on purchase-CPA significance requires either ~8x the budget or ~9 months at current spend" is a number-backed case, not a request.
