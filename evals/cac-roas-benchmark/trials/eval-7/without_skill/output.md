## Verdict: Yellow, not red. Don't let this rattle the board.

Both ratios sit outside the “textbook” threshold, but the story underneath is more forgiving than the headline numbers suggest — and there's one number I'd nail down before Thursday that matters more than either ratio.

### 1. CAC payback: 21 vs. "18"

- Gap is 3 months / ~17% over benchmark — real, but not alarming on its own.
- Trend over 8 quarters (21.5 → 21 → 20.5 → 21 → 20.5 → 21 → 21 → 21, mean 20.94): **flat, tight band (±0.5mo)**. This is not a deteriorating metric — it's a stable one that's always run ~3 months long. Stability is the strongest data point you have; lead with it.
- Your "18" benchmark is an average of three external medians (16/18/20) from unknown methodology, segment, ACV band, and sales motion. Averaging heterogeneous published medians into a single number is a convenience, not a rigorous comparator — expect a sharp board member to ask "18 according to whom, for companies like us?" Have the three sources and their sample definitions ready.

### 2. The number that actually changes the read: NRR-adjusted payback

Standard CAC payback assumes **flat revenue** — it prices in the year-1 ACV only and ignores that your cohorts expand. With NRR at 118%, that assumption is wrong for your business, and it's wrong in a way that flatters you.

Back-solving your CAC from the 21-month figure (ACV $30K, GM 78%, monthly GM$ = $1,950):

- CAC ≈ $40,950 (implied from 21 × $1,950)
- Re-running the same payback but letting cohort revenue compound at 118% NRR (≈1.39%/month) instead of holding it flat: **effective payback ≈ 18.5 months**

That's essentially at your benchmark. The 21-month number isn't wrong, but it's measuring "time to recover CAC if the customer never expanded" — which is not how your customers behave. **Recompute and present this NRR-adjusted payback for the board** (with your actual CAC, not my back-solved estimate) — it's a legitimate, defensible reframe, not spin, because it uses your own actual expansion data.

### 3. LTV:CAC: 2.7 vs. "3" — the more interesting flag is hiding here

The 0.3 gap alone isn't the concern. What's worth checking before Thursday: back-solving from LTV:CAC = 2.7 and CAC ≈ $40,950 gives implied LTV ≈ $110,600. Under a standard perpetuity model (LTV = ACV×GM ÷ annual churn), that implies an **annual value-decay rate of ~21%** driving your LTV — i.e., your LTV math is effectively assuming ~21% gross revenue churn, offset by ~39 points of expansion, to net out at 118% NRR.

That's a big spread between gross churn and expansion. It's a completely normal shape for a strong-expansion SaaS business, but it means your 118% NRR could be **masking real logo/gross-dollar churn** rather than reflecting a universally sticky base. Before the board meeting, pull your actual **gross revenue retention (GRR)** and **logo churn**, and check them against whatever churn assumption is baked into the LTV model that produced 2.7. Two very different board narratives hang on this:

- GRR ~79-85%, expansion doing the heavy lifting → fine, common, but worth knowing and worth a retention narrative, not just an acquisition one.
- GRR much higher (say >90%) and the LTV model is just conservative/short-horizon → your true LTV:CAC is probably comfortably above 3, and the "2.7" is a modeling artifact, not a business problem.

You (or your RevOps/finance team) know which one it is; I don't from the numbers given. This is the single most valuable thing to check before Thursday — it's more decision-relevant than either headline ratio.

### What I'd actually put in the board deck

1. Lead with the trend chart, not the single-quarter number: 8 flat quarters at ~21 months says "stable, well-understood unit economics," not "eroding efficiency."
2. Show the NRR-adjusted payback (~18.5mo) next to the flat-revenue payback (21mo), labeled clearly as two different conventions — don't let the flat number stand alone as if it's the whole truth.
3. Get the GRR/logo-churn number and reconcile it against the LTV model before you present the 2.7. If GRR is healthy, restate LTV:CAC using it and you likely clear 3.0. If GRR is weak, that's the real conversation to have with the board — not the ratio itself, but _why_ churn is where it is and what's being done about it.
4. Footnote the "18-month" and "3x" benchmarks with actual sources and note the comparability caveat (segment/ACV/motion unknown) so you're not caught flat-footed if someone pushes on it.

Bottom line: at 78% margin and 118% NRR, this is a business with strong economics whose headline efficiency metrics are running slightly behind poorly-sourced external benchmarks — not a business with a capital-efficiency problem. The one real homework item is reconciling GRR against your LTV model before you stand behind the 2.7 in the room.
