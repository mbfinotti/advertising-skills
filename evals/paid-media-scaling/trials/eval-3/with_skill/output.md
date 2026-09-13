# Media Scaling Ramp — Finchley Software paid budget, $60K → $180K/month

One process note before the plan: this skill normally interviews one question at a time and gets sign-off section-by-section before drafting anything. Since you asked for the complete deliverable in one pass, I've built it from what you gave me and flagged every gap as an **Open item** rather than quietly assuming an answer — per the skill's anti-fabrication rule, a missing input becomes a stated gap, never a confident-looking guess. Treat the gate failures below as real blockers, not formatting.

## The headline finding

The plan as described — "put most of the increase behind branded search and retargeting because those are the proven winners" — is the exact failure mode this skill exists to catch. Branded search and retargeting are, structurally, the two channel types where platform-attributed ROAS overstates true incremental value **the most**, and you've told me you have zero causal measurement (no lift test, ever) to check that. Two evidence anchors on this, both labeled per the discipline below:

- **research** — Blake, Nosko & Tadelis (2015, _Econometrica_), eBay's own experiment: naive attribution showed +1,400% to +4,100% ROI on non-brand paid search; the causal experiment measured **-63%**. Non-brand, not even brand — brand search's overstatement risk is generally considered worse, because a much larger share of "brand" clicks are people who were already navigating to you.
- **folklore/vendor data** — Haus geo-holdout benchmarks put a reported ~3x _cold prospecting_ ROAS nearer 1.8–2.2x incremental. That's the channel type least prone to inflation (net-new attention); branded/retargeting sit on top of existing intent and demand, so the gap between reported and incremental is typically larger, not smaller.

Your own numbers are consistent with this pattern, not an exception to it: 11x on branded search is plausible almost entirely because branded-search clickers were already going to convert (organic substitution); 7.8x on retargeting is plausible because retargeting fires on people already deep in your funnel. Your 2.1x cold prospecting number is the one number in this set that's actually measuring something close to net-new demand creation — and it's also the one you're proposing to _de-prioritize_.

This doesn't mean branded/retargeting spend is "wasted" — the skill is explicit that folklore/attribution skepticism licenses a test, never a waste percentage. It means: **you cannot tell, from what you have, whether tripling those two lines buys you anything close to 3x the revenue.** At 3x total spend, that's not a rounding error.

---

## Readiness gates

| #   | Gate                                   | Status                                 | Why                                                                                                                                                                                                                     |
| --- | -------------------------------------- | -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0   | Affordability (LTV → max CAC boundary) | **FAIL — open item**                   | No LTV, gross margin, or CFO/RevOps-approved max-CAC / min-ROAS given, and self-serve vs. sales-assist almost certainly have different LTVs. Nothing should scale past current spend until this exists per plan/motion. |
| 1   | Data maturity                          | **UNKNOWN — open item**                | No stated window for how long 11x/7.8x/2.1x have held, or whether it covers your full conversion lag (self-serve is fast; sales-assist is not).                                                                         |
| 2   | Marginal economics                     | **FAIL**                               | You have blended/attributed averages only, on the three channels most likely to diverge from marginal truth. No marginal-band read exists. This is the gate the current plan is actually trying to skip.                |
| 3   | Measurement health (5-area maturity)   | **UNKNOWN, likely low — open item**    | "Never run any lift testing" caps the attribution-process sub-score regardless of dashboard quality. Score this properly before scaling further.                                                                        |
| 4   | Creative supply                        | **UNKNOWN — open item**                | Not stated: proven, non-fatigued ad count per channel, or monthly test throughput. Cold prospecting is the most creative-hungry motion and the one you're about to lean on more.                                        |
| 5   | Business absorption                    | **UNKNOWN — open item**                | CFO approved the _spend_; separately confirm: (a) cash float against B2B pipeline lag, (b) sales/SDR capacity to work a higher lead volume without speed-to-lead degrading — critical for a sales-assist motion.        |
| 6   | Rollback pre-committed                 | Set by this plan (Steps section below) | Not yet in place; fixed here.                                                                                                                                                                                           |

Per the skill's own rule, a failed gate stops the ramp and names its fix — it doesn't get a smaller version of the same plan shipped anyway. Gates 0 and 2 fail hard enough that **no channel should get a 3x-style jump this week.** The fixes below are fast (days, not months) for a company your size, so this isn't a "wait a quarter" answer.

**Immediate fixes (before any dollar moves):**

- Pull LTV and gross margin by motion (self-serve vs. sales-assist) from existing billing/CRM data; get Finance to sign off on a max CAC or min ROAS per motion. This is a data pull, not a new build.
- Confirm CRM → ad-platform offline-conversion loop is live for the sales-assist funnel (if it isn't, that's the real reason branded/retargeting numbers look this clean — no downstream lead-quality signal to contradict them).
- Confirm SDR/sales capacity headroom at 3x lead volume, and cash float against pipeline lag.

---

## Evidence bar

**Attributed only** — by your own statement, no triangulation against CRM/blended revenue, no causal test of any kind, ever. Per Pass Threshold #6 in this skill, a ramp beyond ~2x current spend on purely attributed evidence _requires_ a causal-measurement step or an explicit, user-acknowledged risk line. You're proposing 3x. That step is not optional here — it's built into Phase 1 below.

Planned upgrade: causal tests on branded search and retargeting, launched in parallel with the ramp, not before it — see Steps.

---

## Approach — brainstormed and re-ranked

Default order (efficiency: vertical ladder > measure-first > horizontal; value: measure-first > horizontal > vertical ladder):

- **Measure-first — promoted to lead**, against the default order, for three stacked reasons the skill treats as individually sufficient to promote it: (1) target is 3x, past the 2x line that mandates a causal step anyway; (2) all current evidence is platform-attributed; (3) you have a hard date/budget event (CFO approval) that creates real pressure to ladder blindly — exactly the condition measure-first exists to interrupt.
- **Vertical ladder — run in parallel on cold prospecting only.** Prospecting is the one channel where attribution risk is lowest and real audience headroom likely exists (B2B TAM is finite but you haven't told me penetration is anywhere near saturated). It gets a normal ladder while branded/retargeting sit in test.
- **Horizontal expansion — held as a fallback, not deleted.** Once branded search's holdout confirms (or doesn't) real headroom, branded query volume is close to a fixed pool — you can't buy meaningfully more people typing your brand name. If the lift test shows branded is genuinely incremental but capped, the next dollars for that motion go to a new channel/segment, not more branded budget. I'm not deleting this rung; I'm parking it pending the branded-search readout, and naming that condition explicitly so it doesn't quietly disappear.

**What I did not do:** delete the vertical ladder on branded/retargeting outright. I froze it pending test results, which is different — those channels may well earn a real increase, just not sized off an 11x/7.8x number that gate 2 says isn't trustworthy yet.

---

## Steps

**Step-size basis:** you gave no change-log history (rung 1 unavailable), so this uses the concrete default (15–20% per step, **folklore**, ship only with the recalibration instruction) for prospecting, and validate-then-push (no percentage) for branded/retargeting, since that's exactly the rung causal testing unlocks.

### Phase 0 — this week (no budget change yet)

- Close gates 0, 3, 5 open items above (LTV/max-CAC sign-off, CRM loop check, SDR capacity check).
- Design causal tests:
  - **Branded search:** geo-based brand blackout (pause branded search in a matched set of geos/DMAs, compare to control) — standard incrementality method for exactly this question.
  - **Retargeting:** conversion-lift / ghost-ads holdout via the platform's native lift tool (Meta Conversion Lift, Google/DV360 equivalent) — holds out a control group from retargeting eligibility.
- Freeze branded search and retargeting budgets at current levels during design (no cut, no increase).

### Phase 1 — weeks 1–6 (parallel tracks)

| Track                 | Move                                                                                                                                 | Hold                                                                                                                                          | Monitor                                                                                                           | Rollback trigger → action                                                                           |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Cold prospecting      | +18% (folklore default) at W1, +18% at W3, +18% at W5                                                                                | 2 wks/step                                                                                                                                    | Marginal CAC vs. approved boundary once set, frequency, lead-quality score (not raw CPL — B2B), SDR speed-to-lead | Cost/qualified lead >1.5x target for a full hold → cut 20–30%, stabilize 2 wks, resume at +10%/step |
| Branded search        | Held flat; geo holdout runs                                                                                                          | Full learning window + your actual click-to-SQL lag (open item — get this number, likely days for self-serve intent, longer for sales-assist) | Holdout readout only                                                                                              | N/A during test — any spend change here invalidates the read                                        |
| Retargeting           | Held flat; conversion-lift holdout runs                                                                                              | Same as above                                                                                                                                 | Holdout readout only                                                                                              | Same                                                                                                |
| Test/creative reserve | Carve ~10–15% of the $120K increase into new prospecting creative production, sized against gate 4 once creative-supply counts exist | Ongoing                                                                                                                                       | Proven-ad count vs. budget (folklore ratio: proven ads ≈ monthly budget ÷ $5,000 — recalibrate to this account)   | N/A                                                                                                 |

Remainder of the $120K increase is **explicitly not deployed yet** — it sits in reserve pending the Phase 1 readout. This is the deliberate answer to "CFO approved $180K, so we should be spending $180K by next month": spending the full increase before you know what's incremental is the thing this whole plan exists to prevent.

### Phase 2 — post-readout (targeted week 6–8, contingent on actual conversion lag — open item)

Reallocate the held reserve based on **incremental** lift, not platform ROAS:

- If branded search shows real incrementality: fund it up to the point its own demand-capture ceiling binds (branded query volume is close to fixed — expect this to bind fast, likely well under a 3x increase on this line alone), then route remaining dollars to a new channel/segment, not more branded budget.
- If retargeting shows weak/no incrementality: cap it near current spend, redirect freed budget to prospecting and/or a horizontal test (new segment, new channel, new ICP), consistent with the research that growth comes from penetration and light-buyer reach, not deeper retargeting frequency.
- Continue the prospecting ladder if its marginal numbers (now measurable against the approved CAC boundary) still clear the bar; if 2.1x sits below breakeven once real margin data lands, that's gate 0 doing its job — stop that line's ladder and say so, don't quietly keep raising it because it's "the strategy."

---

## Ceilings

- **Non-media, check first:** SDR/sales capacity is the most likely near-term binding constraint for a sales-assist motion absorbing more prospecting-driven leads — unresolved open item, must be checked before Phase 1 prospecting steps 2–3.
- **Saturation signals:** B2B TAM/penetration numbers not given — open item. Get a 30-day penetration read before committing past Phase 1.
- **Demand-capture ceiling (branded search specifically):** this is very likely the real ceiling on that line regardless of test outcome — "no amount of optimization expands a market of people already searching your brand name." Expect it to bind early even if the holdout comes back favorable.
- **Marginal stop signal:** not computable until gate 0's CAC boundary exists.

## Exit condition

Ramp ends at whichever binds first: target reached ($180K), marginal contribution margin ≤ $0 on any line once measurable, sales capacity ceiling hit, or branded search's demand-capture ceiling reached. Report which one actually bound — that's the KPI on the ramp itself, not on the campaigns.

## Open items (explicit — not guesses)

1. LTV, gross margin, and Finance-approved max CAC / min ROAS, by motion (self-serve vs. sales-assist).
2. How long the 11x / 7.8x / 2.1x numbers have held, and whether that window covers your actual conversion lag.
3. Click-to-SQL and SQL-to-closed-won lag, by motion — sets every hold period in this plan.
4. CRM ↔ ad-platform offline conversion loop status.
5. Proven/non-fatigued ad counts and monthly creative throughput, by channel.
6. 30-day audience penetration / reach trend for prospecting; branded search impression share.
7. Cash float vs. pipeline lag at $180K/month; SDR/sales capacity headroom.
8. Who approves budget moves at what size, and the size of the still-reserved $120K remainder.

Nothing above is a blocker to _starting_ Phase 0 this week — most of it is a data pull, not new infrastructure. It is a blocker to deploying the full increase into branded search and retargeting on the numbers you have today.
