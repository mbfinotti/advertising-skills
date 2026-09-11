# Plumecraft Channel Plan — 2026-09-12

Two corrections up front, because they change the whole setup:

- **Retargeting can't be your day-one channel.** It's a capture mode, not a channel — it multiplies traffic you're already buying. At 900 visits/month, your retargeting pool is roughly 130–220 people (engaged browsers) and maybe 45–90 add-to-carts, well under what any ad platform needs to spend meaningfully or exit learning. There's nothing to retarget yet.
- **Geo-lift holdout testing from day one is the wrong measurement rung.** It's the highest-effort, lowest-efficiency reading in the whole stack — a standing job requiring clean geographies and weeks of deliberately withheld spend. It's reserved for your biggest line item once spend justifies withholding part of it. Running it on a $4,800/month line for a brand-new brand would starve your primary channel below its own learning threshold to feed a test that has no statistical power anyway.

Both ideas are individually reasonable framings ("retargeting is efficient," "incrementality is the gold standard") applied at the wrong scale for a brand at 900 visits/month and $6K/month.

## Assumptions (confirm before locking budget)

Not stated in the brief — I've assumed the conservative default and flagged where the answer changes the plan:

1. **Geography**: assumed US-only. If multi-country, re-check CTV/retail-media US-concentration and consent-tracking loss in the EU.
2. **Repeat purchase / LTV**: assumed none yet (new brand) → allowable CAC uses first-order economics, not LTV:CAC.
3. **Creative capacity**: assumed unconfirmed. This decides whether short-form video (craftsmanship process content) becomes your second channel in 60 days or your third in 6 months.
4. **Checkout/purchase tracking**: assumed not yet verified end-to-end. Do this before any spend — a channel test on broken tracking measures nothing.
5. **Sold anywhere besides your own site** (Etsy, Amazon Handmade)? Changes whether retail media is in scope.
6. **Deadline / one-off vs. compounding**: assumed no hard deadline, compounding build preferred (fits a handmade-goods brand better than a flash sale).

## 1. Economics

- AOV $310 × 62% margin → **contribution per sale ≈ $192**.
- Break-even ROAS = 1 / 0.62 ≈ **1.61x** (not the folk "4x" target — ignore any benchmark framed that way).
- No LTV data yet → allowable CAC falls back to first-order: **≈$135** (about 70% of contribution, leaving room for variable costs and returns/damage on a shipped physical product).
- Payback: immediate at first sale (one-time durable good, no subscription) — the discounted-payback math isn't binding until you have repeat-purchase data.

## 2. Deleted channels

| Family | Gate failed | Reason, dated 2026-09-12 |
|---|---|---|
| Retargeting (as a funded, standalone day-one line) | Funding/signal floor | 900 visits/month → pool far below any platform's practical minimum; nothing to multiply yet |
| Podcast/audio | Affordability / funding floor | $6K < ~$15K measurability floor across 3+ shows |
| Connected TV | Affordability | $192 contribution can't clear $20–40 CPM + $1,500+ production reliably at this spend |
| B2B professional networks | Disqualifier | Consumer product, no firmographic ICP |
| Retail media | Disqualifier (conditional) | Only applies if sold on a marketplace — assumed DTC-only pending confirmation; revisit if you list on Etsy/Amazon Handmade |
| Geo-lift/incrementality (as day-one measurement) | Funding floor | Spend too small and too new to withhold any without starving the primary; not a channel, deferred as a measurement rung |

None of these come back into the table below. Retargeting specifically gets **layered back in as a near-zero-cost secondary** once a real pool exists — see Section 7.

## 3. Candidates ranked by value ÷ effort — survivors only

| Rank | Family | Value (presence/reach/reachability/measurability) | Effort (creative burn/skill/reversibility) | Value ÷ Effort |
|---|---|---|---|---|
| 1 | Paid social prospecting | High — handmade/craftsmanship is genuinely strong visual content, ICP reachable via interest targeting, reach unbounded by your current 900-visit trickle | Medium — standing creative job, but scalable down to one consolidated ad set | Best ratio among channels whose ceiling isn't capped by existing traffic |
| 2 | Paid search (small capture slice) | Low-moderate — real but thin category search volume ("handmade chandelier," "artisan floor lamp") for a new, low-awareness brand | Very low — week of setup, near-zero ongoing, pausable in minutes | High efficiency, low absolute ceiling — good as a slice, not a primary |
| — | Retargeting | N/A day one (no pool) | Near-zero once a pool exists | Reintroduce at ~60–90 days, not scored here |

**Departure from the default ordering**: paid search normally leads step 4's default efficiency order, but Plumecraft's near-zero existing demand (900 visits/month, brand-new) caps its reach subscore hard enough that paid social prospecting — normally mid-table on efficiency — wins the ratio here. This is the same reasoning the skill uses in its own B2C worked example.

**Starved-family check**: short-form video is the other family the ratio would normally starve (highest value, heaviest effort). It's not promoted yet because creative capacity is unconfirmed (open question #3) — promote it once you know you can sustain 10–20 video variants/month; craftsmanship-process content for handmade lighting is a strong natural fit.

**Price-discovery bucket** (native/discovery, programmatic display, paid review listings): not ranked, not funded on day one. Eligible as a second channel only after a small real-money test returns an actual cost number.

## 4. Primary recommendation

**Paid social prospecting.** Handmade lighting is a demand-creation category for a brand nobody's heard of yet — people aren't searching for "Plumecraft," and category search volume for niche artisan lighting terms is real but thin. Social is the only surviving family whose value ceiling isn't bounded by your current trickle of traffic, and craftsmanship/process content plays directly to its strengths.

## 5. Funding plan

Budget: **$6,000/month**.

- **$4,800 (80%)** → one consolidated paid-social prospecting ad set. At the ~50-events/ad-set/7-day learning threshold, $6K/month can't sustain 50 *purchases*/week at a $135 target CPA — so optimize to a higher-frequency proxy event (Add to Cart or Content View) rather than Purchase, and keep it as a single ad set. This is the standard fix when budget sits below the purchase-optimization threshold; splitting into multiple ad sets here would just re-create the "$10K split five ways" anti-pattern at smaller scale.
- **$900 (15%)** → paid search, small always-on capture slice on exact-match category terms, sized after price discovery.
- **$300 (5%)** → reserve. Fold back into prospecting until a real retargeting pool exists (Section 7); don't spend it on a third experiment.

## 6. Test design

1. **Price discovery**: ~$100 on paid social against your best-guess interest clusters (handmade/artisan home decor, interior design, sustainable/craft goods buyers); ~$100 on paid search exact-match terms. Learn real CPC/CPM before committing the rest.
2. **Real test**: 3–5x target CPA per creative concept. At a $100–135 target CPA (under the $135 ceiling), that's **$300–675 per concept**. Run 6 weeks — a $310 purchase is considered, not impulse, so lean to the long end of the social norm (3–6 weeks). Same weekday start/end.
3. **Pass**: CPA ≤ $135 at 90–95% confidence.
4. **Kill**: $270–405 spent on a concept with zero purchases after a readable sample → diagnose creative/targeting/landing page before rerunning, don't just cut and move on.
5. **Don't judge early**: a $310 considered purchase needs the full cycle to read. Don't call a concept dead at day 10.

## 7. Second-channel triggers

- **Real, funded retargeting**: add once prospecting has run long enough to build an actual pool — practically, once monthly sessions and add-to-cart events climb well past current levels (roughly 60–90 days of funded prospecting traffic, not calendar days). Until then it rides along for free wherever the ad platform auto-includes it — don't budget it separately.
- **Short-form video**: add once (a) prospecting shows saturation (rising CPA, frequency crossing ~2.5–3) or (b) you confirm you can sustain 10–20 craftsmanship-process video variants/month.
- **Anything else** (native/discovery, programmatic, a second social ad set): only once budget crosses the ~$50K/month practitioner breakpoint or prospecting clearly saturates — never by thinning the current $6K.

## 8. Measurement approach

This is the actual fix for what the consultant was reaching for with geo-lift — just at the right rung for your scale:

- **Day one**: UTM discipline + last-non-direct attribution. An hour to set up, enforced forever, and it's the cheapest reading you have.
- **Immediately on top**, because a creation channel (paid social) is the primary: add a **"How did you hear about us?"** field at checkout. This is the cheapest correction to the well-documented bias where platform dashboards over-credit capture channels and under-report social by something like 70%. Don't judge paid social on its own ad-platform dashboard alone.
- **MER** (total revenue ÷ total ad spend): not a separate rung yet at $6K/month — but start sanity-checking platform-reported ROAS against actual Shopify/store revenue now, and formalize MER as a tracked metric once that gap becomes visibly material.
- **Geo-lift/incrementality**: explicitly deferred. Revisit once total spend is well past the scaling breakpoint (~$50K/month) and concentrated enough on one line to fund a holdout without starving it. Setting this up "from day one" at current scale would consume effort for a reading with no statistical power.
- **Before any spend moves**: verify checkout/purchase-event tracking end-to-end (open question #4). A test on unverified tracking measures nothing.