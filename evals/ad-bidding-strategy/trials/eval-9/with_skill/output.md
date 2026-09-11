# Nockboard - Meta Bidding Policy: Cost-Per-Result (Webinar Signups)

## What's actually broken, before any rule-writing

The volatility isn't bad luck, and it isn't proof the target is wrong. Line up the timeline against the lag you described:

- Full conversion cycle = ~3 weeks click-to-qualified-signup + a few days reporting delay ≈ **25 days**.
- You've made three target changes plus a creative refresh plus an audience narrowing inside **14 days**.

None of those changes has had time to fully mature in reporting yet. Every CPA number you reacted to over the last two weeks was built from an incomplete, still-filling-in sample - a mix of tail conversions from the previous target still landing, and a partial read on the current one. You were adjusting the dial based on numbers that hadn't finished arriving. That's the textbook "learning churn" pattern: an edit reads as instability, the instability triggers another edit, and the loop feeds itself.

Stacking the creative refresh and audience narrowing into the same window compounds it - you can no longer tell whether any given swing came from the target, the creative, or the audience, because they all changed together.

**One more thing to check before trusting any of this data**: confirm Meta's conversion/attribution window on this ad account is set to at least ~4 weeks (covering the 3-week lag plus reporting delay). If it's still on a shorter default click-through window, results are being undercounted early and correcting upward later - which alone would produce the exact "it keeps swinging" symptom you're describing, independent of anything the bidder is doing.

## Working assumptions (confirm these before treating the policy as final)

I'm drafting this from what you gave me rather than a full back-and-forth interview, since you asked for the complete deliverable directly. Two things are load-bearing and unconfirmed:

1. **"Result" = the qualified signup event itself**, not an upstream proxy (raw form-fill, webinar registration). If Meta is actually optimizing on registration and "qualified" is a downstream CRM judgment layered on top, the cost-goal target is pointed at the wrong event - the canonical B2B failure this skill flags is "cost per lead improves while pipeline dies." Resolve this first; everything below assumes it's already the right event.
2. **Deal economics aren't yet in hand** - average contract value, qualified-signup-to-close rate, contribution margin. Without them I can only set the target from history (what you've achieved), not confirm it's affordable (what you can afford). Get me those three numbers and I'll compute the break-even ceiling and a proper margin buffer.

## Archetype: staying on cost-goal

Cost-goal (Meta's "Cost Per Result Goal") is the right archetype here and the default rung once the tracked event is valid - it's the best return for the setup effort at your likely volume, versus the alternatives:

- **Volume-maximizing (no target)**: fallback if qualified-signup volume turns out too thin to give a cost target a stable read (see sample-size note below). Buys stability, costs all cost control.
- **Return-goal**: not reachable yet - it needs differentiated deal values flowing back and clears a documented volume minimum well above where a webinar-platform B2B account with a 3-week-lag event typically sits. Revisit once values flow (see Switch triggers).

Recommendation: hold cost-goal. Reconsider volume-maximizing only if the sample-size check below shows you can't clear enough qualified signups per week to read a cost target reliably.

## The Bidding Policy

```
BIDDING POLICY  -  Meta / B2B webinar qualified-signup cost efficiency

Objective        : cost efficiency (hold an average cost per qualified signup)

Archetype        : cost-goal (Meta: Cost Per Result Goal), average-based control.
                   Why: matches current setup, event is (assumed) valid, no
                   values flowing back yet to justify return-goal. Runner-up
                   (volume-maximizing) rejected unless the sample-size check
                   below shows the event is too thin for a cost target to read.

Evidence         : event = qualified signup [CONFIRM: not a raw registration
                   proxy]. Depth check: UNRESOLVED - confirm before trusting
                   this policy's target.
                   Value integrity: not applicable at cost-goal.
                   Volume: [not yet supplied - see Action items].
                   Lag: ~21 days click-to-signup + few days reporting ≈ 25-day
                   conversion cycle.

Target           : $50 (current, held - see rationale).
                   Economics: break-even CPA = avg. deal value x qualified-
                   signup-to-close rate. NOT YET COMPUTED - need those two
                   inputs plus contribution margin. Action item, not guesswork.
                   History: no mature trailing actual exists - three targets
                   in two weeks means none of $60/$48/$55/$50 has completed
                   even one conversion cycle. $50 is a RESET POINT, not a
                   proven baseline. Treat it as provisional until it survives
                   one full evaluation window untouched.
                   Refresh: re-derive economics once deal data is supplied;
                   re-baseline history after the first held evaluation window.

Evaluation       : 1-2 conversion cycles = 25-50 days (documented: vendor
                   guidance after a target change). Use the long end (50
                   days, ~7 weeks) given this account is also recovering
                   from three stacked changes, not just one.

Change rules     : - No target change before 2026-10-06 at the earliest
                     (7 weeks from today, 2026-09-12), UNLESS the rollback
                     trigger below fires first.
                   - One variable at a time from here on: target, creative,
                     and audience never move in the same window again.
                   - Step size +-10-15% once resumed (practitioner-convergent,
                     not documented) - never the jump sizes used in the last
                     two weeks ($60->$48 is -20%, $48->$55 is +15%, $55->$50
                     is -9%: the first two exceed the practitioner ceiling).
                   - Batch any pending tracking or creative fixes into the
                     next single change instead of drip-feeding edits.
                   - Approver: name one person who signs off on any target
                     move before it ships - unnamed here, fill in.

Rollback trigger : spend falls below ~60% of budget for a full evaluation
                   window while impression share lost to rank is rising ->
                   raise target back toward the last level that delivered
                   (working backward through $55, then $60) rather than
                   guessing a new number.

Switch triggers  : - Qualified-signup values become real and differentiated
                     (deal size, not one flat value) and clear Meta's
                     documented return-goal volume minimum (re-verify live -
                     these figures drift) -> propose return-goal.
                   - Signup-to-close rate collapses while reported CPA holds
                     steady -> event is shallower than assumed; stop tuning
                     the bid, fix measurement first.
                   - Attribution window check above comes back too short ->
                     fix that before trusting any further CPA reading.
```

## The automated $90 rule - and why the version you asked for gets refused

A blind "pause any ad set above $90 CPA" rule is exactly the anti-pattern this policy exists to prevent: a fixed-cost trigger with no check on sample size, maturity, or confounding changes will pause ad sets on noise, not on a real problem - especially at a 25-day lag, where an ad set's first few weeks of reported CPA are built on a handful of completed signups at most. One expensive early result can blow the average past $90 before the ad set has had a fair chance.

Here's a version that keeps your intent (contain runaway cost) without pausing winners on incomplete data:

**Gate every check on all of the following before it's allowed to fire:**

| Condition | Rule |
|---|---|
| Ad set age | Live at least 1 full conversion cycle (25 days) before it's eligible for this rule at all |
| Sample size | At least 10-15 completed qualified signups in the lookback window (below that, one result swings the average too far to mean anything - derive a firmer number once you know weekly signup volume) |
| Window | Rolling 25-50 day average, never a single day's or single week's figure |
| Recency | No target, creative, or audience change inside the current evaluation window for that ad set (a fresh change hasn't stabilized yet) |
| Tracking health | No known tracking gap or attribution-window issue active |

**On breach, default to flag-for-review, not silent pause.** Route it to whoever owns the account (the "Doctor" job: someone decides whether it's a real problem or noise) within 24-48 hours. If the team genuinely wants a hard automated pause with no human in the loop, restrict it to a containment ceiling, not a working-target multiple - and $90 needs one more check: once you have break-even CPA from the economics derivation above, confirm $90 sits comfortably above it. If break-even turns out below $90, a $90 ceiling lets the account bleed money before it fires and should drop to break-even. If break-even is comfortably above $90, $90 remains a reasonable containment number.

## Action items, in order

1. Confirm the "result" event is the qualified signup, not an upstream proxy.
2. Check Meta's conversion/attribution window is set to cover the ~25-day lag.
3. Supply average deal value, signup-to-close rate, and contribution margin so break-even CPA and a real margin buffer can be computed.
4. Name the approver for future target changes.
5. Hold the target at $50, stop touching creative and audience, and don't revisit any of it before 2026-10-06 unless the rollback trigger fires.
6. Once (3) lands, re-derive the target properly and set the $90 guardrail's containment logic against the real break-even number instead of a placeholder.