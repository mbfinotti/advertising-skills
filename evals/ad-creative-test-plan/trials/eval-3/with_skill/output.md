## Short answer: yes, three things in your plan would produce a number you can't trust, and a fourth thing (the comparison) is measuring against the wrong baseline entirely.

**1. Campaign budget optimization is the wrong structure — never use it for a test.**
CBO (campaign-level automatic budget allocation) is explicitly the worst-ranked test structure: it shifts spend toward whichever cell shows an early lead and can concentrate up to ~90% of budget on one concept before the others collect enough data to be comparable. Cheap to set up, but it corrupts the read — it's not a test structure at all, it's the platform picking a winner before you've measured anything. Switch to **manual fixed-budget ad sets**, one per concept plus control, each running its own protected daily budget. Given your hard 2-week date, the platform-native deterministic split test (Meta's native A/B tool, TikTok Split Test) isn't worth it either — it takes a week+ longer to resolve and at this budget would likely return "no winner" anyway. Manual is the right call here.

**2. Turn the AI creative enhancement off inside the test cells.**
If it's recombining headlines/images/CTAs on its own (Meta's Advantage+ Creative is the likely candidate given your CBO language — confirm platform), the algorithm decides which asset combinations actually ran, not you. You'd then be unable to say "Concept B beat the champion" — you'd only be able to say "some algorithmic recombination of unknown pieces of Concepts A/B/C beat the champion," which answers no question your agency can act on next time.

**3. Comparing the winner to the champion's Q2 CPA of $18 is a new-vs-old comparison — the classic trap.** The champion has been off for a month; Q2 (Apr–Jun) vs. now (mid-September) is a different season, auction, and audience-optimization state entirely, and it's been out of the delivery/learning loop. Any of that could move CPA $5+ in either direction with zero creative signal in it. **Run the champion concurrently as your control cell, same structure, same window, same budget tier as the challengers** — and judge everyone against its CPA *this cycle*, not the stored Q2 number.

**4. There's no pre-registered hypothesis, metric ladder, or kill/scale rule.** "Whichever wins" invites peeking and a declared winner that's really noise. Fix below.

---

## Feasibility math on your numbers

Stable-delivery floor (below this, a cell never stabilizes regardless of what the sample math says): **target CPA × 50 ÷ 7**. Using your $18 reference CPA: **≈ $128.57/day per cell.**

- Your plan as stated: 1 campaign, 3 concepts, CBO — no per-cell budget exists, so this question is moot until you fix #1.
- Fixed structure, 4 cells (control + 3 concepts), $450/day split evenly → **$112.50/cell** — under the floor. Every cell stays delivery-limited; none of the numbers you'd get out of it are trustworthy.
- The number that actually clears the floor with headroom is **~$150/day/cell** (≈17% above floor, matching how much headroom the skill's own worked examples carry).

**$150/day/cell × 4 cells = $600/day.** That's +$150/day (+33%, +$2,100 over 14 days) versus your $450 budget.
**If you hold $450/day flat**, it funds exactly **3 cells** cleanly — control + 2 concepts. The third concept would need a follow-up 2-week window, not a slot in this one.

That's the actual decision in front of you: raise the daily budget ~$150, or drop to two concepts this round.

**On statistical power**: at $150/day/cell, you get ~8.3 purchases/day/cell ≈ **117 purchases per cell over 14 days**. I can't compute an exact required-n without your click-to-purchase rate and CPC (missing — see below), but the reference tables' worked anchors need low-thousands to low-hundred-thousands of denominator events even for a generous 50% relative lift. Unless your funnel is unusually efficient, 117 purchases/cell will **not** reach significance in this window. Call this what it is now, in writing, before launch: a **Directional read** — a screening comparison, never reported as "97% confidence" or "the winner." At your rough spend tier (~$13.5k/month if this is representative of overall spend), that's expected, not a failure — this is proxy-gated screening territory, not a powered A/B test.

---

## Missing inputs (need these to finish, not to start)

- Click-to-purchase rate and CPC — needed to sanity-check the Powered/Directional call precisely
- What decision this feeds: does the winning concept become the new evergreen/scaling creative, or is this just angle-validation before a bigger production round?
- Is $450/day protected test budget, separate from scaling spend?
- Monthly conversion volume account-wide
- 3–6 assets per concept, or is each "concept" a single asset?
- Any health/nutrition claim in the new concepts (protein snacks → claim-substantiation review before launch if so)
- Has conversion tracking been verified recently? (a test on a broken purchase event measures nothing — worth a quick check before spend moves)

I've filled reasonable placeholders below and flagged them — confirm or correct before this ships.

---

## Revised plan

```
CREATIVE TEST PLAN - Peakform three-concept screen, 2026-09-12
decision    : winning concept (if any) becomes the new evergreen creative /
              earns next production round; losers retired or sent back to
              agency with the gate-metric read [CONFIRM: decision framing]
hypothesis  : because the champion has been dark for a month and needs a
              fresh angle to re-enter competitively, at least one of the
              3 new concepts will beat the concurrently-run champion's CPA
              by a meaningful margin for [CONFIRM: audience/targeting],
              by day 14 - directional target, not a significance claim
isolation   : bundled - unlearnable at element level (3 concepts vary
              messaging + execution together; hard 2-week date rules out
              a tiered angle-then-element design)
structure   : control (champion) + 3 concepts, concurrent; manual
              fixed-budget cells, $150/day each ($600/day total - +$150/day
              vs your $450 plan); automated creative-optimization: OFF
              [fallback if budget holds at $450/day: control + 2 concepts
              only, 3rd concept deferred to a follow-up window]
metrics     : gate = hook rate/CTR vs account trailing median, per
              placement, read only >=2,000 impressions/asset - kills
              obvious losers only, never crowns a winner
              primary = cost per purchase (CPA)
              guardrails = frequency, CPM vs account baseline, refund/
              return rate, blended account CPA
cells       : C00_CON-champion_V01 (control) | $150/day | re-verify asset
              count | reference cell, same rules as challengers
              C01_CON-<name>_V01 | $150/day | [N] assets
              C02_CON-<name>_V01 | $150/day | [N] assets
              C03_CON-<name>_V01 | $150/day | [N] assets
              each cell: projected ~8.3 purchases/day, ~117 over 14d
              -> clears ~50/wk stable-delivery floor (needs $128.57/day;
              $150/day carries ~17% headroom)
              required n for Powered on CPA: not computable without
              click-through purchase rate + CPC (missing) - order-of-
              magnitude from reference tables makes Powered unlikely at
              this spend/duration regardless
              VERDICT: Directional read only - declare this before launch
kill        : asset at $36 spend (2x CPA) with zero purchases -> kill
              cell at day 5-7 with no CPA edge over control -> kill
scale       : cell beats control CPA by a pre-agreed margin (ranking,
              not significance) -> +50-100% budget, staged; treat the
              first scale step as its own read (regression-to-mean)
iterate     : cell wins gate metric but not CPA -> check landing
              page/offer before crediting or discrediting the creative
schedule    : launch [date] | earliest evaluation day 3 | hard stop
              day 14 | inconclusive -> keep control running at current
              spend, no challenger promoted
naming      : C##_CON-<concept>_ANG-<angle>_FMT-<format>_V##
caveats     : manual cells still share auctions - overlap/cost inflation
              possible; divergent delivery means even this read is
              relative screening, not causal (Braun & Schwartz 2025);
              Q2's $18 CPA is NOT the benchmark - champion's concurrent
              CPA is; Q2-to-September is a seasonal mismatch on top of
              the staleness problem; 3 concepts vs 1 control = 3
              comparisons - any "winner" is a ranking under noise, not
              a confidence-tested result; confirm conversion tracking
              fires correctly before spend moves
```

Two things to lock in before this launches: confirm the $600/day vs. 3-cell-at-$450 tradeoff, and get the click-through purchase rate so the Directional-vs-Powered call can be stated with real numbers instead of an order-of-magnitude estimate.