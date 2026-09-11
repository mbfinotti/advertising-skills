# Ostrena — Reworking the Spend Guardrails

## Why the current rule kills every new launch

A flat **2.8x ROAS on everything** collapses three things that need to stay separate: the point where spend loses money, the level you actually want to run at, and the point where you pull the plug. When one number does all three jobs, every new channel or audience — which starts cold, thin on data, and naturally below any steady-state ROAS — reads as a "breach" from day one and gets killed before it had a fair chance to prove out. That's the mechanism behind "dies within a week," not bad luck with channels.

Three concrete faults in the current rule:
- **No evidence gate.** Nothing stops a kill decision before enough spend or enough time has passed to be meaningful. A week is shorter than most platforms' learning phase (Meta typically needs ~50 optimization events in a rolling week to exit learning) — you are very likely judging cold, unstable delivery, not the audience's real economics.
- **No separation between proven and exploratory spend.** New channels/audiences are held to the same bar as your scaled Meta/Google core, which is exactly backwards — testing should have a looser, spend-based rule, not the tightest one in the account.
- **Blended-only measurement.** A single ROAS number hides whether the *marginal* dollar (the one a new channel represents) is profitable, versus the *average* dollar across a mature account. You already have the fix for this sitting in-house.

## Architecture: why the portfolio model is the right call here

Normal ranking (efficiency: tiered ladder > single floor > portfolio; effort: single floor > ladder > portfolio) would put the portfolio model last on cost. But the skill's own override condition is your exact situation: *"An account that already owns the expensive parts — a live margin feed, an analyst who reads marginal efficiency — collapses its effort axis and promotes it on cost."* Your analyst already tracking marginal returns weekly is precisely that asset. Combined with "an efficiency bar has already strangled testing" (your media buyer's complaint, literally), the portfolio model is promoted above its default rank.

**Recommendation: run both, on different pools of spend.**
- **Tiered ladder** governs the proven $85K core (existing Meta/Google campaigns at steady state).
- **Portfolio model with a ring-fenced exploration budget** governs every new channel and new audience launch, exempt from the core ROAS/MER floor and judged on its own spend-based rule instead.

This is cheaper to run than it looks precisely because your analyst already does the marginal-efficiency read the portfolio model needs — you're not standing up new capability, just pointing existing capability at a carved-out budget.

---

## Gate on measurement — what's missing before the numeric floors can be finalized

Following the skill's rule against fabricating inputs: I do not have your contribution margin, AOV/price bands, current CAC variant, payback target, cash runway, growth stage, named approvers, or what happened the last time performance dropped. **The numeric floors below are formulas and provisional placeholders, not final numbers — do not operate against them until margin is confirmed.** One usable signal: your existing 2.8x bar implies a break-even contribution margin of **1 ÷ 2.8 = 35.7%** *if* it was ever derived from your margin rather than picked as a round-ish number. Confirm which — if your real CM3 is higher, 2.8x has been over-tight this whole time; if lower, you've been losing money on a chunk of "passing" spend.

```
SPEND GUARDRAIL POLICY - Ostrena, effective <pending sign-off>, review <90 days after effective>

Inputs
  Contribution margin (CM3)        MISSING - required to compute break-even
  AOV / price bands                MISSING
  Current CAC (variant)            MISSING - specify paid / blended / new-customer
  Payback target                   MISSING
  Cash runway / monthly burn       MISSING - sets the cash cap, independent of ROAS
  Implied margin from 2.8x floor   35.7% (1 / 2.8) - HYPOTHESIS, confirm or discard

Derivation (formulas - fill once CM3 is confirmed)
  Break-even MER  = 1 / CM3
  Break-even CAC  = AOV x CM3
  Target MER      = set from the profit the plan needs above break-even, not folklore
  Cash cap        = runway-derived monthly ceiling, stated as a dollar figure
                    independent of efficiency

Layers (core $85K program)
  Break-even floor   MER = 1/CM3            -> stop, always
  Target floor        <pending CM3>          -> investigate within the weekly review
  Hard floor           <pending CM3, set below target, at/above break-even>
                                              -> automatic halt of the breaching
                                                 channel + escalation

Guardrail set - core program (2-3 metrics, weekly cadence)
  1. Blended MER (platform-agnostic: total revenue / total spend)
     counter-metric: new-customer share of orders - catches a floor met by
     harvesting retargeting/branded search instead of real growth
  2. Marginal MER on the last tranche of spend, read by your analyst at every
     scale-up decision
     counter-metric: none needed - this IS the scaling gate
  3. Contribution margin after ads (once a margin feed is confirmed live)
     counter-metric: discount depth - margin propped up by promo isn't real margin

Kill rules - core program
  Streak     marginal or blended MER below hard floor for 3 consecutive weekly
             reads (your analyst's existing cadence)
  Rate       30% of a channel's monthly budget burned with MER below hard floor
  Evidence   no kill before 2 full weeks of data AND enough spend to clear
             platform learning phase (~50 conversions/week on Meta); a channel
             below either bar is held flat, never killed
  Restart    restart at 50% of prior budget after a documented, named fix;
             reviewed at 3 weeks before returning to full budget

Exemptions - exploration budget (fixes "dies in a week")
  Size        10-15% of the $85K core = $8,500-$12,750/month, ring-fenced,
              NOT counted against the core MER floor
  Rule        spend-based evidence gate, not a ROAS floor: no kill before
              $1,000-$1,500 spent per new channel/audience AND 14 days live
              (longer than one Meta learning-phase cycle) - both bars must clear
  Decision    at the gate: keep (graduate into core program, now subject to the
              tiered floors above), extend (one more gate cycle, capped), or cut
  Owner       media buyer proposes, analyst reads marginal signal, Growth/Founder
              approves graduation into core spend

Governance
  Owner        <name> owns break-even/cash inputs (finance role, not the spender)
               <name> owns target and hard floors (Growth/media lead)
  Escalation   target breach -> weekly review
               hard breach   -> same-week decision by <named approver>
               break-even breach -> immediate halt, no discretion
  Separation   the media buyer operates under this ceiling but cannot raise it -
               only <named approver> can, in writing, time-boxed
  Override     max 14 days above target floor with a logged reason; anything past
               break-even requires the finance-role co-sign; never standing
  Re-baseline  quarterly, plus on: margin change, pricing change, platform
               measurement/pixel change, or a change to what "conversion" means

Assumptions
  35.7% implied margin from the old 2.8x floor is unconfirmed. Real CM3, AOV, CAC
  variant, cash runway and named approvers are all missing - this policy is
  PROVISIONAL until those are supplied and the numeric floors are recomputed.
```

## What to do next

Hand the media buyer and analyst the exploration-budget rule immediately — it's the piece that unblocks new launches and doesn't depend on the missing inputs. In parallel, get contribution margin confirmed (finance-reviewed, not a guess) so the core program's target and hard floors stop being placeholders, then name the actual approvers before this policy governs a real dollar.