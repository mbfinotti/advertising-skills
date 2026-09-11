# Brontide Labs — Media Scaling Ramp: $25K → $75K/month

**Headline verdict, up front:** the media-buying mechanics of a 3x ramp in 3 months are doable. Two things are not yet true and will bind before the auction does: (1) creative supply covers roughly $20K/month today, not $75K, and the freelancer's current output can't close that gap inside 3 months; (2) hitting exactly 3 months forces holds shorter than this playbook's B2B default, which trades away your ability to see lead-quality decay before it's already baked into a $75K/month run rate. Both are named as open risks below, not papered over.

This is a proposed plan, not an executed one — nothing here changes a platform setting. Several inputs below are marked ⚠️ UNKNOWN because they weren't in your brief; the plan runs on placeholders for those and flags exactly what to bring back before Step 1 fires.

---

## Readiness Gates

| # | Gate | Status | Basis |
|---|------|--------|-------|
| 0 | Affordability (LTV → max CAC) | ⚠️ UNKNOWN | No contribution margin or owner-approved max-CAC/min-ROAS boundary given. Everything downstream needs this number — get it from Finance before Step 1. |
| 1 | Data maturity | ✅ PASS | Live since March (~6 months) — comfortably past one learning cycle + lag. But zero budget-change history (see quirk below) means this maturity is about steady-state delivery, not about how the account behaves *when budget moves*. |
| 2 | Marginal economics | ⚠️ UNCONFIRMED | "Marginal numbers look decent" is unlabeled — no evidence tier, no Δrevenue/Δspend figure. **Folklore-grade claim until you attach a number and a label (attributed/triangulated/causal).** This gate can't formally pass on the current wording. |
| 3 | Measurement health | ✅ PASS (12/15) | Clears the ~6/15 floor with room. The 3-point gap matters for B2B specifically: confirm whether it includes a live CRM offline-conversion loop (stage changes flowing back to LinkedIn/Meta). If not, that's the fix before scaling on any lead metric. |
| 4 | Creative supply | 🔴 FAIL at target | Folklore ratio: proven ads ≈ monthly budget ÷ $5,000. 4 proven ads support ≈$20K/month — almost exactly current spend, which is itself informative. $75K needs ≈15 proven ads. At 2 new tests/month, even 100% hit rate only adds 6 over 3 months (→10, still 5 short). **This is the binding constraint on the whole ramp, not the platforms.** |
| 5 | Business absorption | ⚠️ AT RISK | Cash: weekly card billing vs. net-60 customer payment, stacked on top of a B2B click-to-close lag (60–281 days, Dreamdata benchmark — research). Tripling weekly card outflow before revenue catches up is a real working-capital ask. CFO signing off on the *media budget number* is not the same as CFO modeling *the cash-conversion gap* — confirm which one happened. Sales/SDR capacity to work 3x the webinar-lead volume: ⚠️ UNKNOWN, ask before Step 1. Card credit limit headroom for 3x weekly charges: ⚠️ UNKNOWN, a decline mid-ramp will look like an emergency but is really an operations miss. |
| 6 | Rollback pre-committed | Set below | — |

**Per the skill this ramp is enforcing:** a failed gate stops the ramp and gets named with its fix — it doesn't get a smaller ramp as a consolation. Gate 4 fails outright for the full $75K scope. What follows is the plan for what the gates *do* support, plus the explicit fix required to unlock the rest.

---

## Evidence Bar

**Attributed**, most likely, based on "marginal numbers look decent" carrying no methodology. Platform-attributed ROAS is exactly least trustworthy on the channels you're running (LinkedIn/Meta paid social skews toward retargeting-like overstatement).

$25K → $75K is a 3x move. Pass-threshold rule for this skill: **any ramp beyond ~2x current spend on purely attributed evidence needs either a causal-measurement step or an explicit, acknowledged risk line.** There's no time for a full geo-holdout in a 3-month B2B sales-cycle world, so this plan inserts a lightweight causal check at the 2x line (Step 4, ~$52K) rather than skipping it — see Steps table. **Explicit risk line:** if that check doesn't run or doesn't read clean, treat everything past $52K as scaling on attribution alone, with the eBay result (-63% causal vs. +1,400–4,100% naive attribution — Blake, Nosko & Tadelis 2015, research) as the standing warning of how wrong that can be.

---

## Approach

- **Vertical ladder — recommended, default rung.** Hard external date (board/CFO, fixed) promotes this per the interview logic. One line to manage, readable fast, and — critically — it doesn't consume more creative than you already have running.
- **Measure-first — folded in, not leading.** The 3x target would normally promote this to first, but there's no time to front-load weeks of holdout before starting against a 3-month clock. Compromise: one lightweight causal check inserted mid-ramp (Step 4) instead of leading with it. Named explicitly so it isn't silently skipped.
- **Horizontal expansion — deleted, not just deprioritized.** New segments/geos/campaigns each need their own learning phase and their own creative, and creative is already your scarcest resource (Gate 4). Adding horizontal lines right now would starve the four ads that currently work. Reconsider only after creative supply is fixed.

---

## Step Size Derivation

- **Rung 1 (account history) is unavailable.** The quirk you flagged — same daily budgets since launch in March, zero budget changes in 6 months — means there is no data on how this account's algorithm reacts to an edit. This isn't neutral: Step 1 will be this account's *first ever* significant edit, with no prior reset behavior to calibrate against. Treat it with more caution than the steps that follow, not less.
- **Rung 3 (validate-then-push) is unavailable** — no causal measurement trusted yet (see Evidence Bar).
- **Using Rung 2: the 15–20% concrete default (folklore — Social Media Examiner, Sept 2021, relaying unverified platform advice).** Shipped only with the standing instruction to recalibrate from real reset behavior after Step 1–2 land — this is an opening guess, not a rule.
- **Hold period:** the skill's own B2B default is "a month or more, judged on leading indicators." Fitting 6 steps into 3 months forces 2-week holds instead — **this is a deliberate compression below the recommended B2B default, done to meet the fixed deadline, and it's the second named risk of this plan.** Two weeks is enough to read cost-per-SQL and delivery stability; it is *not* enough to see the lead-quality decay that's this channel mix's named dominant failure mode ("falling CPL reads as success while pipeline flatlines"). Score lead quality every hold, not just cost-per-SQL.

---

## Ramp Plan

```
MEDIA SCALING RAMP  -  Brontide Labs webinar lead-gen (LinkedIn + Meta), $25K → $75K/month over ~12 weeks

Gates        : affordability UNKNOWN (need max-CAC/min-ROAS from Finance) | data maturity PASS
               (6mo live, but zero change-history) | marginal economics UNCONFIRMED (need
               labeled Δrevenue/Δspend) | measurement 12/15 PASS (confirm CRM offline loop) |
               creative supply FAIL at target (4 proven vs ~15 needed; fix = expand freelancer
               capacity or add a second creative source, now) | absorption AT RISK (confirm
               CFO modeled cash-conversion gap, not just budget total; confirm SDR capacity
               for 3x lead volume; confirm card credit limit) | rollback below

Evidence bar : attributed (unlabeled marginal claim). 3x target exceeds the 2x/attributed-only
               threshold -> lightweight causal check inserted at Step 4, not led with, due to
               the fixed deadline. If that check doesn't run, spend past $52K is explicitly
               scaling on attribution alone.

Approach     : vertical ladder (default, hard date) + one folded-in causal check at the 2x
               line. Horizontal expansion DELETED - would fragment the creative supply that's
               already the binding constraint.

Steps        : Wk2  $30,000 (+20%) | hold 2 wks | cost/SQL & lead-quality score at target,
                    delivery exits learning, no CPM/frequency spike. FIRST-EVER edit on this
                    account - watch daily, not just at hold-end.
              Wk4  $36,000 (+20%) | hold 2 wks | same set + reach/frequency trend
              Wk6  $43,000 (+19%) | hold 2 wks | same set + proven-ad count check (need 9+)
              Wk8  $52,000 (+21%) | hold 2 wks | LAUNCH causal check here (audience-split
                    holdout or CRM-vs-platform reconciliation, whichever LinkedIn/Meta's
                    B2B setup supports) - this is the 2x line
              Wk10 $62,000 (+19%) | hold 2 wks | causal readout gates this step; proven-ad
                    count check (need 12+)
              Wk12 $75,000 (+21%) | hold 2 wks | confirm at target; proven-ad count check
                    (need 15 - almost certainly short, see Ceilings)

Rollback     : cost per SQL > 1.5x target across a full hold -> cut 20-30%, stabilize 2 wks,
               resume +10%/wk. ROAS/aMER drop persisting 5-7 days -> revert to prior budget.
               Lead-quality score falling while CPL looks flat or improving -> freeze
               immediately, this is the named B2B failure mode (proxy broke, not the ads).
               Before acting on any trigger: check sample size, conversion lag, tracking
               outages, seasonality, running experiments first - smallest reversible action.
               Instant cut reserved for runaway spend, broken destination, or tracking
               corruption only.

Ceilings     : creative supply binds FIRST - the math above says you run out of proven ads
               well before Wk12 (10 max at best-case freelancer output vs 15 needed) | cash/
               absorption binds SECOND if CFO sign-off was budget-only, not cash-conversion-
               aware | sales/SDR capacity UNKNOWN, could bind ahead of both if unaddressed |
               audience penetration and TAM saturation UNKNOWN - no data given

Exit         : $75K reached with all gates still passing, OR marginal CM crosses $0 on any
               step, OR creative-supply shortfall forces a hold below target (likely outcome
               on current freelancer capacity - see Open Items), OR lead-quality decay
               triggers a freeze

Open items   : (1) Marginal CAC/ROAS number + evidence label + owner-approved boundary -
               blocks Gate 0/2 sign-off. (2) Confirm CRM offline-loop status inside the
               12/15 score. (3) Creative production fix - second freelancer, in-house rapid
               variants of the 4 winners (new hooks/formats from proven concepts, faster
               than net-new concepts), or an explicit ask to the board to soften the
               3-month date given the creative bottleneck. (4) CFO confirmation that
               the $75K sign-off accounts for the net-60 + B2B sales-cycle cash gap, not
               just the topline spend number. (5) SDR/sales-follow-up capacity check
               against 3x webinar-lead volume. (6) Ad-account card credit limit raised
               ahead of Wk2. (7) 30-day penetration/reach pull on LinkedIn + Meta audiences
               - currently unknown, needed to confirm vertical-ladder headroom holds
               through Wk12. (8) ÷$5,000-per-proven-ad ratio is folklore - recalibrate
               against this account's actual fatigue rate once Steps 1-2 land.
```

---

## What this plan is asking you to do before Wk2

1. Get the four numbers in Open Items 1, 2, 4, 5 from Finance/Sales — none of them are guessable, and the skill this plan runs on treats a confident-looking guess here as worse than an open item.
2. Decide now, not at Wk8, how you'll cover the creative-supply gap — it's the most likely reason this ramp stalls before the auction does.
3. Treat Wk2 as the account's first-ever reset event and watch it daily — six months of flat budgets means you're flying without this account's own history, the one input that's supposed to be free.