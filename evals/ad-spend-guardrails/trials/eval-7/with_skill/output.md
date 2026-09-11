# Lanternfish HQ — Spend Guardrail Policy (CAC ceiling)

## Direct answer

Set the **target CAC ceiling at $196** (5-month payback, your investor's ask), a **hard floor at ~$310** (8-month payback) where spend auto-halts, and treat **~$470** (12-month payback) as the outer stage-guidance bound — not a literal break-even, see caveat below. Your current CAC (~$44) sits far under all three, so the investor's number isn't binding today; the real constraint right now is volume, not efficiency.

I couldn't run this as a live interview (single-shot task), so I derived what the numbers support and flagged every input I don't have rather than guessing at it — per the skill's anti-fabrication rule. Treat the judgment calls below (marked **DECISION**) as things to confirm with your co-founder, not benchmarks.

---

## Inputs

| Input | Value | Status |
|---|---|---|
| Price | $49/mo, one plan | measured |
| Gross margin | 80% | **estimated** (no confidence level given — is this net of processor fees/refunds?) |
| Contribution per customer/month | $39.20 (49 × 0.80) | derived |
| Ad spend | ~$400/mo | **estimated** ("roughly") |
| New customers from ads | ~9/mo | **estimated** ("about") |
| CAC (paid, new-customer, blended) | $44.44 | derived — **not fully-loaded** (excludes founder time, tools) |
| Runway | 15 months | measured |
| Total monthly burn | — | **missing** — needed to set a $ cash cap on ad spend specifically |
| Churn / retention | — | **missing** — needed for a true break-even (CAC recovered before the customer leaves) |
| Measurement trust | — | **missing** — is the 9/$400 a clean attribution read, or platform-reported? |
| Approvers | — | **missing** — who at Lanternfish can pause spend vs. raise the ceiling? |

## Derivation

```
Contribution per customer-month = $49 × 80%                = $39.20
Current CAC                     = $400 / 9                 = $44.44
Current payback                 = $44.44 / $39.20           = 1.1 months
```

At 1.1-month payback, you're recovering acquisition cost almost twice as fast as anyone would ask a bootstrapped company to. This is the single most important number in this policy: **you are not CAC-constrained, you are volume-constrained.**

**On the investor's "5 months":** that's his portfolio's target, not yours (David Skok's own commonly-cited bands put 5–7 months as healthy and call anything past 12 "anemic" — the 5-month figure is in that tradition, not something unique to your business). It happens to translate to CAC ≤ $196 (5 × $39.20). Directionally it's not unreasonable for a bootstrapped company — you carry no subsidized runway, so faster recovery than a venture-funded peer (who can defend 18–24 months) is the right instinct — but it's still quoted, not derived from your margin or your 15-month runway. I'd adopt it as your **target**, not treat it as gospel.

**On break-even:** the skill's standard formula (`allowable CAC = contribution per sale`) is built for one-time purchases. For a subscription, CAC above one month's contribution doesn't mean you're losing money — it just means recovery takes more than one billing cycle. The literal single-month figure ($39.20) is almost exactly your current CAC, so using it as the "stop, always" line would trigger a halt on your current performance, which is wrong. The number you actually need for a true break-even — CAC recovered before churn takes the customer — requires a retention rate you haven't given me. **This is a real gap, not a rounding error: get a churn number before this policy is final.** Until then, I'm using 12-month payback (~$470) as a stage-guidance outer bound, labeled as guidance, not arithmetic.

## Layers

| Layer | CAC ceiling | Payback | Consequence |
|---|---|---|---|
| Target floor | **$196** | 5 months (investor's ask, adopted) | Investigate at your next weekly check-in |
| Hard floor | **~$310** (DECISION) | 8 months | Automatic halt on the channel |
| Outer bound | **~$470** (stage guidance, not break-even) | 12 months | Full stop + re-derive the whole policy, since this is guidance not arithmetic |

The $310 hard floor is a judgment call, not a benchmark: it sits between your target and the outer bound, giving room to test scaling spend before anything auto-halts, while stopping well short of the "anemic" zone. Move it if it doesn't match how much testing risk you two actually want.

## Cash cap

Not computable — I have your runway (15 months) but not total monthly burn, so I can't say what dollar level of ad spend the cash position actually tolerates. At $400/mo it's obviously immaterial today. Before you scale spend by, say, 3–5x, get the burn number and recompute this — that's the check that actually protects your runway, independent of how efficient the CAC looks.

## Guardrail set (2–3 metrics, each with a counter-metric)

1. **CAC** (paid, new-customer, 4-week trailing) — counter-metric: **trial/signup-to-paid conversion rate**. Buying cheap-but-low-intent signups is the obvious way to "beat" a CAC target while quietly hurting the business.
2. **Payback period** (CAC ÷ $39.20) — no separate counter-metric needed; it's the scaling gate itself.
3. **Ad spend as a fixed monthly figure**, reviewed against runway — no counter-metric needed; it's the cash constraint itself, pending the burn number above.

## Kill-switch — sized for your volume

At 9 conversions/month (~2/week), a single bad week is noise, not signal. Don't let the kill rule react to it:

- **Streak**: trailing 4-week CAC above the hard floor ($310) for 2 consecutive trailing reads.
- **Rate**: $300 spent in any 7-day window with trailing CAC above the hard floor.
- **Evidence gate**: no kill before 4 weeks of data **and** at least 15 conversions attributed to the channel — below either bar, hold spend flat, don't kill. (At your current run rate that's roughly your entire monthly output, which is itself a sign you're too low-volume to make confident weekly calls — treat every single-week read as directional, not decisive.)
- **Restart**: resume at prior budget once the cause (creative, targeting, tracking) is named and fixed; review again after 2 weeks.

## Governance (fill with actual names — I don't have them)

- **Ceiling owner**: whichever founder isn't running the ad account day-to-day. Separation of duties still applies at two people — the one spending shouldn't also be the one who decides a breach is fine.
- **Escalation**: target breach → discuss between the two of you within the week; hard-floor breach → automatic halt, same-day joint decision to restart or not.
- **Exceptions**: time-boxed, written down somewhere durable (even a shared doc), never standing.
- **Re-baseline**: quarterly, plus immediately if you get real churn data, margin changes, or your burn rate changes materially.

## Exemptions

None recommended yet. At $400/mo and 9 conversions/mo you're below the volume where a ring-fenced testing slice is statistically meaningful — carving out 10–15% of $400 leaves too little to learn from. Revisit this once monthly spend or conversions roughly triple.

## Assumptions that would invalidate this policy

- **Churn is the big one.** If monthly churn is high (say, north of 8–10%), even your current $44 CAC might not be recovered before the customer leaves, which would mean the whole "you have massive headroom" conclusion is wrong. Get this number before treating any of these ceilings as safe.
- 80% gross margin assumed net of processor fees and refunds — confirm.
- $400/9 is described as approximate; if actual CAC is meaningfully above $44, payback stretches proportionally but stays well under target either way at these margins.
- CAC here is spend-only, not fully-loaded (founder time, tools) — fine for a paid-channel guardrail, but don't use it as your only signal of true unit economics.