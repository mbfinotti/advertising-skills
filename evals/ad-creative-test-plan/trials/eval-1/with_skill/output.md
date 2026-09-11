# Fernweh Goods — Holiday Concept Test Plan

**Headline finding, before anything else:** with $15K/month and 5 weeks, this account can only get a **statistically significant winner if one concept crushes the champion by roughly 50%+ relative lift** on purchase rate. A normal, healthy creative win (15–30% lift) will **not** reach significance in this window — it'll be a **Directional read** (a ranking, not a "95% confidence" claim). Your marketing lead's "announce the winner at 95% confidence" framing needs to be walked back before the all-hands, or the account needs to walk in already knowing which outcome it's likely to get. I've built the plan so it can still deliver a real answer either way — see the framing note at the end.

## Assumptions (flagged because your interview answers weren't given — confirm before launch)

| Item | Assumption used | Why it matters |
|---|---|---|
| Platform | Meta (Advantage+ Creative off in test cells) | Swap to TikTok Split Test / Google Experiments mechanics if wrong; math below is platform-agnostic |
| Assets per new concept | 3–4 finished cutdowns/aspect ratios each | Fewer assets doesn't break the plan, just thins the cell |
| Prior testing | Nothing already settled this question | If you've already tested "utility vs. fear" angles, say so — this may be re-litigating a closed question |
| Auto creative optimization | Assumed currently on somewhere — **must be OFF in these 3 cells** | Otherwise the platform picks the winner, not the test |
| Who monitors this | You, with budget authority inside the protected $15K | Drives the decision-rule choice below |
| Regulatory | None (travel accessories, non-regulated) | Just don't claim the packing hack "prevents" lost luggage — that's a substantiation risk, not a compliance one |

**One thing I can't reconcile and you should, before trusting the numbers below:** your CPC ($1.25) and click→purchase rate (2.5%) imply a ~$50 CPA. Your stated CPA is $20. Those don't arithmetically agree — likely your $20 blends in retargeting/warm traffic or a different attribution window than a fresh 3-way prospecting test will see. I built this plan on the stated $20 CPA (it's the number you gave me for exactly this purpose), but **pull actual cold-prospecting CPA for the last 30 days before locking budget splits.** If real cold CPA is closer to $50, the stable-delivery floor below fails and the fix is "2 sequential challenger waves," not "3 simultaneous cells" — flagged again where it bites.

---

## 1. Decision and hypotheses

**Decision:** the concept (packing-hack demo, lost-luggage horror story, or "neither — champion holds") that wins on cost per purchase gets the holiday production budget.

```
H1: Because [insert the actual customer signal that greenlit this — reviews/support
    tickets/comments mentioning packing frustration], changing the champion's angle
    to a packing-hack demo will lower cost per purchase ~20-30% (screening target,
    not the significance bar) for cold prospecting, by day 28.

H2: Because [insert the actual signal behind the horror-story concept — lost-luggage
    complaints, loss-aversion response in past creative], changing the champion's
    angle to a lost-luggage horror narrative will lower cost per purchase ~20-30%
    for cold prospecting, by day 28.
```

Replace the bracketed evidence — I don't have your customer research, and a hypothesis without real "because" is a guess, not a test.

## 2. Isolation level: bundled concept-level

Ranked deliberately, not by default: **bundled > tiered > strict isolation** here, because:
- A single 5-week window before a hard decision date **deletes tiered** (no time for a second validation pass).
- You want a one-off winner to fund production, not transferable element-level learning — **favors bundled** per the interview logic.
- Packing-hack demo vs. horror story vary angle, format, and execution together — that's inherently bundled, not a clean single-variable swap.

**Labeled: `bundled — unlearnable at element level`.** A win tells you which concept, never which element inside it. Don't let anyone later claim "we learned fear beats utility" from this test — you'll have learned "this specific horror-story cut beat this specific demo cut."

## 3. Cell matrix and structure

| Cell | Content | Daily budget | Assets |
|---|---|---|---|
| C01 (control) | Current champion, running concurrently | $167/day | existing |
| C02 | Packing-hack demo | $167/day | 3-4 |
| C03 | Lost-luggage horror story | $167/day | 3-4 |

**Structure: manual fixed-budget cells.** Native deterministic split test is the cleaner read but needs 7-30 days just to run, on top of setup — the hard date pushes it below manual. Automated budget allocation is never a test structure (it can dump 90% of spend on an early leader).

**Known limitation, stated up front:** manual cells still compete in the same auction against overlapping audiences. Even a clean statistical read here is relative screening, not causal proof (see caveats).

**Naming:**
```
C01_ANG-champion_FMT-<current>_V01
C02_ANG-packing-hack_FMT-demo-video_TAL-<creator>_V01...V04
C03_ANG-lost-luggage_FMT-horror-narrative_TAL-<creator>_V01...V04
```

## 4. Feasibility check — the actual math

- $15,000/month ≈ $500/day ÷ 3 cells = **$167/day/cell**.
- Stable-delivery floor (on stated $20 CPA): $20 × 50 ÷ 7 = **$143/day** minimum — $167 clears it, with only ~17% headroom. *(On the implied $50 CPA, the floor is $357/day and this fails outright — see the reconciliation flag above.)*
- Projected clicks/cell: $167 ÷ $1.25 = **133.6/day** → 935/week.
- Projected purchases/cell: $167 × 7 ÷ $20 = **58.4/week** (clears the ~50/week floor).

**Required sample, primary metric = click→purchase rate, 2.5% baseline, alpha 0.05, 80% power, Bonferroni-corrected for 2 comparisons (2 challengers vs. 1 control, α=0.025 each — disclosed per the skill's multiple-comparison requirement):**

| Relative lift (2.5% → X%) | Required n/cell (corrected) | Required spend/cell | Duration at projected pace |
|---|---|---|---|
| 50% (→3.75%) | ~3,680 clicks | ~$4,600 | **~28 days** |
| 25% (→3.13%) | ~13,300 clicks | ~$16,600 | ~99 days |
| 15% (→2.88%) | ~35,000+ clicks | ~$44,000+ | ~260+ days |

**Verdict: Powered only at ≥~50% relative lift, in ~28 days, on the current split.** Anything realistic (15-30%, what most concept swaps actually produce) is **Directional read** — not testable to significance in this budget or window, full stop.

## 5. Metric ladder (pre-registered)

- **Gate** (screens only, never crowns): 3-second hook rate vs. account's own trailing median, read like-for-like by placement, no verdict before 2,000 impressions/asset.
- **Primary** (the decision): cost per purchase. Powered via click→purchase rate as above; treat the CPA figure itself as **directional** given the reconciliation flag.
- **Guardrails** (must not degrade): frequency, CPM vs. account baseline, refund/return rate, AOV (catches a cell "winning" on cheap junk purchases).

## 6. Decision rules — Denney anchor

Hott needs a maintained best-ads library plus a weekly reviewer — not stated as available, **deleted**. Faris needs an evergreen no-manual-kill structure and returns a portfolio outcome, not a single winner — incompatible with "pick one concept in 5 weeks," **deleted**. Default rung, needing nothing extra: **Dara Denney's set.**

- No evaluation before **day 3**.
- Asset-level kill: **$40 spend (2× the stated $20 CPA) with zero purchases** — reallocate that asset's budget within its cell. *(If your reconciliation check finds real cold CPA closer to $50, raise this to ~$100.)*
- Cell-level dead-cell kill: **zero purchases after 7 days at full budget** → flag, redistribute its budget across the remaining two cells (this is separate from the full statistical window below — it catches a cell that never activates at all).
- Scale: winner gets the holiday production budget, plus an initial +50-100% budget step as its first paid scale-up (treat that first step as its own read — regression to the mean on a low-spend winner is real).
- Iterate: a concept that wins the gate metric but not cost per purchase gets a landing-page/offer check before any further creative work — don't blame the creative for a funnel problem.

## 7. Schedule (calendar dates, from today 2026-09-12)

| Date | Milestone |
|---|---|
| Mon 2026-09-14 | Launch, all 3 cells concurrently |
| Thu 2026-09-17 (day 3) | Earliest evaluation — no judgment before this |
| Day 3-28, ongoing | Asset kill checks (2× CPA, zero purchases), dead-cell checks (7 days, zero purchases) |
| Mon 2026-10-12 (day 28) | **Hard stop** — pre-registered: 28 days or 3,680 clicks/cell, whichever comes first |
| Oct 13-16 | Buffer: guardrail confirmation, CPA reconciliation sanity check, readout deck |
| Fri 2026-10-16 (day 32) | All-hands readout — 3 days inside your 5-week (day-35) deadline |
| Inconclusive → | **Keep control.** Champion retains the holiday budget by default. Decided now, not at readout. |

---

## The plan document

```
CREATIVE TEST PLAN - Fernweh Holiday Concept Test, 2026-09-12
decision    : winning concept earns Q4 holiday production budget; losing
              concept(s) shelved; inconclusive keeps champion
hypothesis  : H1 - packing-hack demo lowers cost per purchase ~20-30% vs
              champion for cold prospecting by day 28 [swap in real customer
              evidence before launch]
              H2 - lost-luggage horror story lowers cost per purchase ~20-30%
              vs champion for cold prospecting by day 28 [same]
isolation   : bundled - unlearnable at element level (angle + format + talent
              vary together across C02/C03; hard date and one-off-winner
              mandate both favor bundled over tiered/strict)
structure   : 2 challenger cells + control, concurrent; manual fixed-budget
              cells $167/day each; automated creative-optimization: OFF
              (confirm Advantage+/Dynamic Creative disabled before launch)
metrics     : gate = hook rate vs account trailing median, per placement,
              >=2,000 impressions/asset before judged
              primary = cost per purchase (decision), click->purchase rate
              (statistical proxy)
              guardrails = frequency, CPM vs baseline, refund rate, AOV
cells       : C01_ANG-champion (control) | $167/day | existing assets
              projected 58/wk purchases | reference cell, same rules
              C02_ANG-packing-hack_FMT-demo-video | $167/day | 3-4 assets
              C03_ANG-lost-luggage_FMT-horror-narrative | $167/day | 3-4 assets
              each: projected 133.6 clicks/day, 58/wk purchases
              required (click->purchase, 50% rel MDE, Bonferroni-corrected
              for 2 comparisons): n=3,680 clicks/cell, ~$4,600, ~28 days
                -> VERDICT: Powered on click->purchase rate AT 50%+ lift ONLY
              at realistic 15-30% lift: n=13,300-35,000+ clicks/cell,
              99-260+ days
                -> VERDICT: Directional read on cost per purchase (the
                   decision metric) for any lift below ~50% relative
              kill: asset at $40 spend (2x stated CPA) with zero purchases;
                    cell at 7 days zero purchases -> flag, redistribute budget
              scale: winner gets holiday production budget + initial
                     +50-100% budget step, treated as its own read
              iterate: gate-winner/CPA-loser -> landing page/offer check
                       before further creative work
schedule    : launch 2026-09-14 | earliest evaluation 2026-09-17 (day 3)
              | hard stop 2026-10-12 (day 28) or n=3,680 clicks/cell,
              whichever first | readout 2026-10-16 | inconclusive -> keep
              control, decided now
naming      : C0#_ANG-<angle>_FMT-<format>_TAL-<creator>_V0#
caveats     : manual cells share auction/audience - contamination noted;
              divergent delivery means even a "Powered" read is relative
              screening, not causal proof (Braun & Schwartz 2025); stated
              $20 CPA does not reconcile with $1.25 CPC x 2.5% CVR (~$50
              implied) - verify cold-prospecting CPA before trusting the
              stable-delivery floor; if real CPA is ~$50, floor requires
              ~$357/day/cell and this 3-way split fails - restructure to
              2 sequential challenger waves against a shared concurrent
              control instead of 3 simultaneous cells; Bonferroni correction
              applied for 2 comparisons (alpha 0.025 each)
```

---

## What to actually tell your marketing lead

Say this before the all-hands, not at it:

> "We can promise a statistically significant winner only if one concept beats the champion by roughly 50% or more on purchase rate — that's a blowout, not a normal creative win. If the real difference is a more typical 15-30% lift, which is common, we'll have a clear ranking on cost per purchase but not a 95%-confidence claim. I'd rather announce 'X is ranking ahead on CPA, here's the guardrail data, we're scaling it with eyes open' than a false-precision number that doesn't survive scrutiny."

If a 50%+ blowout does happen, you likely won't need the p-value to notice — it'll be obvious in the raw CPA gap well before day 28. The statistical machinery here mainly protects you from the opposite trap: crowning a winner off a 4-day, 40-conversion peek that's actually noise (see the skill's negative example — that's the failure mode this whole plan exists to prevent).