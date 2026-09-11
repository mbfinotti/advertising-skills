# Cartelle Creative Test Plan — Reality Check + Restructured 6-Month Program

I read `ad-creative-test-plan` and its two reference files in full before building this. I'm not going to hand you the six-slot micro-variable calendar as briefed — the math says it would burn six months producing noise, not learning, which is the opposite of what you told me you actually want. Here's the honest version, with the numbers shown so you can audit every conclusion.

## Why the backlog as specified doesn't survive the feasibility check

**Assumptions used** (swap these for real account numbers before launch — everything below scales with them):
Meta paid social · conversions objective · $6,000/mo, no separate protected test budget stated (full account = test infrastructure) · CPA $70 (given) → ~86 purchases/mo account-wide · CPC $1.25 (assumed) · CPM $18 (assumed) · landing-page-view rate 35% of clicks (assumed) · derived CVR = CPC/CPA ≈ 1.8%.

**The hard numbers:**

- **Stable-delivery floor** on the purchase event = CPA × 50 ÷ 7 = 70 × 50 ÷ 7 ≈ **$500/day per cell**. A minimal 2-cell test (control + 1 challenger) needs **~$30,000/month** just to stop being delivery-limited — 5× your entire current spend.
- **True significance** on any of these six elements, measured on CPA/CVR itself at a generous 20% relative MDE, needs ~24,000 clicks/cell ≈ **$30,000 spend/cell (~$60,000 total for one test)**. That's the $100k-1M/month spend tier in the skill's own guidance — not this account.
- Six items — CTA copy, a dash, beige vs off-white, model orientation, serif vs sans, price display — are all **copy/layout/typography micro-variables**. The skill's explicit instruction: *"Refuse to burn spend isolating micro-variables (button color, font, minor copy) at normal budgets — fold them into a concept or drop them."* Its own spend-tier table puts "normal" starting around $20k/month. You're at 30% of that.

**Verdict, stated plainly: every one of the six items, run as its own isolated single-variable cell, is `Not testable as designed` at $6,000/month.** This isn't a production or design problem — no test structure fixes a budget/effect-size mismatch. Isolating a beige-vs-off-white background or a headline dash would need six-figure sample sizes (the reference's own anchor: 5% baseline, 5% relative lift ≈ 122,000/cell) regardless of how long you run it, because the true effect of those two is almost certainly inside your day-to-day performance noise, permanently.

## The restructure

1. **Fold all six backlog items into one bundled "refresh" cell** vs. your current champion. Bundling is the only posture that buys a *detectable* effect at this budget (the skill ranks bundled #1 on efficiency for exactly this reason). Labeled honestly: `bundled — unlearnable at element level`. This uses month 1.
2. **Reserve months 2–6 for real high-leverage levers** — concept, angle, hook, format, talent. These are the only lever classes the skill sanctions for isolation, and they're the ones that can actually move a number this account can see. This is also what compounds into transferable learning — six months of noise on a font doesn't.
3. **Revisit the original six items once the account can dedicate ~$15,000/mo to one test cell** (stable-delivery floor) — and ~$60,000 total for one test if you want them significance-tested rather than directional. Until then they ride inside concept bundles; they never get their own slot.

This keeps your two real constraints: one lever changes at a time *within each slot*, and the program is built to accumulate reusable learning rather than chase a single winner.

---

## Test 1 — Bundled creative refresh (uses the backlog)

```
CREATIVE TEST PLAN - Refresh bundle v1, Cartelle
decision    : does the bundled "new-look" creative replace the current champion
              as always-on control for Q1 2027
hypothesis  : because no creative variable on this account has been tested,
              a bundled refresh (price hidden, "Shop the collection" CTA,
              off-white bg, model facing left, serif overlay, headline dash)
              will move landing-page-view rate ~30% vs champion, for cold
              prospecting, by day 10; effect on cost-per-purchase is a
              screening target, not a significance claim
isolation   : bundled - unlearnable at element level (6 elements change
              together; deliberate, since none of them is individually
              testable at this budget - see feasibility note above)
structure   : 1 challenger + control (champion), concurrent; manual
              fixed-budget cells, $100/day each ($3,000/mo each);
              automated creative-optimization (Advantage+/dynamic creative):
              OFF in both cells - CONFIRM this is currently on, unconfirmed
metrics     : gate = outbound CTR vs account trailing median, per placement,
              read only at >=2,000 impressions/asset
              primary = landing-page-view rate (up-funnel proxy, powered)
              business = cost per purchase (directional/guardrail only)
              guardrails = order/customization cancellation rate, frequency,
              CPM vs account baseline, blended account CPA drift
cells       : C01_CTRL-champion_V01 (control) | $100/day | existing asset(s)
              C02_PKG-refresh2026Q4_V01 (challenger) | $100/day | 3-6 assets
              projected ~80 clicks/day/cell, ~196 page-views/wk/cell
              required (page-view rate, 30% rel MDE, 35%->45.5%):
                n=349 clicks, ~$436, ~5-7d -> VERDICT: Powered on page-view rate
              required (cost per purchase): ~43 purchases/cell over 28d,
                far below any powered threshold -> VERDICT: Directional read,
                judged as relative ranking + guardrails, never "at 95% confidence"
              kill: asset at $140 spend (2x CPA) with zero purchases
              scale: challenger promoted to new champion if it wins page-view
                     rate AND guardrails hold; first scale step (+50-100%
                     budget) treated as its own read, not assumed to repeat
              iterate: wins proxy but breaches a guardrail -> hold, do not
                       scale, re-test isolated once volume supports it
schedule    : launch Mon 2026-09-21 | earliest evaluation day 5 (09-26)
              | hard stop day 28 (2026-10-19) | inconclusive -> keep champion
naming      : C##_PKG-<bundle-name>_V##
caveats     : manual cells share auctions - overlap noted; a null result here
              is expected and informative (rules out a large bundled effect),
              not a failed test; divergent delivery means even the "Powered"
              proxy read is relative, not causal; mirroring vs. re-shooting
              the model-orientation photo - CONFIRM which (a mirror flip can
              read oddly if any text/logo is in frame); price-hidden needs a
              precise operational definition for made-to-order (no price? or
              "from $X"?) - CONFIRM before asset production
```

---

## Tests 2–6 — real high-leverage levers (template + illustrative fills)

Same feasibility math applies to every future test at this budget (constant CPA/CPC/spend), so the numbers below repeat almost unchanged — this is the reusable part of the program. Swap the bracketed content per test; keep the structure fixed.

```
structure   : 1 challenger + control (current champion, rolling - incorporates
              prior winners), $100/day each; manual fixed-budget cells;
              automated creative-optimization: off
metrics     : gate = outbound CTR, like-for-like by placement, >=2,000 impr/asset
              primary = landing-page-view rate, 20-30% relative MDE
                -> n~350-800 clicks/cell, ~5-12 days -> Powered
              business = cost per purchase -> ~43 purchases/cell/mo
                -> Directional read only, always
kill        : asset at $140 spend (2x CPA), zero purchases
scale       : winner -> new rolling champion, +50-100% next step, first
              step is its own read
iterate     : proxy win + guardrail breach -> hold, re-test, don't scale
schedule    : 28-day window each, launch Monday, earliest eval day 5,
              hard stop day 28, inconclusive -> keep control
naming      : C##_ANG-<angle>_HOOK-<hook>_FMT-<format>_TAL-<talent>_V##
```

| Test | Lever (sanctioned: concept/angle/hook/format/talent) | Launch | Hard stop | Illustrative fill (replace with real assets) |
|---|---|---|---|---|
| 2 | Angle | Mon 2026-10-19 | 2026-11-16 | Craftsmanship/durability story vs. speed-and-customization story |
| 3 | Hook | Mon 2026-11-16 | 2026-12-14 | Problem-led opener ("tired of off-the-shelf sizing?") vs. benefit-led opener |
| 4 | Format | Mon 2026-12-14 | 2027-01-11 | Static product photography vs. short-form UGC/process video |
| 5 | Talent/creator | Mon 2027-01-11 | 2027-02-08 | In-house model vs. real customer testimonial creative |
| 6 | Consolidation | Mon 2027-02-08 | 2027-03-08 | Scale the strongest cumulative winner as its own read (regression-to-mean check); or re-test the closest call from tests 2-5 per the iterate path |

Total: $6,000/mo × 6 = $36,000 test-period spend, none of it incremental — this is your existing budget, restructured.

## Kill/scale anchor (adopted once, applied to all six tests)

**Dara Denney's set**, adapted — chosen because it needs nothing this account doesn't already have, and because your stated "compounding learning over single winner" goal explicitly deletes the Andrew Faris anchor (no-manual-kill, portfolio-only, no element-level read) per the skill's own named rule. Barry Hott is deleted too — it needs a standing best-ads library and a weekly reviewer, which a $6k/mo solo-run account doesn't have.

- Asset-level kill: 2× CPA spend ($140), zero purchases.
- No verdict before day 5.
- Cell-level: no early kill before the up-funnel proxy window closes; hard stop day 28 regardless.
- Scale winners +50–100%, done 2–3 times across the program, each step read as its own result.
- Peeking is the named failure: the day-5/day-28 gates exist so nobody eyeballs day-2 numbers and calls a winner.

## What I need you to confirm before test 1 launches

- Replace CPC/CPM/page-view-rate assumptions with real account numbers — this changes every duration and spend figure above.
- Confirm Advantage+ Creative / dynamic creative is currently on (it usually is by default) and can be switched off in test ad sets.
- Confirm the exact "champion" creative currently running — that's your control.
- Lock the operational meaning of "price hidden" for a made-to-order product (no price shown at all, vs. a "from $X" starting price).
- Confirm model-orientation asset production: a genuine second-angle shoot, not a mirrored flip (flips can misread if any text/logo sits in frame).

**Bottom line:** you asked for rigor and for learnings that compound. At $6,000/mo, the six items you listed can't deliver either individually — they're too small to separate from noise no matter how long you wait. One bundled refresh this month, then five real concept/angle/hook/format/talent tests, gets you both. Revisit the original backlog once you can put ~$15,000/mo behind a single test cell.