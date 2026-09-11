# Settling the Halden Grove bidding debate

**Short version:** this isn't a manual-vs-automated question. It's a measurement question that's been misread as a bidding question. Fix that first; the bidding debate mostly dissolves once you do.

## Diagnosis

Run the **measurement gate** before any bid-strategy talk: does the tracked event (demo-request form fill) predict revenue? Your SDR team already answered that — most of the new leads are students and job seekers, not facilities directors. That's a fail on **event depth**, not a bidder malfunction.

This matches the canonical B2B failure mode: *optimizing raw form-fills — cost per lead improves while pipeline dies.* Cost per form fill down 30% with volume up is exactly what an automated bidder does when told "get me more of this label," and the label is wrong. The bidder is doing its job faithfully on a bad instruction.

Use the three-job framework (Pilot / Doctor / Teacher) to name which job is actually failing:

- **Teacher** — feeding the algorithm the business signal it can't see on its own (real lead quality). **This is the one failing.** Unqualified form fills are flowing in as if they were equally valuable conversions.
- **Doctor** — diagnosing whether the target is right. Secondary issue once the event is fixed.
- **Pilot** — monitoring delivery, catching drift. Not implicated by what SDRs are reporting.

Reframed this way, "go back to manual" and "never fight the machine" are both answering the wrong question. Manual bidding doesn't fix a bad conversion event — it just makes the same bad optimization visible instead of automated. You'd still be buying clicks that convert into form fills from students, just by hand, and slower.

## Candidate policies

1. **Re-point the optimization event to a qualified lead, feed automated bidding the corrected signal.** Push SDR qualification outcome (or the CRM stage where a lead is marked "ICP: facilities director, real opportunity") back to the platform as an offline conversion import, and switch the bid strategy to optimize toward *that* event instead of raw form fill.
2. **Layer value differentiation on top.** Once qualification flows back, assign real or tiered values (qualified facilities-director lead high, student/job-seeker lead zero or filtered out entirely) and move toward a return-goal strategy once volume and value integrity clear the documented minimums.
3. **Revert to manual bidding.** Regains a sense of control and legibility. Does nothing to the underlying signal — the same wrong audience keeps getting bid on, just without the platform's optimization pushing harder toward it. Also throws away the 30% cost efficiency and volume gains, which were real, just pointed at the wrong outcome.

**Ranked by value per unit of effort: (1) re-point the event > (2) add value differentiation > (3) revert to manual.**

- Option 1 is the fix that matches the actual diagnosis. Effort is coordination-heavy but one-time: get SDR qualification outcomes flowing back as a conversion import, redirect the bid strategy's optimization target. Reversible, and it's the change that determines whether options 2 and 3 are even worth discussing.
- Option 2 compounds option 1's payoff but needs qualification data to already be flowing and trustworthy — sequence it after, not instead of, option 1.
- Option 3 is cheapest to execute and cheapest in trust cost to the skeptical half of the team, but it's treating a symptom (discomfort with the black box) instead of the cause (bad signal). It doesn't even guarantee cost-per-form-fill gets worse — it just stops being efficiently wrong and starts being manually wrong.

**What this order starves:** the "black box trust" concern is real and shouldn't be waved away just because option 1 wins on ratio. Address it directly — see Change discipline below — rather than by reverting the strategy.

## Why the qualification event, not closed-won

Your sales cycle is ~4 months. Optimizing directly on closed-won would be too deep and too laggy for an automated bidder: thin volume per period, long feedback delay, high variance, slow to correct. Optimizing on raw form fill is too shallow: no lead-quality signal at all, which is the problem you have now.

SDR qualification sits in between — available within days, and it's the exact signal that separates "facilities director" from "student." That's the depth to import. Once qualified-lead volume is flowing and stable, decide later whether enough differentiated value exists to justify pushing further toward a return-goal strategy (option 2).

## What's still needed from you before the target can be set

Two derivations are required, and I don't have the inputs yet:

- **Economics (affordable ceiling):** average deal size × lead-to-close rate → break-even cost per qualified lead. Need deal size and lead-to-close rate.
- **History (achievable start):** trailing actual cost per *qualified* lead once the import is live and has 30-60 days plus conversion lag to mature. Doesn't exist yet — you're currently only measuring cost per raw form fill, which is the wrong denominator.

Also needed: monthly qualified-lead volume you'd realistically expect (sets whether cost-goal is viable on this narrower event, or whether volume-maximizing on the qualified event is the safer interim rung while volume builds), and who approves a target change.

## Draft policy (fill once inputs land)

```
BIDDING POLICY - <search platform> / lead quality correction
Objective        : cost efficiency, on the corrected event
Archetype        : cost-goal on "SDR-qualified lead" (offline import) — not return-goal yet
                    (no differentiated values flowing back), not manual (doesn't fix the signal)
Evidence         : event = SDR qualification stage in CRM, imported as offline conversion
                    depth check: passes once qualification reflects "facilities director, real opp"
                    value integrity: n/a until option 2
                    volume/period: [needed] | lag: SDR qualification, typically days not months
Target           : [needed: break-even cost per qualified lead = deal size x lead-to-close rate]
                    initial target set at/near trailing actual on the NEW event once it has a
                    mature history window — not at the old form-fill number, not aspirational
                    refresh date: [needed]
Evaluation       : window in conversion cycles = qualification lag + reporting delay
                    (days, not the 4-month sales cycle — don't wait for closed-won to judge this)
Change rules     : ~10-15% target steps, one evaluation window between moves, no concurrent
                    confounding changes, batch pending fixes into one relearn event
                    approver: [needed]
Rollback trigger : qualified-lead volume/period lands below the platform's reliable-evaluation
                    threshold for cost-goal even after the event switch → fall back to
                    volume-maximizing on the qualified event until volume builds
Switch triggers  : differentiated lead values become available and trustworthy → move to
                    return-goal (option 2)
```

## Settling the actual argument in the room

Tell both halves of the team the same thing: neither "trust the machine" nor "go back to manual" was ever the decision that mattered. The decision was whether the machine was being taught the right thing. It wasn't. Fix the Teacher job — route qualified-lead signal back to the platform and re-point the optimization there — and keep automated bidding, because a corrected signal is exactly the case where an algorithm plus proper monitoring (the Pilot layer) outperforms manual price-setting by hand. Add monitoring rules on top (delivery drops, cost spikes, re-entry into learning) so the "black box" half of the team has a legible way to catch it drifting, instead of relying on trust alone.

Don't revert to manual as a first move. It spends effort on the wrong lever and gives up gains you already earned, without touching the reason SDRs are seeing junk.