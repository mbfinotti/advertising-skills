# Paid Media Scale-Up Plan — $60K → $180K/month

## The flaw in the current logic

Platform-reported ROAS is not causal. Before allocating the $120K increase, this needs to be said plainly to the CFO:

- **Branded search (11x)** mostly captures demand that already exists — people who already know Finchley and were going to convert via organic/direct anyway. The platform takes 100% credit for a conversion it didn't create.
- **Retargeting (7.8x)** re-engages visitors sourced by other channels. It's stealing credit from whatever brought them to the site the first time, not generating new revenue.
- **Cold prospecting (2.1x)** is the only channel creating _new_ demand. Its reported ROAS is structurally understated because platform attribution doesn't credit it for the branded search and retargeting conversions it seeds downstream.

"Proven winners" here means "proven in a ledger that's biased toward channels that harvest rather than create demand." Scaling on that basis will look great on the dashboard and be wrong in reality.

## Structural ceiling problem (independent of attribution)

Even ignoring attribution bias, branded search and retargeting **cannot structurally absorb a 3x budget increase**:

- Branded search volume is capped by brand awareness. Tripling spend into a near-fixed query volume means bidding up an exhausted auction — rising CPCs, and cannibalizing clicks you'd get for free organically.
- Retargeting pool size is capped by top-of-funnel traffic. Without more new visitors, 3x-ing retargeting spend just means more frequency on the same people — ad fatigue and negative marginal returns, not more revenue.
- Cold prospecting is the only channel with real headroom to absorb new budget at volume.

Putting most of a 3x increase into the two channels least able to absorb it is close to a best case of wasted spend and a worst case of active harm (creative/audience fatigue, CPC inflation raising cost on your _existing_ $60K base too).

## Recommended approach: test, then scale by evidence

Don't deploy the full increase on day one. Run a 4–6 week incrementality phase in parallel with a conservative first tranche of new budget.

**Lift tests to run immediately (using the existing $60K, no incremental spend needed):**

1. **Branded search holdout** — pause branded search bidding in a matched sample of geos/markets for 2–4 weeks; compare organic + direct conversions vs. control geos. This isolates true incremental lift from brand-term bidding.
2. **Retargeting conversion lift study** — use Meta/Google's built-in ghost-ads/PSA holdout (a portion of your retargeting audience sees a public-service ad instead, is still tracked). Both platforms support this natively.
3. **Cold prospecting geo lift test** — matched-market test: increase spend in a subset of geos, hold flat in control geos, compare blended pipeline/revenue. If historical spend variance exists, a lightweight MMM can cross-check this.

Cost is mostly opportunity cost, not new cash — this runs inside the current $60K.

## Phased budget rollout

**Phase 0 (Month 1, spend stays ~$60–70K):** Launch all three lift tests. Do not commit new budget yet beyond a small, reversible test increase for cold prospecting (new audiences, new ad platforms, creative testing) since that's the one channel safe to scale on priors alone.

**Phase 1 (Month 2, ramp to ~$110–120K):** Allocate based on early readouts.

- Branded search: +20–30% max, focused on long-tail/competitor terms, not a blanket increase — defend share, don't assume linear scaling.
- Retargeting: scale only in proportion to top-of-funnel traffic growth (pool size), not to the 3x target. If prospecting hasn't grown the visitor pool yet, retargeting stays flat.
- Cold prospecting: majority of the new budget — new audiences/lookalikes, additional platforms (LinkedIn, programmatic display, content syndication/ABM given B2B self-serve + sales-assist), new creative angles.

**Phase 2 (Month 3, reach $180K):** Reallocate using confirmed lift results.

- If branded/retargeting lift comes back genuinely strong: scale further, but model a decay curve, not a flat 11x/7.8x continuing at 3x spend.
- If lift is low (the likely outcome given the mechanics above): cap branded search and retargeting near their Phase 1 levels and push the remaining increase (likely $80–100K+ of the $120K) into cold prospecting and new channel expansion.

## Guardrail metrics (track weekly, not monthly)

- **Blended CAC / blended MER** (total revenue ÷ total spend) at the company level — the only number immune to cross-channel credit-stealing.
- **New-to-brand customer count and CAC**, separate from total conversions — the CFO approved this budget for growth, not for buying back existing pipeline more expensively.
- **Branded search query volume trend** — a leading indicator that prospecting is working. If cold spend rises and branded query volume doesn't follow over 60–90 days, prospecting isn't creating new demand and needs rework, not more budget.
- **SQL/pipeline creation by channel** (not just self-serve conversions) — since this is B2B SaaS with sales-assist, cold prospecting likely feeds longer-cycle assisted deals that a last-click, short-window ROAS number will always undervalue.
- **Retargeting frequency/reach** — watch for fatigue signals as a check against over-scaling into a fixed pool.

## What to tell the CFO

Recommend against putting most of the $120K increase into branded search and retargeting. Frame it as: protect the investment with a 4–6 week test phase (near-zero incremental cost), then scale each channel to what the data shows it can actually deliver — rather than to what platform dashboards, which have an in-built incentive to over-credit themselves, report. Expect blended CAC to rise somewhat as spend scales — that's normal — but this avoids pouring six figures into two channels that are structurally capped and largely measuring the same demand twice.
