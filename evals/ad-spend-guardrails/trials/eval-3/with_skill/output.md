# Ad Spend Guardrail — Torvale Supplements, scale decision to $150K/month

## The short answer

Don't approve the $150K jump on the agency's number. Their arithmetic is correct but it answers the wrong question, and it's *the exact same conflation* that produced a well-documented cautionary case in paid-media (Dave Rekuc, Common Thread Collective, 2022) at almost identical numbers to yours: 70% margin, ~$110K spend, blended MER 2.0 — where "you might set your budget as high as $110k per month. And yet, spend after $60k only loses money." Blended MER 2.0 tells you the *average* dollar across your current $110K is profitable. It tells you **nothing** about whether the *next* dollar — the one between $110K and $150K — is profitable. Those are different numbers, and the guardrail on a scaling decision has to be set on the second one.

Below is the guardrail, derived from your own numbers, not borrowed from the agency's framing.

## Derivation (shown so finance can audit it)

```
Contribution margin rate        : 70%                              measured
Break-even MER                  : 1 / 0.70 = 1.43x                 derived
Current blended MER              : 2.0x at $110K/month spend        measured
Implied current monthly revenue : $220K                             derived
Agency's proposed floor          : 1.4x, i.e. break-even             — this is a
                                    STOP line, not a scaling ceiling
```

The agency's "1.4x" is your break-even floor. Break-even is the line below which spend is definitionally destroying money — it is not evidence that spend up to that line is a *good* idea. Between break-even and wherever your marginal efficiency actually sits, there is a wide band where spend is "not yet losing money" but is also actively eroding your average — the Haus data on Meta shows this pattern directly: a $337 blended CPIA account had its last 25% of spend running above $1,000, more than 2x its own average. A "beat break-even" floor would have waved all of that through.

## The three layers, separated

| Layer | Value | Basis | Consequence |
|---|---|---|---|
| **Break-even floor** | Marginal MER 1.43x | 1 ÷ 70% margin | Stop, always — no discretion |
| **Target floor** | Marginal MER ≥ 2.0x (provisional) | See note below | Investigate, don't halt |
| **Hard floor / kill switch** | Marginal MER < 1.6x for 2 consecutive days on the incremental tranche | Buffer above break-even, sized for daily noise | Auto-revert the tranche, escalate |

**Target floor is provisional and I'm flagging it as such rather than dressing it up as derived.** A real target floor comes from your payback tolerance and cash runway — I don't have either. Absent that, the defensible provisional default is: *don't let the new spend drag the average down* — i.e. require the incremental dollars to perform at least as well as your current blended average (2.0x), not merely better than break-even. Replace this the moment you have a payback target and a cash cap; until then, treat the policy as provisional, not final.

## Missing inputs (name them, don't guess them)

| Input | Status |
|---|---|
| Contribution margin (70%) | Measured, but confidence unstated — is this finance-reviewed, and is it first-order margin or does it net out subscription/repeat economics? |
| Payback target | Missing |
| Cash runway / burn | Missing — this sets an absolute dollar cap on top of the efficiency floors, independent of MER |
| Whether MER is platform-reported or business-validated | Missing — critical. A platform-reported MER measures *claimed* revenue, not *caused* revenue, and rewards shifting spend into retargeting/branded search. If Torvale doesn't have an incrementality read (geo holdout, MMM, or at minimum a UTM-validated revenue feed), the guardrail below is measuring the wrong thing. |
| Who owns this ceiling at Torvale | Missing — see governance note below, this one matters |

## The guardrail for this specific decision

Don't approve $150K in one move. Approve a gated ramp, and put the gate on marginal efficiency, not blended.

**Guardrail set (2 metrics, each with a counter-metric):**

1. **Marginal MER on the incremental spend tranche** (the $110K→$130K→$150K steps), measured separately from the existing base.
   - Counter-metric: **new-customer share of the incremental spend.** This is what catches the agency hitting a MER number by pushing the new budget into retargeting/branded search rather than genuine prospecting — a MER met that way isn't the growth you're paying for.
2. **Blended account MER**, monthly — this is the reporting number, not the scaling gate.
   - Counter-metric: **contribution margin after ads.** Catches margin quietly funded by discounting rather than efficiency.

**Kill rule for the ramp:**
- Streak: marginal MER on the current tranche below 1.6x for 2 consecutive days → halt that tranche, revert spend to the prior confirmed level.
- Evidence gate: no read before the tranche has run at least 5-7 days (B2C window) and cleared a minimum spend of ~$3-5K on that tranche specifically — reading it sooner reads noise, not signal. Adjust upward if Torvale has any subscription/repeat-purchase tail, since first-touch attribution windows on a repeat-purchase supplements brand can understate true marginal value.
- Restart: after a halt, resume at half the failed increment, with a named reason logged (creative, audience, or tracking), not a blind retry.
- Fail closed: if the revenue feed is stale, broken, or unvalidated for the tranche period, hold spend flat — never scale on missing data.

**Governance — the part most likely to get skipped:**
This ceiling has to be owned by someone at Torvale, not by the agency. The agency is the party whose revenue grows if spend grows; recommending "you have headroom" and then being the one who judges whether the headroom held is a conflict, not a control. Concretely: name a person at Torvale (founder/finance) who reads the marginal-MER number weekly during the ramp and who alone can authorize the next tranche — the agency executes against that ceiling, it doesn't set it.

## Bottom line

Approve a test, not a target. Move to $130K, hold it 1-2 weeks, and only authorize the next $20K to $150K if the marginal MER on that new tranche clears ~2.0x with genuine new-customer volume behind it — not merely above the 1.4x break-even the agency quoted. If the marginal read comes in between 1.43x and 1.6x, you're in the Rekuc zone: technically not losing money, definitely not worth spending.

This is provisional pending your payback target, cash cap, and confirmation that MER isn't purely platform-reported — worth a short follow-up to lock those down before this becomes your standing scaling policy rather than a one-decision guardrail.