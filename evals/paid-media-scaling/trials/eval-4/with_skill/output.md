# Media Scaling Ramp — LinkedIn Compliance-Software Lead Gen

**Bottom line first:** the plan as described — $20K → $45K next month, judged weekly — fails on gates before step size is even a question. Two of your own side notes are the evidence. I'm not shipping a smaller version of that plan as a consolation prize; I'm naming the failures and building the ramp that survives them.

## Why the ask as stated doesn't ship

**1. Your measurement-health gate is failing, and the fix you picked is backward.**
LinkedIn overcounting vs. CRM is the single most common B2B paid-media failure this skill tracks: *falling CPL reads as success while pipeline quality erodes — the proxy breaks, not the ads.* The standing rule for this exact situation is **when platform and CRM disagree, the CRM wins** — you're doing the opposite. Trusting LinkedIn "because CRM lags" conflates two different problems: CRM *timing* lag (real, expected) vs. CRM *count* disagreement (a tracking/definition bug — duplicate leads, gated-form conversions firing before CRM qualification, etc.). Until that gap is diagnosed, your CPL of $61 is not a trustworthy number.

**2. Discovery calls "feeling lighter" is your lead-quality proxy breaking, not sales complaining.**
Sales always complains — true, and also the exact line a real signal hides behind. You cut spend efficiency (CPL $95→$61) at the same moment sales flags softer calls. That correlation is the textbook pattern for creative/targeting broadening to reach weaker prospects as spend rises. It needs a number (a quality score on discovery calls), not a dismissal.

**3. The math doesn't fit "next month."**
$45K is +125% in one move and 2.25x your current spend — past the 2x line where attribution-only evidence stops being sufficient on its own. Your sales cycle is ~4 months; you have 6 weeks of history on the *current* tier. You cannot have "working great" verified by anything but CPL yet — closed-won on this cohort doesn't exist. Evaluating weekly compounds this: a week is far short of learning-phase-plus-conversion-lag for a 4-month deal cycle, even on leading indicators.

## Readiness gates

| Gate | Status | Basis |
|---|---|---|
| 0. Affordability (nCAC ceiling from LTV/margin) | **UNKNOWN** | Have ACV ($28K) only — no gross margin, refunds, or OpEx to derive a max-CAC boundary |
| 1. Data maturity | **FAIL** | 6 weeks doesn't cover one learning cycle + 4-month lag; "working" = CPL only |
| 2. Marginal economics | **FAIL** | No approved CAC/margin boundary to compare against; CPL itself is disputed |
| 3. Measurement health | **FAIL** | Unresolved LinkedIn-vs-CRM conflict; CRM should arbitrate and currently doesn't |
| 4. Creative supply | **UNKNOWN** | Not provided — need proven-ad count vs. ~budget÷$5,000 (folklore ratio, calibrate) |
| 5. Business absorption (sales capacity) | **UNKNOWN / at-risk** | Discovery-call complaint may be early speed-to-lead or quality strain |
| 6. Rollback pre-committed | **FAIL as proposed** | No named trigger or down-move exists in the current plan |

One passing/unknown-but-fixable gate does not offset three fails. Per the gate discipline: name the failure and fix it — don't ship a smaller jump instead.

## Evidence bar

**Attributed only, and internally contradicted.** No triangulation with CRM currently trusted, no causal test. Given the target crosses 2x current spend, this needs at minimum a resolved triangulated read (CRM as source of truth) before stepping past ~$40K; a true B2B holdout may not be feasible at this TAM — that gets confirmed during the fix sprint below, not assumed.

## Approach

Default order for this shape of account is vertical ladder → measure-first → horizontal. Two of the three promotion conditions for measure-first are met here (target is 2x+, and all current evidence is platform-attributed) — so it moves ahead of a pure percentage ladder. Horizontal isn't ruled out by anything known yet (penetration unreported) — parked, not deleted; revisit once reach data exists.

**Chosen approach: measure-first-flavored vertical ladder** — fix the measurement/quality signal first, then resume laddering on the corrected numbers. Same structure as a standard B2B compounding ramp, front-loaded with the diagnostic work this account is missing.

**Strongest case against this approach, stated honestly:** you lose a month of "next month" momentum, and if the CRM gap turns out to be a benign timing artifact and discovery calls are actually fine, this was a costly pause. I'm recommending it anyway because the downside of being wrong the other way — scaling a proxy that already broke — is a quarter of wasted spend and a sales team that stops trusting the pipeline, not one lost month.

## Step size

No usable account-history rung yet — one prior sized change ($12K→$20K, +67%) isn't enough to read reset behavior reliably, and that jump itself was already outside the standard band. Falling back to the **concrete default: 15–20% per step, held 3–5+ days minimum, never 30%+ in one move** (folklore, Demand Curve's $62K→$493K/90-day case used this exact band) — shipped only with the explicit instruction to recalibrate from history once 2–3 real steps exist. For a 4-month B2B cycle, hold windows extend to **a month or more per step**, judged on leading indicators, not last month's CPL (documented pattern for this vertical).

## The Ramp Plan

```
MEDIA SCALING RAMP  -  LinkedIn compliance-software lead gen, $20K → $45K/month
Gates        : affordability UNKNOWN (need margin data) | data maturity FAIL (6wks
               vs 4-month lag) | marginal economics FAIL (no CAC boundary) |
               measurement health FAIL (LinkedIn/CRM disagree, CRM should arbitrate)
               | creative supply UNKNOWN | absorption UNKNOWN (quality signal at risk)
               | rollback undefined until Phase 1
Evidence bar : attributed only, internally contradicted. Upgrade: CRM-reconciled
               triangulated read, required before any step past ~$40K (the 2x line)
Approach     : measure-first-flavored vertical ladder - promoted ahead of straight
               laddering because target is 2x+ current spend AND evidence is
               attribution-only (both promotion conditions met); horizontal parked,
               not deleted - no penetration data yet to judge saturation

Phase 0 - Fix sprint (Wks 1-3, spend held flat at $20K, no % step):
  - Reconcile LinkedIn vs CRM conversion counts for the last 6 weeks; find the
    root cause of the gap. CRM count becomes the source of truth going forward.
  - Confirm/build the offline-conversion loop (CRM stage → platform import) -
    precondition for judging any future step on this channel.
  - Score the last 6 weeks of discovery calls on a simple quality rubric
    (BANT-style or similar); get a baseline number instead of "feels lighter."
  - Get owner-approved margin/refund/OpEx inputs from ACV $28K to compute a
    max-CAC boundary (gate 0).
  - Count proven, non-fatigued ads and monthly creative test throughput
    (gate 4 - compare against ~budget÷$5,000, folklore ratio, calibrate).
  - Pull 30-day audience penetration, frequency, and CPM trend.

Steps (Phase 1, only after Phase 0 gates clear; dates assume a 3-week fix sprint):
  M1 (Wk4)  $23-24K (+15-20%) | hold 4 wks | cost-per-SQL ≤ boundary from gate 0,
            quality score ≥ Phase-0 baseline, frequency <3, CRM/LinkedIn gap tracked
  M2 (Wk8)  $27-29K (+15-20%) | hold 4 wks | same set + creative-count check
  M3 (Wk12) $32-34K (+15-20%) | hold 4 wks | same set + penetration/reach check
  --- 2x-current checkpoint (~$40K): triangulated-or-causal read required before
      crossing it. State plainly if a clean holdout isn't feasible at this TAM
      rather than skip the check. ---
  M4 (Wk16) $38-40K (+~15%)  | hold 4 wks | checkpoint read gates this step
  M5 (Wk20) $44-45K          | hold 4 wks | confirm at target on cost-per-SQL and
            quality score, not CPL alone
Rollback     : cost-per-SQL >1.5x target across a full hold → cut 20-30%,
               stabilize 2 wks, resume +10%/step (practitioner convention).
               Quality score drops OR falling-CPL-with-flat-SQL-volume at any
               point → freeze the ramp immediately at last good tier - the proxy
               broke, don't push through it. Instant cut reserved for runaway
               spend, policy exposure, or confirmed tracking corruption.
Ceilings     : sales capacity/lead quality is the leading suspect for what binds
               first (the discovery-call signal), ahead of creative or audience -
               this is a hypothesis to confirm in Phase 0, not yet a fact.
               Creative supply, cash, and penetration remain open until measured.
Exit         : $45K reached with cost-per-SQL and quality score inside boundary
               at every tier, OR marginal contribution margin ≤ $0 once
               computable, OR penetration crosses ~35% (switch remainder
               horizontal), OR quality score keeps declining despite the fix
               sprint → stop and re-check business/market fit before spending
               more, not just channel tactics.
Open items   : gross margin/refund/OpEx inputs (gate 0) | CRM-vs-LinkedIn root
               cause | discovery-call quality rubric + baseline | proven-ad
               count + monthly test capacity | 30-day penetration/frequency/CPM |
               cash/working-capital ceiling for the ramp | approval authority
               and escalation size | one-off $45K push vs. a compounding program
               (changes whether Phase 0's cost is worth it - assumed compounding
               given the ongoing weekly-review cadence you described)
```

## What this means for "next month"

$45K/month arrives around **week 20 (~5 months out)**, not next month — and that's the honest output of your own inputs (4-month sales cycle, unresolved measurement conflict, one data point of scaling history). If the board/timeline pressure behind "$45K next month" is fixed and non-negotiable, that's a separate conversation about which gate to consciously waive and what risk you're accepting in writing — not something to route around by evaluating faster.

This is a plan, not an executed change — nothing here touches LinkedIn's budget settings. Tell me which of the open items you can answer now (margin data and the CRM reconciliation first — they unblock the most) and I'll tighten the dates and step sizes against real numbers instead of the folklore defaults.