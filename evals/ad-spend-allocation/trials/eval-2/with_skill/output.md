# Loam & Ember — Paid Media Spend Allocation

**Before the split: the even five-way $2,400 doesn't survive the funding-floor gate.** At your $35 target CPA, a prospecting/audience-based channel (Meta, TikTok, Pinterest) needs roughly `$35 × 50 ÷ 7 ≈ $250/day` (~$7,500/month) just to feed its ad-delivery algorithm ~50 conversions/week — the volume it needs to exit learning phase and optimize at all. Below that, you're not testing the channel, you're underfeeding it and reading noise. $2,400/month is under a third of that floor. Google Search only needs ~$50/day (~$1,500/month) to be viable, so it's the one channel where $2,400 actually clears the bar. Running all five thin is five underpowered experiments, not one diversified presence — this is the classic even-split fallacy, and it's the reason a $5K–20K monthly budget is conventionally sized to **search + two social/video channels**, not five.

At $12,000 total, even two full-floor social channels ($7,500 × 2 = $15,000) don't fit alongside search. So the real choice at this budget is **search + one paid-social channel**, not five thin lines.

## Gates

| Gate | Result |
|---|---|
| **Affordability** (CAC ÷ margin × retention) | **Cannot compute.** Contribution margin isn't worked out. AOV $120 and your $35 target CPA are taken here as an owner-set boundary, not independently verified against payback — see Open Questions. |
| **Measurement maturity** | Meta pixel installed 2 weeks ago, **events unverified**. No conversion-tracking status given for Google Ads/GA4, TikTok, Pinterest, or YouTube. Treat the whole account as pre-verification — plan below is provisional until tracking is confirmed. |
| **Funding floor** (per channel, at $35 target CPA) | Google Search non-brand floor ≈ $1,500/mo — **clears**. Meta/TikTok/Pinterest floor ≈ $7,500/mo each — **fail** at $2,400. YouTube has no sourced floor in this framework; by the same auction-learning logic it's unlikely to clear at $2,400 either — **rejected this cycle as unaffordable to test properly**. |
| **Data basis** | Pre-launch — no platform-reported numbers exist yet to mistrust. Flag for the cycle after launch: don't let platform ROAS drive the next resplit without accepted (business-level) outcome data behind it. |

Evidence label for every line below: **directional proxy / heuristic posture** — this is a new account with zero spend history, so nothing here is measured or tested yet.

## Approach

**Named heuristic posture** (budget-tier channel gating + funding floors), not a reweight — there's no existing account history to reweight. Marginal evidence takes over starting the first resplit once real data exists.

## The Split

```
SPEND ALLOCATION — Month 1, total $12,000/month (fixed)
Approach   : Named heuristic posture (zero account history)
Evidence   : All lines directional proxy — no measured/tested data yet
```

| Line | Current | Proposed | Rationale | Expected effect | Uncertainty | Owner | Verify | Rollback threshold |
|---|---|---|---|---|---|---|---|---|
| **Google Search, non-brand** | $0 (new) | **$4,500** | Clears its $1,500 floor with real room for category-term coverage; auction/keyword channel, lowest cold-start risk of the set | Directly readable clicks/conversions from week 1 | Medium — new account, no impression-share-lost data yet | Freelancer | Day 30 | Conversion tracking still unverified by day 14 → pause optimization, run on Maximize Clicks until fixed |
| **Meta, prospecting** | $0 (new) | **$7,500** | Funded exactly to the paid-social learning-phase floor — below this, the algorithm can't exit learning at your target CPA | Enough weekly volume (~50 target-CPA conversions/wk) to actually read performance by day 30 | High — pixel installed but **events not yet verified** | Freelancer | Day 14 (pixel check), Day 30 (spend review) | Purchase event not confirmed firing correctly in Events Manager Test Events by day 14 → **hold spend at current level, do not scale, switch campaign objective off Purchase-conversion optimization until fixed** |
| **TikTok** | — | **$0 — rejected this cycle** | Fails funding floor at any slice of remaining budget (~$7,500/mo needed; none left after Search + Meta) | — | — | — | — | — |
| **Pinterest** | — | **$0 — rejected this cycle** | Same floor failure. Qualitatively a strong long-term fit for cookware (visual, high purchase-intent), but not affordable to test properly this cycle | — | — | — | — | — |
| **YouTube** | — | **$0 — rejected this cycle** | No sourced floor for video/auction algorithms in this framework, but same logic applies — $2,400 is very unlikely to buy enough weekly conversion volume to optimize | — | — | — | — | — |
| **Total** | **$0** | **$12,000** | Sums exactly to the fixed total | | | | | |

**Experiments this cycle:** none funded below floor. Per the skill's own rule: if the budget can't clear a channel's floor, the fix is fewer channels, never a thinner spread — a $2,400 "test" slice on TikTok/Pinterest/YouTube would be underpowered by design, not a real read.

## Constraints

- **Creative supply for Meta**: rule of thumb is proven-ad inventory ≈ monthly budget ÷ $5,000 → at $7,500/mo you want at least **1–2 proven ad concepts** ready before launch, not one.
- **Pixel verification** blocks Meta from scaling past floor — this is the binding constraint on that line, not budget.

## Open Questions (answer these before or alongside launch)

1. **Which one social channel** — Meta, Pinterest, or TikTok? This plan defaults to **Meta** (broadest prospecting tooling, most mature ad infrastructure) but that's a judgment call, not a data-backed pick — you have zero account history on any of them. Pinterest is a real qualitative alternative for a home/kitchen brand (visual intent, often cheaper CPMs) if you'd rather start there instead. Your call.
2. **Contribution margin per order.** Without it, the $35 CPA target can't be checked against actual payback — it's currently just your stated number, not a verified boundary. Nail this down before the day-30 review.
3. **Tracking status on every channel besides Meta** — Google Ads conversion tracking / GA4, and (if Pinterest is picked instead of Meta) the Pinterest tag. None of this was confirmed.
4. **When budget could grow past ~$20K/month** — that's roughly the point (Search + 2 full-floor social channels) where a second social channel becomes affordable to test properly, matching TikTok/Pinterest/YouTube back into the mix.

## Revisit

- **Day 14**: Meta pixel verification checkpoint — confirm Purchase event fires correctly in Test Events before any scaling decision.
- **Day 30**: first real read on both lines — cost per new customer vs $35 target, Search impression-share-lost, Meta weekly conversion volume.
- **Day 60**: first resplit decision — move from heuristic posture toward marginal-evidence reweighting once real spend/outcome data exists on both lines.
- **Governance**: you're the sole approver. Have the freelancer flag any move above 10% of a channel's budget to you before executing; get your explicit sign-off above 25%.

## Anti-fabrication check
Amounts sum to $12,000 exactly. No line is funded on invented data — Meta and Search are funded to their sourced learning-phase floors, not to a proportional guess. TikTok/Pinterest/YouTube are rejected with an explicit reason, not silently dropped or given a token amount. Margin and full tracking status are named as missing, not assumed.