# Spend Health Check — Nivara Health, Q1 vs Q2 (Series B board deck)

## Headline

**No — do not run with "CAC improved 35%."** The two figures compare different CAC variants, not two readings of the same metric. This is the exact failure this skill exists to catch. On a same-variant (paid CAC) basis, paid CAC went from $95 to $100 — a **5.3% increase**, not a 35% improvement.

## Definitions record

Model: B2B SaaS · Window: Q1 vs Q2 (quarterly) — sales-cycle length not provided, so cohort-lag maturity is unconfirmed · History: 2 periods, below the 4–8 needed for a trend read, and not even on one consistent definition · Contribution margin / ACV: not provided → break-even not computable · Revenue basis: not provided.

**The variant switch, made explicit:**

| Quarter | Formula used | Numerator | Denominator | Result | Variant |
|---|---|---|---|---|---|
| Q1 | as reported | $190,000 paid spend | 2,000 paid-attributed customers | $95 | **Paid CAC** |
| Q2 | as reported | $217,000 total marketing spend | 3,500 all new customers | $62 | **Blended CAC** |

Marketing's slide divides a paid-only number by a paid-only denominator in Q1, then divides an all-in spend number by an all-customer denominator in Q2. Those are two different metrics in the same family — this is the skill's own textbook case, near-verbatim: *"$84K spend, 2,000 new customers of which 1,200 from paid = $42 blended and $70 paid CAC for the same month. Silently switching variants makes CAC 'improve' with nothing changing."* Same mechanism here, larger stakes because it's headed to a board deck.

## Metric table (restated on consistent variants)

| Metric | Variant | Value | Window | Source |
|---|---|---|---|---|
| Paid CAC | paid spend ÷ paid-attributed customers | $95 | Q1 | sheet |
| Paid CAC | paid spend ÷ paid-attributed customers | $100 | Q2 | sheet |
| Blended CAC | total marketing spend ÷ all new customers | $62 | Q2 | sheet |
| Blended CAC | total marketing spend ÷ all new customers | **not computable** — Q1 total marketing spend and Q1 total new customers (organic included) weren't given | Q1 | — |
| Organic-attributed new customers (implied) | all new − paid-attributed | 1,650 (47% of Q2 new customers) | Q2 | derived: 3,500 − 1,850 |

## Comparison ladder

1. **Break-even** — not computable. No contribution margin, gross margin, or ACV was provided, so rung 1 is blocked outright.
2. **Own history** — only one clean same-variant data point exists (paid CAC $95 → $100), one period short of the 4–8 needed for a real trend read. What it shows: paid efficiency held roughly flat, drifting slightly worse, not better.
3. **External** — not needed to settle this. This is a definitional-mismatch finding, not a "how do we compare to the market" question; pulling a benchmark here would be Step-3-rung-3-as-verdict, the core failure mode this skill flags.

## Verdict and evidence gate

Gate: variant established **Y — but the two headline figures used different variants, which is the defect** · margin known **N** · window ≥ conversion lag **unconfirmed** · channels complete **N (Q1 blended components missing)**.

- **On the "35% improvement" claim: rejected.** It's a Paid-CAC-vs-Blended-CAC comparison. The gap measures the definitions, not the quarter's performance.
- **On overall paid-channel health: insufficient evidence** for a full verdict (no margin → no break-even; only one same-variant data point → no valid trend), but the one clean read available is a mild ~5% *increase* in paid CAC, the opposite direction of the claim.
- **What actually happened in Q2:** organic new customers jumped to ~47% of the total, plausibly the stated PR hit, and pulled the blended number down. That's a real, good thing — but it's a mix-shift, not a paid-spend efficiency gain, and mix-shift is exactly what Step 2 warns can move a blended number "while every segment is flat."

## For the board slide

Don't ship "CAC improved 35%" — a diligence associate who asks for the paid/organic split (a routine question at Series B) will surface the switch in minutes, and that costs more credibility than a modest, correctly labeled number. Two honest, separately defensible statements instead:

- *"Paid CAC held roughly flat quarter-over-quarter ($95 → $100)."*
- *"Organic acquisition surged following [PR event], now ~47% of new customers, pulling blended CAC to $62 — a genuine efficiency win worth its own line, not folded into a paid-performance claim."*

## Handoffs

- Get Q1 total marketing spend + Q1 total new customers (organic included) so blended CAC can be trended across both quarters on one definition → re-run this skill.
- Get contribution margin/gross margin and ACV to compute break-even and payback (rung 1) — worth doing before this reaches the board, per this skill's own rule: promote fully-loaded/rung-1 rigor whenever the audience is finance or investors.
- Confirm the B2B sales cycle length; if it's longer than a quarter, both quarters' paid CAC may be counting this period's spend against a customer cohort that hasn't fully closed yet — check before trusting even the $95→$100 read.
- Setting a target/floor for what "healthy" paid CAC looks like going forward is out of scope here — that's `mbfinotti/advertising-skills@ad-spend-guardrails`.