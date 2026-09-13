# Loamly — Paid Channel Plan (2026-09-12)

## The board's number is the wrong gate — here's why

LTV:CAC of 3.2:1 is a blended figure sitting on top of two products that don't behave alike. It can't describe both at once, and averaging them produces a number that describes neither. Payback per plan is the real gate.

**Reverse-engineering your customer mix from blended ARPU ($74):** solving `19w + 549(1-w) = 74` gives **w ≈ 90% Starter, 10% Scale** by customer count. Nine in ten of the customers a $200 CAC actually buys are Starter customers — so that's the economics that matter most, not the Scale economics the blended average is secretly weighted toward.

**Contribution margin per sale** (price × 82% margin):

| Plan    | Monthly gross profit/customer |
| ------- | ----------------------------- |
| Starter | $19 × 0.82 = **$15.58**       |
| Scale   | $549 × 0.82 = **$450.18**     |

**Payback at the agency's $200 CAC** — raw and discounted for churn (`CAC / (monthly gross profit × annual retention)`):

| Plan                    | Raw payback                  | Discounted payback (retention-adjusted) | Verdict                                                                |
| ----------------------- | ---------------------------- | --------------------------------------- | ---------------------------------------------------------------------- |
| Starter (45% retention) | 200/15.58 = **12.8 months**  | 200/(15.58×0.45) = **28.5 months**      | Fails — outside the 3–12mo band, past even the 18mo enterprise ceiling |
| Scale (92% retention)   | 200/450.18 = **0.44 months** | 200/(450.18×0.92) = **0.48 months**     | Under 3 months — signals _underinvestment_, not health                 |

**Allowable CAC by plan** (derived, 12-month target, discounted for retention):

- Starter: 12 × 15.58 × 0.45 ≈ **$84** (up to ~$126 even at an 18-month enterprise-grade ceiling)
- Scale: 12 × 450.18 × 0.92 ≈ **$4,970**

So the agency's $200 is roughly **2–2.5x too expensive for Starter** and **25x too cheap for what Scale could actually support**. "Safe to pour money into paid" is true only for the 10% of the funnel that lands on Scale. Applied to the 90% that lands on Starter, $200 paid CAC is a slow bleed against 55% annual churn. Front-loaded churn (typical for a low-price self-serve tier) makes the real number worse than the discounted figure shows.

**Verdict: gate paid spend to Scale-fit intent only. Starter goes through organic/PLG, not paid.**

---

## Deleted channels

| Family                  | Gate failed                        | Reason, dated 2026-09-12                                                                                                                                           |
| ----------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Retail media            | Disqualifier                       | B2B software, not sold via a marketplace                                                                                                                           |
| Podcast/audio           | Funding floor                      | Needs ~$15K+ spread across 3+ shows just to be measurable — that's your _entire_ monthly budget with nothing left to concentrate elsewhere                         |
| Connected TV            | Affordability + funding floor      | $500–$5,000+ entry plus $1,500–$15,000+ production; Starter's $15.58 contribution can't clear it, and it's a quarter-long, front-loaded commitment before any read |
| Short-form video        | Disqualifier (capacity unverified) | No stated video capacity, no evidence (Q9) that ops/supply-chain buyers concentrate on short-form surfaces — revisit if that changes                               |
| Paid social prospecting | Not deleted, but unranked here     | No audience-presence evidence for this niche B2B buyer; heavy standing creative burden. Treat as an unproven candidate, not a funded row, until evidence exists    |

**Assumptions flagged, unconfirmed:** sales cycle length, geography/regulation, tracking/landing-page readiness, existing channels, team's channel skill, deadline. None of these changes the payback math above, but confirm them before the budget moves — especially tracking, since a test on unverified tracking measures nothing.

---

## Candidates ranked by value ÷ effort (Scale-tier targeting only)

| Rank | Family                                    | Value (presence/reach/targetability/measurability) | Effort (creative/skill/reversibility) | Ratio    |
| ---- | ----------------------------------------- | -------------------------------------------------- | ------------------------------------- | -------- |
| 1    | Paid search                               | 4+4+3+4 = 15                                       | 1+2+1 = 4                             | **3.75** |
| 2    | B2B professional networks (LinkedIn-type) | 4+4+3+3 = 14                                       | 2+3+4 = 9                             | **1.56** |

No departure from the default efficiency ordering — nothing here overrides it. Paid review listings (G2/Capterra) sit in the unranked price-discovery bucket: B2B software is an actively-compared category, "often skipped, high intent," and G2's entry tier (~$299/month) is cheap enough to run alongside the primary without diluting it.

---

## Primary recommendation

**Paid search, scoped to Scale-fit intent keywords** (e.g. multi-warehouse, enterprise, demand-planning-at-scale terms — not generic/self-serve terms). Capture beats creation here: the category has real search intent, setup is a week, it's pausable in minutes, and Scale's allowable CAC ($4,970) has enormous headroom over any realistic B2B search CPL.

## Funding plan

- **$12,000/month (80%)** → paid search, Scale-fit intent only.
- **$3,000/month (20%)** held in reserve for the review-listings test below (not split thinner than that — five-way splits at this budget would starve every channel below its learning threshold).
- Starter acquisition is **not funded from this budget** — route it to SEO/content/self-serve signup, a decision this skill doesn't cover (that's `ad-spend-allocation`/PLG territory, not paid channel selection).

## Test design

1. **Price discovery**: ~$100–$300 on exact/phrase-match Scale-tier keywords to learn real CPC for this vertical (published B2B CPCs range wildly — don't trust a benchmark for this niche).
2. **Real test**: set target CAC well inside the $4,970 ceiling — e.g. $1,000–$1,500 — and budget 3–5x that per concept ($3,000–$7,500/concept). Run at least 8–12 weeks; B2B considered-purchase cycles read as false negatives on anything shorter.
3. **Pass**: cost per Scale customer ≤ $4,970 at 90–95% confidence.
4. **Kill**: 2–3x target CPA spent ($3,000–$4,500) with zero Scale conversions after a readable sample.
5. **In parallel, not competing for the primary's budget**: run G2/Capterra listings (~$299–$500/month) as its own price-discovery test.

## Second-channel trigger

Add B2B professional networks only when paid search CPA rises on saturation, or once Scale-intent keyword volume proves too thin to absorb $12K/month efficiently — not before, and not by splitting the $15K now. Budget clears its ~$5K/month North America floor when the time comes.

## Measurement approach

- **Segment every report by plan from day one** — a blended CAC/ROAS dashboard is exactly the trap that produced the 3.2:1 number. Track MQL→SQL→Scale-customer, not just signups (a "cheap" signup that becomes Starter isn't a win against this budget's goal).
- UTM discipline + self-reported "how did you hear about us" at signup (cheap, catches what last-click misses).
- Verify conversion tracking end-to-end before the real test starts — this wasn't confirmed and needs to be before spend moves.
