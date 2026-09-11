## Before configuring anything: one framing correction

Two things in your framing need separating, because the board doc will live or die on this distinction:

**What's actually true:** Meta's (I'm assuming Meta Ads Manager — see note below) native A/B Test / Experiments tool does deterministic, non-overlapping user-bucket randomization. A given user is hashed into exactly one cell and stays there — this genuinely eliminates cross-cell contamination (the same person being influenced by both creatives, or the auction reallocating budget toward whichever ad "looks" better early and starving the other). That part of your reasoning is correct and is the real reason to use the native tool instead of two standalone ad sets.

**What's not true as stated:** randomization removes *bias*, not *uncertainty*. It gives you an unbiased causal estimate with a confidence interval — not "proof." Whether that interval is tight enough to declare a winner depends entirely on sample size, and your numbers are a problem:

- $150/day ÷ $32 CPA ≈ **4.7 conversions/day total**, ≈ **2.3/day per cell**
- Over a 10-day test window (leaving 2 days to analyze before the board meets): **≈23 conversions per cell**
- Meta's own learning-phase exit criterion is ~50 conversions **per ad set per week**. At this spend, each cell gets ~16/week — under a third of that. Both cells will likely sit in "Learning Limited" for the entire test, which adds delivery noise on top of the sampling noise.

Rough power math (two-proportion test, 95% confidence, 80% power, illustrative 2% baseline conversion rate):
- Detecting a **50% relative difference** between creatives needs ~90–100 conversions/arm
- Detecting a more realistic **25% relative difference** needs ~300+ conversions/arm
- You're on track for ~23–28/arm

So: presented honestly, this design can only reliably catch a *huge* difference between concepts. If the real difference is moderate — the more likely case for two competently-made concepts — the test will most likely come back "inconclusive," and if it does show a "winner," the confidence interval will be wide enough that calling it causal proof would be indefensible in front of anyone who checks the math.

This doesn't mean don't run it — it means present it as what it is. I've configured the test as designed and written the board doc to state the uncertainty honestly rather than oversell it, which is the more defensible position for a board audience anyway. Recommendations to actually close the power gap are in the doc below.

*Assumption flagged: I've built this for Meta Ads Manager's native A/B Test tool, since that's the standard "native experiment tool" for DTC creative testing. If it's actually Google (Campaign Experiments) or TikTok (Split Test), the cell/budget mechanics below map 1:1, but the significance-reporting UI differs slightly — say the word and I'll adjust.*

---

## Part 1 — Test configuration (Meta Ads Manager → Experiments → A/B Test)

**Structure**
- 1 campaign → 2 ad sets (cells), created via the native A/B Test flow (not manual duplication — the native tool is what guarantees the non-overlapping random split)
- **Variable isolated:** Creative only. Everything else — audience, placement, optimization event, bid strategy, budget — must be byte-for-byte identical between cells. Any second variable (e.g., also testing a different CTA or audience) breaks attribution of the result to "which concept wins."

**Cells**
| | Cell A | Cell B |
|---|---|---|
| Creative | Concept A | Concept B |
| Audience | Shared, randomly split by Meta (non-overlapping) | same |
| Daily budget | $75/day | $75/day |
| Optimization event | Purchase | Purchase |
| Bid strategy | Lowest cost (no cap) | same |

*Note on optimization event:* optimizing for Purchase directly is correct for a CPA-honest test, but it's also the lowest-volume event you could pick — which is exactly the power problem above. If the test comes back inconclusive on CPA, track Add-to-Cart and Landing Page View as optimization-adjacent secondary reads (see metrics below), not as a mid-test pivot of the optimization event itself — changing the optimization event mid-flight would itself contaminate the results.

**Duration**
- Fixed end date, **10 days**, set at launch — not stopped manually early. Peeking at day 3–4 and calling it because one cell looks ahead is the single most common way "clean" tests stop being clean (early trends regress to the mean as sample size grows).
- Leaves 2 days before the board meeting for analysis and slide-building.

**Confidence level**
- Set to 95% in the Experiments tool. Given the math above, expect it to report "not significant" more often than not at this budget — that's the tool working correctly, not failing.

**Primary metric:** Cost per Purchase (CPA)

**Secondary metrics to track in parallel (higher volume, faster signal, report as directional, not primary):**
- CTR (link click-through rate)
- Cost per Landing Page View
- Cost per Add-to-Cart
- Hook/thumbstop rate if either concept is video

**Pre-registration (do this before hitting launch, not after seeing early numbers):** write down the hypothesis, the primary metric, and the stopping rule in one line each. This is what actually makes a test "clean" for a board audience — more than the tool itself.

---

## Part 2 — Board write-up

*(Ready to paste into slides or a memo — this is written to be presented alongside whatever result the test actually returns, including "inconclusive.")*

### Creative A/B Test: Design & Methodology

**Objective**
Determine which of two new creative concepts (Concept A, Concept B) drives a lower cost per purchase, using [Meta]'s native randomized experiment tool rather than manual A/B comparison, to eliminate audience overlap and auction-driven bias between the two creatives.

**Method**
- Randomized controlled test: users are deterministically and randomly assigned to one of two non-overlapping cells (Concept A / Concept B), each held out from the other's spend and audience.
- This design removes cross-contamination — no user is exposed to both concepts, and neither cell's delivery can crowd out the other's.
- Budget: $150/day total, split evenly ($75/day/cell). Duration: 10 days. Confidence threshold: 95%.
- Primary metric: cost per purchase. Secondary metrics (CTR, cost per landing page view, cost per add-to-cart) tracked as earlier, higher-volume leading indicators.

**What this design can and cannot claim**
At current CPA (~$32) and budget, the test is expected to generate roughly 20–30 purchases per cell over 10 days. A test at this scale can reliably detect only a large gap between concepts (a difference on the order of 50%+ in relative CPA). It is underpowered to reliably detect a moderate, still business-meaningful gap (e.g., 20–30%) — that would require roughly 10x the conversion volume per cell.

Practically: if one concept is a runaway win, this test will very likely show it clearly and the primary metric alone will support a decision. If the two concepts perform similarly, the test is more likely to return "not significant" than to wrongly call a winner — the randomization protects against a *false* winner, it just can't always produce a confident one at this volume.

**Recommendation**
1. Treat the day-12 readout as a **directional result with a stated confidence level**, not a final verdict — report exactly what the platform's significance test returns, including "inconclusive" if that's what it is.
2. Use the secondary funnel metrics (CTR, cost/LPV, cost/ATC) as an earlier, higher-volume signal to say which concept is *trending* ahead, clearly labeled as directional rather than definitive.
3. If the board wants a statistically confident CPA verdict rather than a directional one, the two levers are: more budget (roughly 3–4x, to ~$450–600/day, gets us into range to confidently call a *large* gap) or more time (continue the test past the board meeting and report the confirmed result at the next check-in).
4. Either way, do not stop the test early based on an interim lead — that invalidates the randomization guarantee this design is built on.

---

**Open items to confirm before I finalize/launch:**
- Confirm ad platform (Meta assumed) and current landing-page purchase conversion rate, so I can tighten the power numbers above from illustrative to actual.
- Confirm Concept A / Concept B creative assets are ready and whether either is video (affects the hook-rate secondary metric).
- Decide now, before launch: extend past board date, add budget, or present as directional — pick one so it's in the pre-registered write-up rather than decided after seeing a lead.