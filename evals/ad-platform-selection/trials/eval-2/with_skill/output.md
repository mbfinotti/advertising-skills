# Kelpwild channel plan — paid media, Sept 2026

**Short answer: no, don't run it as written.** Three separate gates fail — one on economics (the 4x/2-week bar), one on funding (splitting $12K five ways underfunds every channel's learning threshold), one on channel fit (streaming TV doesn't clear affordability or timing at this budget). Below is the framework this plan needs to pass, and the corrected version.

## 1. Economics

|                                                     |                    |
| --------------------------------------------------- | ------------------ |
| AOV                                                 | $42                |
| Gross margin                                        | 58%                |
| Contribution per sale                               | $24.36             |
| Break-even ROAS (1 ÷ 0.58)                          | **1.72x** — not 4x |
| Allowable CAC (first-order; no LTV/retention given) | **~$17**           |

Two corrections to the stated plan:

- **4x ROAS is the wrong bar in both directions.** Break-even is 1.72x. A blended target should sit near AOV ÷ allowable CAC = 42/17 ≈ **2.5x ROAS (≈$17 CPA)**, not 4x — a 4x floor kills channels that are still profitable, and it isn't derived from anything in Kelpwild's actual economics.
- **$17 is a thin ceiling**, thinner than either worked example in this framework. At that ceiling, most channel benchmarks below sit _above_ it, which is the real problem with the five-way split — not which five channels were picked.

**Open question that changes everything: is sunscreen a repeat purchase for you (subscription, seasonal reorder, multi-tube households)?** This plan uses first-order CAC because no retention data was given. If Kelpwild customers reorder even 2-3x/year, real allowable CAC is materially higher than $17 and several deleted/starved channels re-open. Get this number before locking budget.

Also unconfirmed and worth flagging before spend: primary geography (assumed US), whether sunscreen/health-claim ad policies are cleared on each platform (OTC sunscreen + "reef-safe" claims can trigger platform health-ad certification and FTC substantiation scrutiny — verify per platform before launch), and whether conversion tracking is live and verified.

## 2. Deleted channels

| Family           | Gate failed                                 | Specifics                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ---------------- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Streaming TV** | Affordability + funding floor + test design | $24 contribution can't clear $20-40 managed CPM plus $1,500-$15,000+ production. Even the cheapest self-serve tier's own guidance (~$165/day, ~$5,000/month) exceeds the proposed $2,400 — production alone would eat most of that budget before a single spot airs. On top of that, CTV needs a full quarter (production + incrementality build) before a readable result; a 2-week kill on this family is a guaranteed false negative, not a verdict. |
| **Pinterest**    | Not gateable                                | Doesn't map to a benchmarked family in this framework — it belongs in the deliberately-unranked price-discovery bucket (wide, unverified cost range, like native/discovery). Never fund it as one of several equal lanes on a first plan; it's a second-channel candidate _after_ a small standalone price-discovery test returns a real number.                                                                                                        |

## 3. Candidates ranked by value ÷ effort — survivors only

| Rank | Family                    | Value (presence/reach/reachability/measurability)                                                                        | Effort (burn/skill/reversibility)                  | Ratio   |
| ---- | ------------------------- | ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------- | ------- |
| 1    | **Paid search**           | 16/20 — precise intent, strong measurability, category search volume for "reef-safe sunscreen" plausible but unconfirmed | 4/15 — text + landing page, pausable in minutes    | **4.0** |
| 2    | Paid social (Meta)        | 15/20 — DTC/skincare buyers demonstrably here                                                                            | 8/15 — standing 8-15+ variant creative job         | 1.9     |
| 3    | Short-form video (TikTok) | 13/20 — weaker measurability, less precise targeting                                                                     | 10/15 — heaviest creative burn, days-level fatigue | 1.3     |

No departure from the default ordering — nothing in what's known about Kelpwild (no confirmed in-house video team, no owned audience, no answers to Q15-17) earns a promotion against rank.

**The affordability math is the real story here, not the ranking**: Meta's median CPA benchmark (~$38) and TikTok's comparable range both sit **over 2x above the ~$17 CAC ceiling**. They're not deleted outright — benchmarks are directional medians, and this needs verification for Kelpwild's specific audience — but neither should get equal-share, blind-committed budget. Both need price discovery to prove they can even clear the ceiling before real money moves.

## 4. Primary recommendation

**Paid search.** Category has plausible existing search demand ("reef-safe sunscreen" is a real, if niche, search term), capture is fully unfunded today, it clears the affordability math most cleanly of the three survivors, and it's the only family cheap enough in effort to validate fast on a $12K budget.

## 5. Funding plan

Stop splitting five ways — at $2,400/channel (~$80/day) you're already at the textbook anti-pattern this framework calls out by name: below every major family's learning threshold, five experiments each too thin to read.

- **~80% ($9,600/mo, ~$315/day) to paid search.** Clears the floor easily (floor is 3-5x the $17 target CAC = $51-85/day).
- **~$100 held for a Meta price-discovery test only** — not a funded prospecting campaign. $2,400 is nowhere near Meta's real learning threshold (~50 events/ad set/week at ~$38 CPA implies ~$8,200/month for one ad set alone) — funding it as a fifth of the budget would burn it without ever exiting learning.
- **Remainder to retargeting** once search traffic accumulates (days) — near-zero incremental effort, reuses paid traffic already bought.

## 6. Test design (paid search, the primary)

1. **Price discovery**: ~$100 on exact/phrase-match reef-safe/ocean-safe sunscreen terms to get Kelpwild's real CPC before committing further.
2. **Real test**: $51-85/concept (3-5x the $17 target CPA) per ad group, run **2-4 weeks** (full search cycle for an impulse-to-days purchase), same weekday start/end.
3. **Pass**: CPA ≤ ~$17 at 90-95% confidence — not a blended ROAS number, and not judged off the platform dashboard's inflated conversion count.
4. **Kill**: $34-51 spent (2-3x target CPA) with zero conversions after a readable sample.

If Meta's price-discovery pull-in shows CPC/CPA plausibly near the $17-25 range, run its own real test on the same 3-5x logic — but over **3-6 weeks**, not 2. A uniform two-week window is a false-negative trap for social and video regardless of what they cost; it's short enough that even a working channel reads as "zero lift."

## 7. Second-channel trigger

Add Meta as a real (not token) second channel only when **either** search CPA rises on saturation (impression share maxing out) **or** total budget crosses toward $50K/month — and only if price discovery already cleared it. Don't add it by thinning search's budget; add it with fresh money or reallocated savings.

## 8. Measurement

- UTM discipline + last-non-direct now (capture-heavy, small budget — the correct starting rung).
- Add "How did you hear about us?" at checkout the moment Meta/TikTok enters the mix — cheap correction for last-click's structural bias against creation channels.
- Move to MER once ecommerce spend is material enough that platform-reported ROAS and real revenue visibly diverge.
- Verify tracking end-to-end before any spend lands — an unverified pixel/conversion API means the whole learning phase is wasted by design.

---

**Bottom line**: keep the $12K total, drop the even split, drop streaming TV, drop the 4x/2-week rule everywhere. Put ~80% into search with a real 2-4 week test at a $17 CPA bar, hold a small reserve for Meta price discovery (not a funded campaign), and answer the repeat-purchase question — it's the single number most likely to change this whole plan.
