# Kestrel Data — Paid-Media Spend Guardrail Policy

**Status: provisional.** Your margin is enough to derive a real break-even ceiling, but several inputs behind the dollar figures aren't in front of me yet (listed at the end). Ship the architecture and break-even math now; slot in the missing numbers before finance signs it.

## Why "3x target CPA for 3 days, auto-kill" isn't a rule yet

Four fixable problems, in order of how much money each one costs you:

1. **"3x CPA" is untraceable folklore, not your economics.** No published source derives it — it's not tied to your 62% margin. At 62% gross margin your break-even ROAS is 1.61x (1 ÷ 0.62); your break-even CAC is $14,880 (62% of $24K ACV). "3x target" could sit well inside that break-even line (safe but slow to react) or well past it (the rule lets you bleed for three full days before it fires). You can't tell which without one more number (below), so as written the rule is unverified, not wrong — but it has to be checked against break-even, not asserted.
2. **One trigger condition, no evidence gate.** A pure "N days above threshold" streak with no minimum spend or SQL volume kills on noise as readily as on real degradation — this is the exact thrash pattern the skill literature flags. LinkedIn also runs delivery optimization; killing and later re-enabling a campaign resets its learning, which is its own cost, not just an opportunity cost.
3. **No restart condition.** A halt with nothing defining how the channel turns back on isn't a kill switch, it's a permanent shutdown with extra steps.
4. **No named owner, applies flat across channels.** "Gets shut off" by whom, approved by whom, logged where? And a flat CPA ceiling structurally punishes prospecting channels (LinkedIn cold outreach) against retargeting/branded search, which always look cheaper because they harvest demand that already existed.

The policy below keeps your instinct — a 3x multiplier, a 3-day window, automatic — but derives it from your numbers and gives it the other three pieces a kill rule needs.

```
SPEND GUARDRAIL POLICY — Kestrel Data, effective 2026-09-12, review 2026-12-12

Inputs
  ACV                             $24,000                                   measured
  Gross margin                    62%                                       measured
  Sales cycle (median)            ~75 days                                  measured
  Contribution per closed-won     $14,880 (= $24,000 x 62%)                 derived
  SQL-to-closed-won rate                                                    MISSING
  Payback target                                                            MISSING
  Cash runway / monthly burn                                                MISSING
  Current baseline cost per SQL (pre-spike)                                 MISSING — only
                                                                             known to have doubled

Derivation
  Break-even ROAS       = 1 / 0.62 = 1.61x
  Break-even CAC         = $14,880 per closed-won deal
  Break-even cost/SQL    = $14,880 x SQL-to-closed-won rate — formula only;
                            needs the missing rate to become a dollar figure
  Target cost/SQL         = trailing 30-day median cost per SQL, recomputed weekly
                            (measured from your own platform + CRM data, not guessed)

Layers
  Break-even floor   cost/SQL = $14,880 x SQL-close-rate    -> stop, always
  Target floor        trailing 30-day median cost/SQL         -> investigate, weekly review
  Hard floor           MIN( 3 x trailing 30-day median cost/SQL , break-even cost/SQL )
                        -> automatic halt of the breaching channel
                        The MIN() clamp is the fix to your original rule: it keeps your
                        3x multiplier as the normal trigger, but never lets 3x authorize
                        spend past actual break-even once the SQL-close rate is supplied.

Guardrail set
  1. Cost per SQL, per channel, daily read against 30-day trailing baseline
     source: ad platform spend ÷ CRM-confirmed SQL count
     counter-metric: SQL-to-closed-won rate — catches a channel that gets "cheaper"
     by delivering SQLs that never close
  2. Blended CAC on new-logo pipeline, monthly
     counter-metric: new-logo share of pipeline
  3. Paid spend as % of cash cap, monthly — cap value pending runway input

Kill rules
  Streak     cost/SQL above hard floor for 3 consecutive days (your original window —
             appropriate here since SQL qualification is fast, unlike the 75-day cycle)
  Rate       25% of the channel's weekly budget spent while above hard floor within
             any 72h window — second, independent trigger (proposed default, confirm
             with RevOps)
  Evidence   no halt before the channel has both run >=3 days live in-flight AND
             generated >=15 SQLs, whichever comes first (proposed default, confirm
             typical LinkedIn SQL volume with RevOps) — a channel below this bar is
             held flat, never killed
  Fail-closed  missing / stale / broken SQL feed data -> hold spend flat, never
             treat as breach or as clean
  Restart     restart at 50% of prior daily budget once root cause is named and fixed
             (creative, targeting, bid strategy, or tracking); cap any pause near 7 days
             before requiring a "cold-restart" review — algorithmically-optimized
             platforms tend to lose learned delivery after longer pauses, so a slow
             evidence gate plus no restart cap can cost more than the overspend it
             prevented

Governance
  Owner        CFO owns break-even inputs and the break-even floor
               CMO owns the target floor and the hard floor
  Execution    Media buyer/agency executes; cannot raise its own ceiling
  Escalation   target breach -> Growth/Demand Gen lead, weekly review
               hard breach   -> automatic halt + notify CMO within 1 hour
               break-even breach -> CFO, immediate halt, no discretion
  Override     CMO may authorize up to 5 business days above the hard floor (never
               above break-even) with written reason logged in this ops doc;
               break-even breaches require CFO co-sign; no standing exceptions
  Re-baseline  quarterly, plus on: pricing change, margin change >3pts, sales-cycle
               shift >2 weeks, SQL definition change, LinkedIn tracking/attribution
               change

Exemptions
  Testing/exploration budget — unknown whether one exists; open question below.

Assumptions
  This assumes "CPA" means cost per SQL, matching the LinkedIn incident. If your CMO
  meant cost per closed-won or cost per opportunity, re-anchor the hard-floor formula
  to that variant — the break-even multiple is different for each.
  Assumes LinkedIn's SQL-to-close rate is close to your blended rate. If LinkedIn SQLs
  close materially worse (or better) than other channels, this floor needs to be set
  per channel, not flat.
```

## Inputs to supply before the dollar figures are final

- SQL-to-closed-won rate (blended, and ideally per channel) — this is the one number that turns every formula above into an actual dollar ceiling.
- Payback target and its source (board-set? finance-set?).
- Cash runway and monthly burn, to set the cash cap line.
- Pre-spike baseline cost per SQL on LinkedIn (absolute $, not just "doubled").
- Conversion feed reliability — confirm the CRM→SQL pipeline is trustworthy before this becomes a live control; a kill switch on bad data fires on noise, not economics.
- Whether a ring-fenced testing budget exists today, and at what share of spend.
- Named individuals for CFO/CMO/Growth-lead roles above, for the ops doc.

Once those land, the hard-floor and target-floor lines resolve to real dollar figures instead of formulas — nothing else in the structure changes.