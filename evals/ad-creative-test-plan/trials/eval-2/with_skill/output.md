# CREATIVE TEST PLAN — CFO cost-cutting vs. automation time-saving, Veyra Systems LinkedIn demo-request

## The direct answer to your CRO first

**You cannot get a statistically significant winner on form fills in three weeks at $9,000/month, and no honest version of this test can.** Two independent numbers force that, before any formula:

1. **Stable-delivery floor.** LinkedIn's delivery algorithm needs ~~50 optimization events/week/cell to deliver reliably. At $120 CPA, that floor is **$857/day per cell**. Your test budget, split across a control + one challenger, gives each cell **~~$214/day** (front-loading the full $9k into 21 days) — **25% of the floor**. Both cells stay delivery-limited for the entire test; the numbers won't stabilize regardless of the sample math.
2. **Sample math.** At your 30% form-fill→qualified rate, detecting even a large 50% relative lift (30%→45%) needs ~163 qualified-eligible form fills per cell. At projected volume (~1.8 form fills/day/cell), that's **~91 days — 13 weeks, not 3**. Detecting a more realistic 20-30% lift needs 245–540 days.

The only way to buy significance inside 21 days is an ~$10k spend increase *and* an implausible effect (qualified rate roughly doubling). Real, defensible lifts (20-30%) would cost **$105k–$231k for the window** — 12-25x the test budget. That's not a negotiating position, it's arithmetic; see the table below.

What you _can_ honestly deliver in 3 weeks is a **directional screening read**: a ranked judgment call between the two angles on cost-per-qualified-lead, built on roughly 11 qualified leads per cell, clearly labeled as a ranking, not a "95% confidence" winner. If "form fills" is the number that goes upward regardless, report the **volume and CPA of form fills** as an operational fact, but do not let it be the metric that declares a winner — cheap form fills that sales rejects are a guardrail breach, not a win, and that's exactly the trap this budget/timeline sets.

Options to give your CRO, not just a "no":

| Option                                 | What changes                        | What you get                                                                                                                                 |
| -------------------------------------- | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **A. Ship the directional plan below** | Nothing — run as designed           | A ranked call by day 21, labeled Directional, with a real (Powered) qualified-lead read arriving ~13 weeks later if you keep both cells live |
| **B. Extend the window, same budget**  | Deadline moves to ~13 weeks         | A real Powered read on qualified-lead rate, but only if the true lift is ≥50% (unlikely for a messaging swap)                                |
| **C. Raise the budget, keep 3 weeks**  | Budget → ~$40k-$105k for the window | A real Powered read at a defensible 30-50% MDE                                                                                               |
| **D. Both — realistic ask**            | ~6-8 weeks, ~2-3x current budget    | Powered read at a 30-40% MDE, the honest middle ground                                                                                       |

I've designed the plan below as **Option A**, since that's what your stated budget and deadline actually support. If the CRO picks B/C/D instead, the isolation and structure below don't change — only the feasibility numbers and stop date do; I'll recompute on request.

---

## Assumptions I'm stating rather than asking about, since you want the full deliverable now

Flagging these so you can correct any before launch — the plan's cell budgets and asset counts depend on them:

- **4 assets per cell** (not stated). If your creative capacity differs, cell budgets per asset move but not the totals.
- **Automated creative optimization (LinkedIn's dynamic/audience expansion features) is OFF inside test cells.** Confirm — if it's on, the platform picks the winner, not the test.
- **Full $9,000 monthly test budget is front-loaded into the 21-day window** (~$428/day total) rather than spread evenly across the month (~$300/day), because that's what gives the CRO's 3-week ask its best chance. This uses the entire month's test allocation in 3 weeks, leaving nothing for the remaining ~9 days — confirm that trade is acceptable.
- **"Automation time-saving" is the current always-on angle** — it becomes the control, relaunched concurrently at matched budget, not compared to its historical/scaled numbers (those aren't comparable — different delivery history and seasonality).
- **Qualified-lead status (the 30% SQL-acceptance figure) is knowable within days of a form fill**, not gated behind the 4-month sales cycle — the sales cycle is opportunity→close, which lags further. If that assumption is wrong and qualification also takes months, this test cannot even produce a directional read in 3 weeks; say so and I'll redesign around CTR/gate signals only.
- **No prior angle-test history was given** — the hypothesis magnitude below is a screening target, not evidence-backed. Replace it if you have prior data on finance-persona response.

---

## 1. Decision and hypothesis

**Decision:** Based on this test, the higher-cost-per-qualified-lead cell gets deprioritized for next testing cycle's budget; the winner (by ranking, not significance) gets a scale step. Neither angle is permanently retired off a 3-week read.

**Hypothesis:**

```
Because procurement software buying committees for $45k+ ACV deals typically
include a budget-holder motivated by cost avoidance, changing the LinkedIn ad
angle from "automation time-saving" to "CFO cost-cutting" will raise the
qualified-lead rate by roughly 20-30% relative (30% -> 36-39%) for LinkedIn
demo-request traffic, and we will know DIRECTIONALLY by day 21 — full
statistical significance at that magnitude would require ~35-77 weeks at
current budget, not 3 weeks, so day-21 is a ranking, not a verdict.
```

## 2. Isolation level

**Bundled concept-level test — unlearnable at element level.** The angle change carries new headline, body copy, and visual treatment together (CFO/finance framing vs. automation/time framing). This is deliberate, not a shortcut: your hard 3-week deadline deletes tiered testing outright (one test window before the decision date), and strict single-variable isolation is already ruled out by the feasibility math above (single-element effects are smaller than the bundled effect, and the bundled effect itself isn't powered at this volume). Bundled is the only posture that fits the constraints — it buys a ranking, not an "angle vs. hook vs. visual" learning.

## 3. Cell matrix

- **Control**: `C01_ANG-automation-timesaving` — current champion, relaunched fresh and concurrent (never compared to its historical account numbers).
- **Challenger**: `C02_ANG-cfo-costcutting` — new angle.
- 4 assets per cell (variations executing the same concept — same angle, different hooks/formats).
- **Structure: manual fixed-budget cells**, $214/day each ($4,494/cell over 21 days, ~$8,988 total ≈ your $9,000 cap). Default structure — comparable, if imperfect (auction overlap noted below). LinkedIn's native Split Test is the cleaner structure but adds 1+ week to time-to-answer, which your deadline doesn't have room for.
- **Automated creative optimization: off.**

**Naming convention:**

```
C02_ANG-cfo-costcutting_HOOK-fear-of-overspend_FMT-single-image_TAL-none_V01
```

Concept ID — angle — hook — format — talent — version. Every asset name follows this exact field order; reporting rolls up by parsing it.

## 4. Feasibility check

|                                       | Control (C01)                                       | Challenger (C02)     |
| ------------------------------------- | --------------------------------------------------- | -------------------- |
| Daily budget                          | $214/day                                            | $214/day             |
| Projected form fills                  | ~1.79/day (~12.5/wk)                                | ~1.79/day (~12.5/wk) |
| Stable-delivery floor                 | $857/day                                            | $857/day             |
| Floor met?                            | **No — 25% of floor, delivery-limited all 21 days** | **No — same**        |
| Projected qualified leads (21d, @30%) | ~11                                                 | ~11                  |
| Total form fills (21d)                | ~38                                                 | ~38                  |

**Required sample for Powered, on qualified-lead rate (30% baseline), per cell:**

| Relative MDE                | n required/cell | Total spend (both cells) | Days at current front-loaded pace |
| --------------------------- | --------------- | ------------------------ | --------------------------------- |
| 20% (30%→36%)               | ~962            | ~$231,000                | ~540 days                         |
| 30% (30%→39%)               | ~437            | ~$105,000                | ~244 days                         |
| 50% (30%→45%)               | ~163            | ~$39,100                 | ~91 days                          |
| 100% (30%→60%, implausible) | ~42             | ~$10,100                 | ~24 days                          |

**VERDICT: Directional read, delivery-limited, declared.** No MDE reachable at significance within the 21-day hard stop or even the standard 4-6 week ceiling at current budget. This mirrors the standard shape of B2B lead-gen tests at this volume — not a design flaw, a budget/volume reality that must be said out loud rather than hidden behind a peeked "95% confidence" number.

Only 2 cells (control + 1 challenger) = 1 comparison, so no multiple-comparison correction needed.

## 5. Metric ladder

- **Gate** (screen only, never crowns): CTR / engagement rate vs. account trailing median, compared like-for-like by placement, read only once an asset clears ~2,000 impressions. Kills obvious losers cheaply and early — but a $1.47M cross-account analysis found no significant correlation between hook-rate and downstream revenue, so a CTR win here proves nothing about lead quality.
- **Primary (decision metric): cost per CRM-qualified lead / qualified-lead rate**, fed back from CRM — **not raw form fills**, even though form fills are what you report upward. This is the one place I'd push back on the CRO's framing directly: optimizing or judging on raw form fills at $120/fill with no quality filter risks crowning whichever angle is cheapest to click on, not the one that produces pipeline sales will work. Report form-fill volume and CPA as an operational fact alongside the qualified-lead read — just don't let it be the tiebreaker.
- **Guardrails**: lead-to-qualified rate ≥ account trailing median (30%); frequency (LinkedIn B2B audiences for a $45k ACV product are narrow and saturate fast); CPL drift vs. account baseline ($120); cost-per-qualified vs. baseline ($400).

## 6. Pre-registered decision rules (Denney anchor, adapted for low volume)

Denney is the default anchor here (no stated media-buyer bandwidth or benchmark library to support Hott's comparative-judging method; nothing rules out Denney) — adapted where the standard cadence assumes more volume than this account has:

- **No evaluation before day 3.**
- **Kill an asset** at 2× CPA spend ($240) with zero form fills. At ~4 assets/cell sharing $214/day, each asset reaches that threshold in ~4-5 days — leaves room to reallocate mid-window.
- **No mid-window cell kill.** Denney's standard "kill the cell after 5-7 days with no winner" doesn't apply — at ~12.5 form fills/week/cell, 5-7 days of data is noise, not a signal. Both cells run the full 21 days.
- **Scale**: at hard stop, if the challenger ranks ahead on cost-per-qualified-lead AND the guardrail (lead-to-qualified ≥30%) holds, it gets +50% budget next testing cycle. Treat that first scale step as its own read (regression to the mean on a low-spend "winner" is a real risk at n≈11).
- **Iterate**: if the challenger wins the CTR gate but not cost-per-qualified (or vice versa), that's inconclusive — check the landing page/offer before touching creative again.
- **Fixed stopping rule**: day 21 or $9,000 total spend, whichever first. **Inconclusive → keep control** (automation angle), decided now, not at readout.
- **No peeking.** The 21-day/qualified-lead numbers don't get checked and acted on before day 21 — early reads at this volume are pure noise and will look dramatic.
- **Second look (mandatory, scheduled now, not skipped)**: opportunity-creation rate per cell at ~day 130 (one full sales cycle from launch), since a 21-day ranking on ~11 qualified leads is not the revenue verdict.

## 7. Plan document

```
CREATIVE TEST PLAN - CFO cost-cutting angle screen, 2026-09-12
decision    : winning angle (by ranking, not significance) gets next cycle's
              test-budget priority; loser is not retired off this read alone
hypothesis  : because procurement buying committees include a cost-averse
              budget holder, a CFO cost-cutting angle will raise qualified-
              lead rate ~20-30% relative (30%->36-39%) vs the automation-
              time-saving champion, for LinkedIn demo-request traffic, known
              DIRECTIONALLY by day 21 (real significance needs 13-77+ weeks
              at this budget - see feasibility table)
isolation   : bundled - unlearnable at element level (angle + copy + visual
              treatment change together; labelled so no element-level
              insight is mined from this result)
structure   : 1 challenger cell + control, concurrent, manual fixed-budget
              cells $214/day each; automated creative-optimization: off
metrics     : gate = CTR vs account trailing median, per placement, read at
              >=2,000 impressions/asset (screens only, never crowns)
              primary = cost per CRM-qualified lead / qualified-lead rate
              (never raw form fills - report form-fill volume/CPA
              separately as an operational number, not the decision metric)
              guardrails = lead-to-qualified rate >=30% (account trailing
              median); frequency; CPL drift vs $120 baseline; cost-per-
              qualified vs $400 baseline
cells       : C01_ANG-automation-timesaving (control) | $214/day | 4 assets
              projected ~12.5 forms/wk, ~3.75 qualified/wk
              C02_ANG-cfo-costcutting (challenger) | $214/day | 4 assets
              projected ~12.5 forms/wk, ~3.75 qualified/wk
              required (qualified rate, 50% MDE): n=163/cell, ~$39,100
              total, ~91d -> exceeds both deadline and 4-6wk ceiling
              -> VERDICT: Directional read, delivery-limited, declared
              kill: asset at $240 spend (2x CPA) with zero form fills;
                    no mid-window cell kill (volume too thin before day 21)
              scale: ranked winner at hard stop -> +50% budget next cycle,
                     treated as its own read (regression-to-mean risk)
              iterate: gate/primary split result -> check landing page/
                       offer before further creative iteration
schedule    : launch Mon 2026-09-14 | earliest evaluation day 3
              (2026-09-17) | hard stop day 21 (2026-10-04) or $9,000
              spent, whichever first | inconclusive -> keep control
              | second look 2027-01-22 (~day 130, one sales cycle):
              opportunity-creation rate per cell from CRM
naming      : C##_ANG-<angle>_HOOK-<type>_FMT-<format>_TAL-<talent>_V##
caveats     : both cells run at ~25% of the stable-delivery floor for the
              entire window - numbers stay noisy regardless of ranking;
              manual cells share the same LinkedIn auction/audience pool,
              inflating cost and blurring attribution between cells;
              divergent delivery means even the ranking is relative
              screening, not causal, per Braun & Schwartz (2025); day-21
              result will be reported as a ranking on ~11 qualified leads
              per cell, never as a "winner at 95% confidence"; if the CFO
              angle cites specific $ or % savings figures, route those
              claims through legal/product marketing before launch -
              LinkedIn and B2B buyers scrutinize unsubstantiated cost claims
```

## What to send up as "the number," honestly

If leadership needs a form-fill number regardless: report **total form fills and blended CPA per cell** as the operational read (it's real, it's just not the decision basis), and report the **qualified-lead ranking, labeled Directional**, as the actual test outcome. Don't let the first metric silently become the headline the second one should own — that's precisely the "cheap leads sales rejects" failure mode this budget and timeline are set up to produce if nobody says so out loud.
