# SPEND GUARDRAIL POLICY — Plumeria Skincare
**Status: PROVISIONAL** (see gate below) · effective 2026-09-12 · review 2026-10-13, or immediately on either gap closing

---

## Why this is provisional, not final

Two inputs are broken, and the skill this policy follows treats that as a stop condition, not a detail: a guardrail built on numbers nobody trusts manufactures confident wrong decisions.

1. **Contribution margin is a guess** ("50–60%, probably") — confidence level 1, not finance-reviewed. Every number below shifts if the real figure is outside that band.
2. **The conversion feed is unreconciled**: Meta reports ~40% more revenue than Shopify. That is not noise — it's large enough that a guardrail read off Meta's dashboard is measuring a different business than the one that actually gets paid. Per the guardrail discipline: never set a threshold on platform-reported ROAS. **Shopify revenue is the source of truth below; Meta's Ads Manager numbers are not used to bind any floor.**

Because you asked for something to operate on today rather than nothing, this policy is built to be safe under uncertainty: it binds on the *worse-case* end of your margin guess, and it prices in a buffer for the fact that the guess could still be wrong. Treat it as a placeholder to tighten, not a benchmark to defend.

---

## Inputs

| Input | Value | Status |
|---|---|---|
| Contribution margin (CM3) | 50–60% | **estimated**, low confidence |
| AOV / price | — | **missing** |
| Payback target | — | **missing** |
| Cash runway / monthly burn | — | **missing** |
| Cash cap on paid media | — | **missing** |
| Meta vs. Shopify revenue gap | Meta ≈ 1.4× Shopify | **measured but unreconciled** — root cause unknown |
| Sales/repurchase cycle | — | assumed short (skincare DTC), **unconfirmed** |

Everything downstream in this policy fails if the margin guess is wrong or if the 1.4× gap turns out to be more than double-counting (e.g. genuine incrementality Shopify isn't capturing). Both are named as open risk in Assumptions, not smoothed over.

## Derivation

```
Break-even ROAS = 1 / margin

  at 60% margin (optimistic bound): 1.67x
  at 50% margin (conservative bound): 2.00x   <- this is the one that binds

Binding rule: guardrails are set on the worse-case margin (50%), because
setting them on the hopeful end (60%) means you find out you were wrong
by losing money, not by a warning firing first.

Allowable CAC (break-even) = AOV x margin
  = AOV x 0.50, i.e. CAC ceiling <= 50% of AOV
  (AOV wasn't given — apply this as a ratio to whatever your AOV is;
   don't wait on that to start using the ratio)

Attribution translation (Meta dashboard -> real economics), stop-gap only:
  Meta-reported ROAS overstates true ROAS by ~1.4x
  True MER floor 2.0x  ==>  Meta-dashboard proxy floor ~2.8x
  This conversion factor is itself a single unreconciled data point.
  It is a temporary reading aid, not a substitute for fixing the feed.
```

Worth naming so it isn't quoted at you as if it were derived: the common "4x ROAS" target floating around ad accounts is folklore with no traceable author — it's simply break-even at a 25% margin, retroactively treated as a rule. At your (estimated) 50–60% margin, 4x would be roughly double what your business actually needs to break even. Don't adopt it.

## Layers

| Layer | Threshold (true, Shopify-based) | Meta-dashboard proxy* | Consequence |
|---|---|---|---|
| **Break-even floor** | MER 2.00x / CAC ≤ 50% of AOV | ~2.8x | Stop, always — no discretion |
| **Hard floor** | MER 2.20x / CAC ≤ 45% of AOV | ~3.1x | Automatic halt of scale-ups + escalation |
| **Target floor** | MER 2.50x / CAC ≤ 40% of AOV | ~3.5x | Investigate at next review, not a stop |

\*Proxy column exists only until the feed is reconciled — retire it the day it is.

The 0.20x and 0.30x gaps above break-even are **not derived from a profit plan** (you don't have a payback target or cash cap set yet) — they're a flat buffer sized to absorb the margin guess being wrong by a few points either way. Replace them with real numbers the moment you have a payback target and a cash cap; until then, treat Target and Hard floor as placeholders, not benchmarks.

## Guardrail set (2, per the two-or-three rule)

1. **Blended MER**, weekly — **source: Shopify order revenue ÷ total paid spend. Never Meta Ads Manager.**
   Counter-metric: new-customer share of orders (a MER held up by retargeting existing buyers isn't growth).
2. **Contribution margin after ads**, weekly, computed against the 50–60% band as a range until finance confirms a point estimate.
   Counter-metric: discount depth / % of orders on promo (skincare DTC margin is commonly propped up by discounting, which this would hide otherwise).

## Kill rules

```
Streak     Blended MER (Shopify-based) below hard floor (2.2x) for 5
           consecutive days
Rate       25% of the week's planned budget spent while MER sits below
           the hard floor  (expressed as % of budget, not a dollar
           figure — your actual spend level wasn't given)
Evidence   No kill before $750-1,000 spent on a campaign AND 3 days
           live; below either bar, hold spend flat, don't kill
Restart    Resume at 50% of prior daily budget once a specific cause is
           named and fixed; full budget after 1 clean week
Fail-closed  "No data" / feed broken / stale Meta-Shopify reconciliation
           counts as a blocking state, not as "the number is fine" —
           hold spend flat, don't scale on an unreconciled read
```

## Governance

- **Owner of break-even and hard floor:** *[name needed — not filled in, because inventing one would defeat the point of separating who spends from who sets the ceiling]*
- **Owner of target floor / weekly review:** *[name needed]*
- **Escalation:** target breach → weekly review; hard breach → same-day decision by the named owner above; break-even breach → immediate halt, no discretion.
- **Exceptions:** must be time-boxed (max 14 days), a specific written reason, logged — "seasonal push" or "seemed fine" doesn't qualify.
- **Re-baseline:** quarterly, **plus immediately when**: (a) finance confirms a real margin number, (b) the Meta/Shopify gap is reconciled, (c) COGS, shipping, or pricing changes.

## Exemptions

None defined — no testing/exploration budget was mentioned. Worth adding one later so tests aren't held to the same bar as scaled spend, but not invented here.

## Assumptions — what breaks this policy

- If real contribution margin turns out below 50%, every floor above is wrong and must be re-derived, not nudged.
- If the Meta/Shopify gap isn't simple over-attribution (duplicate conversions, inflated attribution windows) but reflects Shopify under-capturing real sales, the "Shopify is source of truth" call above is also wrong — worth a quick incrementality or UTM-reconciliation check before trusting this policy past a few weeks.
- No AOV, payback target, or cash cap were provided, so the CAC ceiling above is a ratio, not a dollar figure, and Target/Hard floor are a flat buffer, not a profit-plan-derived number.

---

**Two things would turn this from provisional to real, fast:** a finance-reviewed margin figure, and a reconciliation of why Meta and Shopify disagree by 40%. Until then, operate on the Shopify-based numbers above and don't let Meta's own dashboard be the thing that tells you whether to keep spending.