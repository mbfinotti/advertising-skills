# Creative Test Plan — Merrow & Finch, 2026-09-12

## 0. Verdict on the proposed workaround — rejected, with the fix

**Running 10 weeks instead of 4 does not solve the problem you have, and it creates two new ones.**

- Your $500/day ÷ 4 cells = **$125/day/cell**. The purchase event ($180 CPA) needs a stable-delivery floor of **target CPA × 50 ÷ 7 ≈ $1,286/day/cell** just to stop being delivery-limited. You're at **9.7% of that floor**. This is a *rate* problem (events/week), not a *volume* problem — stretching the calendar doesn't raise the weekly rate. At $125/day/cell you get ~4.9 purchases/week/cell no matter how many weeks you run. Even at 10 weeks that's only ~49 purchases/cell — still under even the loosest "100-400 conversions" screening convention, let alone a statistically powered read.
- Separately, 10 weeks blows through the **4-6 week duration ceiling** the skill sets for a reason: past that window, novelty decay and creative fatigue contaminate the comparison between week-1 delivery and week-10 delivery on the *same static assets*. You'd be trading "underpowered" for "underpowered *and* contaminated."

**What actually rescues this test is the thing you weren't sure mattered: add-to-cart.** At $12/ATC, the stable-delivery floor is only $85.71/day/cell — your $125/day/cell clears it at 146%. Projected ~73 ATC/week/cell, and over a proper 6-week window (the ceiling, not 10) that's ~438 ATC/cell — squarely in the community-convention band for a legitimate **Directional** screening read. Purchase stays a lagging guardrail, not the decision metric. This is the "move the read up-funnel" fix, and it's the only lever available to you: raising budget is closed (finance, twice), and dropping to fewer cells wouldn't get purchase anywhere near its floor either (3 cells at ~$166/day is still ~13% of the $1,286 floor).

So: **keep the existing $500/day, run 6 weeks (not 10), decide on add-to-cart, track purchase CPA as a directional guardrail only.** No new money, no finance ask, no calendar violation.

## 1. Assumptions and missing inputs

The skill wants these asked one at a time before designing; you asked for the deliverable directly, so here's what I assumed instead of asking, flagged so you can correct any of it before launch:

| Missing input | Assumption used |
|---|---|
| Baseline click-through / landing-page session volume (CPC or CTR) | **Not available** — means I cannot run the formal two-proportion required-n-in-clicks formula for either metric. Verdicts below use cost-per-event volume math (stable-delivery floor, Denney-style thresholds) instead, which don't require it. If you can get me CPC or weekly sessions, I can upgrade the add-to-cart verdict from Directional toward Powered. |
| Exact decision this test informs | Assumed: winning concept (by ATC ranking, guardrails intact) becomes the new control next cycle; losers retired. No budget increase implied or requested. |
| Existing champion/control creative | Assumed it exists, since you said "3 concepts plus control." |
| Assets per concept | Assumed 4 per cell (within the 3-6 range); confirm before launch. |
| Automated creative optimization (Advantage+/dynamic creative) status | Assumed unknown — **must be verified off** in test cells regardless (see structure line). |
| Refund / sleep-trial return window | Assumed premium-mattress-typical (often 90-365 nights) — long enough that the refund-rate guardrail will not have fully resolved by the day-42 stop. Scheduled a second look below; confirm your actual trial length. |
| Prior tests / settled questions | Not provided — assumed none, so nothing here is a re-test of a settled question. |
| Claim-substantiation constraints | Not provided — flag if any concept makes a health/orthopedic/sleep-quality claim; that needs a compliance pass this plan doesn't cover. |

## 2. Decision and hypothesis

```
decision: Based on this test, whichever new concept ranks best on add-to-cart
rate vs. the control, without degrading directional purchase CPA or refund
rate, becomes the new control next cycle. Losing concepts are retired. No
budget increase is requested or assumed — same $500/day.

hypothesis: Because [insert the actual customer/creative evidence behind each
concept — reviews, research, prior signal], changing [concept/angle] will
raise add-to-cart rate by a large, easily-detectable margin (realistically
only 30%+ relative lifts are visible at this volume) vs. the control, for
[confirm: cold prospecting / existing audience], and we will know by day 42
or 400 add-to-cart events/cell, whichever comes first.
```

The bracketed parts are yours to fill — I have no visibility into what the three concepts actually are or why they were chosen, and I'm not going to invent supporting evidence for them.

## 3. Isolation level

**Bundled concept-level ("big swings") — unlearnable at element level.** Three "new concepts" is definitionally a bundled test: each cell varies messaging + execution together. This is also the only posture with a realistic chance of a detectable effect at $125/day/cell — strict single-variable isolation is not on the table at this budget (deleted: no lever this small can isolate hook-vs-format-vs-talent and still clear even the ATC floor per sub-variant).

## 4. Cell matrix and structure

```
structure: 4 cells (1 control + 3 concepts), manual fixed-budget,
$125/day each ($500/day total, unchanged from your allocation).
Automated creative-optimization (Advantage+/dynamic creative etc.): OFF —
verify this before launch, not assumed from data given.
```

- Control: current champion, running concurrently at the same $125/day — never compared to its historical numbers.
- One concept per cell, ~4 assets/cell (confirm you have them at this lead time).
- Platform-native deterministic split test: not recommended — at $125/day/cell it would take longer to answer with no better odds of significance, and you have a hard cost constraint, not a hard causality requirement.
- Campaign-level automatic allocation: ruled out outright (can concentrate ~90% of spend on an early leader and corrupt the read).

## 5. Feasibility math (shown for audit)

**Purchase ($180 CPA):**
- Stable-delivery floor: $180 × 50 ÷ 7 = **$1,286/day/cell** required. Available: $125/day/cell = **9.7% of floor**.
- Projected: 125/180 = 0.69/day → **4.86/week/cell**.
- Cumulative at 6 weeks (42d): **~29/cell**. At the rejected 10-week version: **~49/cell**.
- Even the loosest event-count screening convention (100-400 conversions/variant) is not reached at either duration.
- **VERDICT: Not testable as designed on purchase, at any duration within (or even beyond) reasonable bounds.** This is a hard floor problem, not a sample-accumulation problem.

**Add-to-cart ($12/event):**
- Stable-delivery floor: $12 × 50 ÷ 7 = **$85.71/day/cell** required. Available: $125/day/cell = **146% of floor — clears it.**
- Projected: 125/12 = 10.42/day → **72.9/week/cell**.
- Cumulative at 6 weeks (42d): **~438/cell**.
- Falls inside the community "100-400 conversions/variant" screening band (upper end). This is real, legitimate ranking-grade volume.
- Formal Powered/Directional call via the two-proportion formula needs baseline click/session data I don't have — so I can't certify "Powered." **VERDICT: Directional read on add-to-cart**, and I'm confident in that call independent of the missing rate data because the event count clears the practitioner screening threshold with room to spare.
- Spend-tier cross-check: $500/day ≈ $15k/month sits in the "under $20k/month" tier — proxy-gated screening only is the honest ceiling for this budget, which is exactly what this plan delivers.

**Multiple comparisons:** 3 concepts vs. control = 3 comparisons, disclosed. If you later get budget to chase significance, apply a Bonferroni-style correction (~30-40% more sample) — moot for now since purchase is untestable regardless and ATC is being read directionally, not as a significance claim.

**Lever check on the "Not testable" purchase cell** (fixes ranked: up-funnel > wider MDE > fewer cells > more budget):
- *Raise the budget* — **deleted**, named explicitly: finance has closed this door twice this quarter.
- *Move up-funnel* — **applied**: add-to-cart is the primary decision metric for exactly this reason.
- *Widen the MDE* — doesn't help here: it lowers required sample, but does nothing to the weekly event *rate*, which is what's actually failing (delivery-limited, not underpowered).
- *Fewer cells* — available but not worth it: even 2 cells (~$166-250/day) stays under 20% of the purchase floor. Not pursued; flag if you want the tradeoff spelled out.

## 6. Metric ladder

```
metrics: gate = hook rate/CTR vs. account trailing median, per placement,
         no read before ~1,000-2,000 impressions/asset
         primary = add-to-cart rate/ranking (Directional — the decision-
         bearing metric at this budget)
         secondary (lagging, non-decision) = purchase CPA — tracked as a
         directional guardrail only, never reported as a winner
         guardrails = frequency, CPM vs. account baseline, refund/return
         rate (lags the day-42 stop — see schedule), blended account CPA
```

## 7. Pre-registered decision rules

Anchor: **Dara Denney's set** — the default rung, since nothing here indicates a maintained best-ads benchmark library plus a weekly reviewer (which would be required to promote to Hott). Adapted to ATC as the operative "conversion" since that's the metric with real volume:

```
kill (asset)  : 2x cost-per-ATC ($24) spend with zero add-to-carts
kill (asset,
 catastrophic) : 2x CPA ($360) spend with zero purchases — a guardrail
                 circuit-breaker, not the primary read
kill (cell)    : no clear ATC-rate leader after day 14 checkpoint — flagged
                 for attention, not auto-killed before earliest evaluation
scale          : winner becomes new control next cycle, absorbing the
                 largest share of the same $500/day — NOT a budget increase
iterate        : a concept that wins ATC but shows directional CPA or
                 refund-rate degradation -> landing-page/offer check before
                 any creative iteration (high gate + low downstream = offer
                 problem, not a creative problem)
```

## 8. Schedule

```
schedule: launch Monday | earliest evaluation day 10 (and >=50 ATC/cell,
          whichever later) | hard stop day 42 (6 weeks) or 400 ATC/cell,
          whichever comes first | inconclusive -> keep control
          second look: refund-rate guardrail re-checked once your sleep-
          trial/return window closes (mattress returns lag the creative
          verdict the same way a B2B sales cycle does — schedule it,
          don't skip it)
```

## 9. Naming convention

```
C0#_CPT-<concept-name>_HOOK-<type>_FMT-<format>_V0#
```

Example: `C02_CPT-firmness-guarantee_HOOK-question_FMT-ugc-video_V01`

## 10. Full plan document

```
CREATIVE TEST PLAN - concept screen, 2026-09-12
decision    : winning concept (by add-to-cart ranking, guardrails intact)
              becomes new control next cycle; losers retired; no budget
              change from current $500/day
hypothesis  : because [ADD: evidence per concept], changing [concept/angle]
              will raise add-to-cart rate by a large (~30%+ relative)
              margin vs. control, for [ADD: audience], known by day 42 or
              400 ATC/cell
isolation   : bundled - unlearnable at element level (3 concepts, full
              execution bundled per cell)
structure   : 4 cells (1 control + 3 concepts), manual fixed-budget,
              $125/day each; automated creative-optimization: OFF (verify)
metrics     : gate = hook rate vs. trailing median, per placement
              primary = add-to-cart rate (Directional)
              secondary = purchase CPA (guardrail only, not testable)
              guardrails = frequency, CPM vs. baseline, refund rate
cells       : C01_CPT-control (control) | $125/day | ~4 assets
              C02/C03/C04_CPT-<concept> | $125/day each | ~4 assets each
              projected: 72.9 ATC/wk/cell, 4.86 purchases/wk/cell
              ATC: 438 events/cell @ 42d -> VERDICT: Directional read
              purchase: 29 events/cell @ 42d -> VERDICT: Not testable as
                designed (floor is $1,286/day/cell; have $125/day/cell)
              kill: asset at $24 spend (2x cost/ATC) w/ zero ATC, or $360
                spend (2x CPA) w/ zero purchases
              scale: winner -> new control, same total budget reallocated
              iterate: ATC win + CPA/refund degradation -> offer/LP check
schedule    : launch Mon | earliest eval day 10 (min 50 ATC/cell) |
              hard stop day 42 or 400 ATC/cell, whichever first |
              inconclusive -> keep control | refund-rate second look after
              sleep-trial window closes
naming      : C0#_CPT-<concept>_HOOK-<type>_FMT-<format>_V0#
caveats     : manual cells share auctions (overlap noted); divergent
              delivery means even this Directional read is relative
              screening, not causal proof; purchase CPA is guardrail-only
              and must never be reported as a tested winner; formal
              Powered verdict on ATC is blocked on missing CPC/session
              data - supply it to upgrade the call; 10-week duration
              rejected - breaches the 4-6wk freshness ceiling and does not
              fix the purchase floor regardless of length
```

**Completion bar check:** every cell has a declared verdict (Not testable / Directional), computed sample/spend/duration, pre-registered kill and scale thresholds, and a named primary metric with guardrails. The one open item before this ships is the CPC/session data — without it the plan runs as written, but you're leaving a possible upgrade (Directional → Powered on add-to-cart) on the table.