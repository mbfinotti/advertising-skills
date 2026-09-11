# Spend Health Check — Loopwell, last month (single-month read)

## Headline

- **Pro plan segment: Healthy** — rests on rung 1. Payback ≈5.6 months, well clear of every reference point, but rung 2 (trend) unavailable this run.
- **Basic plan segment: Watch** — rests on rung 1, contingent. Payback ≈36.9 months — the plan only breaks even if customers stay ~3 years, and retention data to confirm that isn't in hand.
- **Blended figure: context only, not a verdict.** $310 CAC / 10.3‑month blended payback is the flattering number the mislabeled denominator and the plan-mix blend both produce — neither survives Step 1 or the per-plan discipline.

## Definitions record

Model: self-serve subscription SaaS, treated with the B2C-style payback lens (no sales funnel/SQLs exist to measure, so the B2B cost-per-SQL framework doesn't apply here) · Window: last calendar month, single period · Spend lines: $93,000 total marketing spend, assumed acquisition-directed (not split into new-vs-winback campaigns — **flagged gap**, see below) · New customer = billing's "new customer" **minus** 60 reactivations/annual renewals → **240 true new customers** (mandatory correction for a subscription business, Step 1) · Revenue basis: plan list price, gross margin 70% on both plans (given) · Plan mix: assumed the 2/3 Basic / 1/3 Pro split applies to the 240 true new customers (**stated assumption** — if it instead describes the raw 300, the split shifts slightly; ask billing to confirm) · Contribution margin: 70% both plans (given, treated as = gross margin, no separate COGS breakdown provided) · History: **0 prior periods supplied** — this run is a single month.

Scoping: this is a fast, one-off "where do we stand" read, not a described standing check — so fully-loaded CAC (needs a salary-allocation rule from finance) and marginal CAC (needs deliberate test spend) are deleted from this run, not computed. **Promote next period:** a per-plan trailing history (rung 2) and a retention/cohort read (needed for discounted payback) — both are cheap once tracked monthly and are what actually unlocks a firmer verdict on Basic.

## Metric table

| Metric | Variant | Value | Window | Source |
|---|---|---|---|---|
| Billing-reported CAC | blended, **uncorrected** (renewals/reactivations left in) | $310.00 | last month | billing, as given |
| New-customer CAC | blended, corrected ($93,000 ÷ 240) | **$387.50** | last month | billing, corrected per Step 1 |
| Monthly gross profit / customer — Basic | $15 × 70% | $10.50 | — | own plan economics |
| Monthly gross profit / customer — Pro | $99 × 70% | $69.30 | — | own plan economics |
| Payback — Basic | corrected CAC ÷ Basic gross profit | **36.9 months** | last month | derived |
| Payback — Pro | corrected CAC ÷ Pro gross profit | **5.6 months** | last month | derived |
| Payback — blended | corrected CAC ÷ mix-weighted gross profit ($30.10) | **12.9 months** | last month | derived |
| Payback — blended (uncorrected, for comparison) | $310 ÷ $30.10 | 10.3 months | last month | derived, shown to expose the distortion |

## Comparison ladder

1. **Own economics (rung 1).** Positive margin on both plans means CAC is arithmetically recoverable eventually — this isn't a "loses money by construction" case like a sub-break-even ROAS. The open question is *timing*: Pro clears in under 6 months; Basic takes over 3 years, which only pays off if a Basic customer actually sticks around that long. That's a retention question, not something this run's inputs can settle — no churn/tenure data was supplied. Gap named, not guessed around.
2. **Own trailing history.** Not available — only one month was given. No trend direction can be reported. This is the single biggest thing missing from a confident verdict; a 4–8 month per-plan series would tell you within a quarter whether Basic's payback is stable, worsening, or was always this shape.
3. **External, provenance-labeled, context only:**
   - David Skok's 12-month payback rule (Matrix Partners, ~2011) — folklore, not a study; Skok himself: "I guessed at that number." Named because you raised it, weighted accordingly.
   - Best variant-matched published figure: Benchmarkit 2025/2026 CAC-payback-by-ACV-segment survey (583 / 342 participants, self-reported) puts sub-$5K-ACV SaaS at **~11 months**. Both Loopwell plans (Basic ACV $180, Pro ACV $1,188) fall in this tier — this is the right comparison, not the generic blended medians below.
   - Generic (less well-matched, larger-ACV-weighted) panel medians, presented as a conflict, never averaged: 18 months (Benchmarkit 2025, n=583), 16 months (Aleph×Benchmarkit 2026, 198/342 reporting), 20 months (KeyBanc 2024).
   - Against every one of these, Pro's 5.6 months is comfortably inside the healthy range on any panel. Basic's 36.9 months is roughly **3–3.5× every one of them**, including the folklore number and the correctly-matched segment.

## Verdict and evidence gate

Gate: variant established (yes — corrected new-customer CAC) · margin known (yes, 70%) · window ≥ conversion lag (yes — self-serve has no sales-cycle lag to mature) · channels complete (yes, single total, nothing to renormalize) · **retention/tenure known (no)** · **own history available (no, single period)**.

The gate doesn't block a verdict outright — rung 1 arithmetic is computable — but two real gaps limit how firm each verdict can be:

- **Pro: Healthy**, on rung 1, with headroom against every reference point. Caveat: no trend yet, so call it confirmed-healthy next period once a second data point exists.
- **Basic: Watch**, not Unhealthy. "Unhealthy" would mean below your own break-even on arithmetic — that's not established here, because whether the 36.9-month payback is ever actually recovered depends entirely on whether Basic customers outlast that window, and no retention number was given to check it. Calling it "unhealthy" off the benchmark gap alone would be exactly the rung-3-only mistake this method exists to prevent. Named next-period question: **what's Basic's median customer tenure — above or below ~37 months?**
- **Blended (12.9 months): not a verdict.** It sits just past Skok's folklore line, but that's an artifact of averaging a 5.6-month segment with a 36.9-month one — it describes neither plan. Don't report it as "the" number.
- One more thing worth surfacing on its own: the corrected CAC ($387.50) is **25% higher** than the number billing currently reports ($310) purely from excluding reactivations and renewals. That gap exists every month this flag isn't fixed at the source, not just this one.

## Folklore appendix

- **12-month CAC payback** — David Skok, 2011. Self-admitted rule of thumb tied to 2011 fundraising conditions, never empirically validated. Loopwell's own numbers: Pro clears it by more than 2×; Basic misses it by roughly 3×; the blended figure (12.9 months) sits just past it, which is the least informative of the three ways to read this.

## Handoffs

- Basic's long payback, once retention data confirms whether it's actually recoverable → `mbfinotti/advertising-skills@ad-spend-guardrails` (should there be a floor or kill-switch on Basic-targeted spend) and `mbfinotti/advertising-skills@ad-spend-allocation` (shift budget toward the channels/campaigns that skew Pro).
- The billing system flagging reactivations/renewals as "new customers" is a measurement fix, not a marketing one — worth raising with whoever owns that billing flag so this correction doesn't have to be done by hand every month.
- Building the per-plan trailing history and a retention/cohort read is what turns this from a one-off read into a standing check with a real rung 2 — recommend doing that before the next run rather than repeating a single-month snapshot.