# Spend Health Check — Corvid Analytics, Q3 2026 (trailing 8 quarters)

## Headline

- **Blended CAC payback: WATCH** — rests on rung 2 (own history) with partial rung 1 support. Two years flat at ~21 months, not deteriorating — but that's 7 months (≈50%) above the properly ACV-matched external comparator, only partly explained by strong NRR, and the trend's flatness means nothing is fixing it on its own.
- **LTV:CAC 2.7** — secondary signal only, not verdict-driving. Below the folklore "3" and below current descriptive medians (~3.2–3.6). Named in the folklore appendix below; don't let it anchor the board conversation.

## Definitions record

Model: B2B SaaS · Window: 8 trailing quarters (2 years), payback "computed the same way each quarter" — window/lag maturity assumed since these are realized, not projected, figures · **Spend-line composition of the CAC numerator not stated** (blended vs. paid vs. fully-loaded) — flagged, not fatal, because consistency across periods still makes the *trend* valid even with the *level* undefined · New-customer basis (renewals/reactivations excluded?) not stated · Revenue basis: ACV $30K, gross vs. net not specified · **Contribution margin: 78% gross margin, used as a proxy** — reasonable for SaaS (COGS ≈ hosting/support, few other variable costs), but not confirmed as true contribution margin · History: 8 quarters available (exceeds the 4–8 minimum).

Given the Thursday deadline, I deleted from this run: a fully-loaded CAC rebuild, a cohort/segment breakdown by plan or ACV band, and a CM1/2/3 waterfall — all need raw spend and customer-level data I don't have, and none fits before Thursday. **Promote next period:** (1) fully-loaded CAC, because this is going to a board deck and blended/undefined-variant numbers won't hold up to a director's follow-up question; (2) gross logo retention (not just NRR), which is the one missing input that would let rung 1 be answered definitively instead of partially; (3) per-segment payback, since a blended $30K-ACV average likely hides very different economics across your accounts.

## Metric table

| Metric | Variant | Value | Window | Source |
|---|---|---|---|---|
| CAC payback (current) | undefined spend-line composition, consistent methodology | 21 months | current quarter | user-provided, internal calc |
| CAC payback (8-quarter trend, oldest→newest) | same | 21.5, 21, 20.5, 21, 20.5, 21, 21, 21 | trailing 2 years | user-provided, internal calc |
| Monthly gross profit per customer | ACV × gross margin ÷ 12 = $30,000 × 0.78 ÷ 12 | $1,950 | — | derived from user-provided ACV/margin |
| Implied CAC (backed out of payback) | payback × monthly gross profit = 21 × $1,950 | $40,950 | current quarter | derived |
| Allowable CAC (first-year) | ACV × gross margin | $23,400 | — | derived, own economics |
| LTV:CAC | as reported | 2.7 | current | user-provided |

The $40,950 "implied CAC" is arithmetic, not a new fact — it's what your 21-month payback and stated margin necessarily imply about dollars spent per customer, useful for translating "months" into a number the board reacts to more directly.

## Comparison ladder

1. **Break-even (partial).** First-year allowable CAC is $23,400 (12 months of contribution); your implied CAC of $40,950 exceeds that, which is just another way of saying payback runs longer than 12 months — not itself alarming for a $30K-ACV, 78%-margin business. The real break-even test is whether payback completes before customers churn, which needs gross/logo retention. You gave NRR (118%, net of expansion) but not gross churn, so I can't close this rung. NRR 118% is a positive proxy — it's hard to post that number with high logo churn — but it's an inference, not a measurement. **This is the single highest-value number to bring to the next check.**
2. **Own history — the strong rung here.** 21.5 → 21 → 20.5 → 21 → 20.5 → 21 → 21 → 21 over 8 quarters. Range of exactly 1 month, mean 20.9. This is flat, not deteriorating — genuinely reassuring against a "things are getting worse" reading. It also means the gap to peers (below) is structural and two years old, not a recent event.
3. **External — present as conflict, not an average.** You collected three published medians; averaging them to "18" is exactly the move to avoid, because they measure different panels on different definitions:
   - 18 months, 2024 (Benchmarkit 2025 SaaS Performance Metrics Survey, n=583, self-reported)
   - 16 months, FY2025 (Aleph x Benchmarkit 2026 SaaS & AI Survey, 198 of 342 respondents reporting, self-reported)
   - 20 months, 2024, down from 25 in 2022 (KeyBanc/KBCM, private SaaS panel, self-reported)

   None of these is the right comparator for Corvid specifically — they're generic aggregates across all ACV sizes. Benchmarkit also publishes payback **segmented by ACV**, which is the actual apples-to-apples figure: the $25K–50K ACV band runs **~14 months**, and "mid-market" runs ~14–18 months (same source/panel). Corvid's $30K ACV sits squarely in that band. Against **14 months**, not 18, the gap is 7 months (~50%), which in dollar terms is $27,300 (benchmark-implied CAC) vs. your $40,950 — roughly $13,650 more per customer than a segment-matched peer. That's the number that should replace "18" in the board deck.

   One mitigating factor named explicitly in the same source: a below-median payback at a given ACV isn't automatically a red flag if NRR is high, since strong expansion can justify a longer upfront acquisition period. Corvid's 118% NRR is a real, favorable data point here — but it's a partial offset, not a full explanation, and I can't quantify how much of the 7-month gap it covers without more data.

## Verdict and evidence gate

Gate: variant established — **partial** (composition undefined, but consistent, so trend is trustworthy even though the level's precise definition isn't) · margin known — **yes** (78%, used as contribution-margin proxy) · window ≥ lag — **assumed** (realized quarterly figures, not stated explicitly) · channels/complete — **n/a**, single blended figure.

**Verdict: Watch.** Not unhealthy: the trend across 8 quarters is flat, not crossing further from break-even, and NRR 118% argues the business likely recovers CAC well before churn even though that can't be proven from what's here. Not healthy either: the gap to the properly ACV-matched benchmark (14 months, not the naive 18-month average) is large — about 50% — and it has been stable for two years, meaning it's a structural characteristic of the go-to-market, not noise that will resolve itself. Waiting for it to improve on its own has a two-year track record of not happening.

## Folklore appendix

- **"LTV:CAC should be 3:1"** — David Skok (Matrix Partners, ~2011–2013): on record at SaaStr as "I guessed at that number." Not a study. Current descriptive medians run *above* 3, not at it (3.2:1, Optifai 2025–2026, n=939; 3.6:1, Benchmarkit 2025) — so by that lower bar Corvid's 2.7 is a bit further behind than "below the folklore rule" alone suggests, but it's still a secondary check; prefer the payback read above, which is directly grounded in your own ACV and margin.
- **The 16/18/20-month figures you collected** — correctly gathered as a range rather than a single number, which is the right instinct. The mistake was collapsing them to one average (18); the fix is the ACV-segmented figure above, not a better average of the three.

## Handoffs

- Gap is structural and unexplained for two straight years → `mbfinotti/advertising-skills@ad-account-diagnostic` to find out *why* Corvid's payback sits ~50% above segment peers (channel mix, sales cycle, discounting, something else).
- If next quarter's payback moves further from 14 months, or NRR softens (removing the offsetting justification), escalate to `mbfinotti/advertising-skills@ad-spend-guardrails` to set an explicit ceiling — this check doesn't set policy, it only reads the arithmetic.
- Gross/logo retention is the one input that would let rung 1 close definitively — get it before the next quarterly check, not before Thursday.