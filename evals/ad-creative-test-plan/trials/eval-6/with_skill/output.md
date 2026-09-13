# Nordvik Outdoor — Creative Test Plan (Thursday launch)

Before the plan itself: **your stated reading plan and launch sequencing both break the test.** I've corrected them below rather than writing them up as designed — shipping them as-is would put "95% significance" on a number that can't legally carry that label, and the skill this plan follows treats that as the one failure mode it exists to prevent.

## Three corrections — non-negotiable

1. **Delivery-limited at $250/day/cell.** At a $45 CPA, the stable-delivery floor is `$45 × 50 ÷ 7 ≈ $321/day/cell`. $250/day sits below it — the cell never reaches stable delivery and the numbers stay noisy regardless of how long you wait. This isn't a sample-size problem, it's a floor problem. **Raise each cell to ~$325/day** (see budget math below), or the test is `Not testable as designed` on CPA from day one.
2. **No day-3/4 significance call.** At $250/day ÷ $45 CPA you get **~5.6 conversions/day/cell**. By day 4 that's ~22 conversions/cell. The rigorous two-proportion test needs low thousands per cell for any realistic lift (see table below); even the loose, non-authoritative "100–400 conversions" screening convention isn't cleared. **A 95%-confidence winner is mathematically unreachable this week at this spend.** Checking every morning and stopping the instant a number looks favorable is textbook peeking — it inflates false positives, it's not a safeguard against them. Replace it with one pre-registered check at a fixed date (below).
3. **Control must launch with the variants, not 4 days later.** Comparing new cells to the champion's historical numbers is invalid (different seasonality, different delivery history) — the whole point of a control cell is that it runs _concurrently_. Staggering also means the two new concepts get a 4-day head start with no baseline to gate against, and a Thursday→Monday split crosses a weekend, which contaminates day-of-week composition on top of that.
   - **Preferred fix:** hold all three cells to Monday. Four extra days to cut the control's new post IDs is cheap; a broken read is not.
   - **If Thursday is truly fixed:** launch the control Thursday too, on a placeholder post ID, and do not swap the "real" post ID in later — swapping creative under a live cell resets delivery learning mid-test (see Failure modes). Treat the whole week as one clean run on whatever post ID the control launches with.

## Open items — confirm before this plan is final

These weren't in your message. I've flagged them rather than inventing numbers:

| Missing                                                                            | Why it matters                                                                                                                                    |
| ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Baseline purchase/landing conversion rate and CPC                                  | Needed to compute an exact required sample (the table below is decision-relevant even without it, but a precise "Powered" line needs it)          |
| Hypothesis evidence ("because [X]...") and predicted magnitude                     | Section 1 of the underlying method requires this before launch — a test with no falsifiable prediction isn't a test, it's a screen with no target |
| Assets per concept                                                                 | Denney's default is ~6 per cell; confirm how many video cuts exist for each new concept                                                           |
| Monthly test budget and whether it's protected from scaling spend                  | Determines whether the $325/day floor is affordable alongside the rest of the account                                                             |
| Is Advantage+ Creative / any automated creative optimization on for this campaign? | Must be off in test cells or the platform picks winners, not the test                                                                             |
| Any claim-substantiation constraint on the two new concepts?                       | Standard for outdoor/gear DTC (durability, performance claims) — flag now, not at review                                                          |

## Feasibility math

- Daily conversions/cell at $250/day: `250 ÷ 45 ≈ 5.6` → **~39/week** — below the ~50/week stable-delivery floor.
- Stable-delivery floor: `45 × 50 ÷ 7 ≈ $321/day/cell`. Recommended cell budget: **$325/day**.
- New daily conversions/cell at $325/day: `325 ÷ 45 ≈ 7.2` → ~51/week, clears the floor.
- Total test spend: 3 cells × $325/day = **$975/day** (up from $750/day), **$6,825** over a 7-day window. Denney's own budgeting rule (`avg CPA × 50` per cell = `$45 × 50 = $2,250`/cell) lands at the same $321/day — the floor and the practitioner default agree, which is why $250/day was under-built, not just under-cautious.
- Required sample for a _significance-tested_ CPA winner: at a plausible 2–5% baseline purchase rate and a 50% relative lift, the two-proportion formula needs **~1,500–3,800 per cell** (denominator: clicks/landing views, not raw conversions — we don't yet have that baseline). At ~7 conversions/day this is not reachable inside the 4–6 week test-freshness ceiling.
- **Verdict: this cannot be Powered on CPA at this spend, full stop.** It can be a clean Directional read if run correctly.

## The plan

```
CREATIVE TEST PLAN - Nordvik Outdoor video concept test, 2026-09-17 (Mon)
decision    : better-performing new video concept becomes challenger and gets
              scaled; if neither beats the champion by the stop date, champion
              holds. [hypothesis below needs the team's evidence + target %
              before this plan is complete - see Open items]
hypothesis  : because [insight driving the two new concepts - TBD],
              changing [concept/angle - TBD] will [raise/lower] cost per
              purchase by roughly [magnitude - TBD] for [audience - TBD],
              and we will know by day 7 (directional) / not at significance
              this cycle
isolation   : bundled - unlearnable at element level (two full new concepts,
              messaging + execution changed together; hard Monday date rules
              out tiered or strict isolation this cycle)
structure   : 2 new-concept cells + control champion, concurrent, same launch
              day; manual fixed-budget cells at $325/day each;
              automated creative-optimization: off (confirm Advantage+ status)
metrics     : gate = hook rate / 3-sec view rate vs account trailing median,
              read like-for-like by placement only
              primary = cost per purchase (decision metric)
              guardrails = frequency, CPM vs account baseline, return rate,
              blended account CPA
cells       : C01_ANG-current-champion_V01 (control) | $325/day | [existing assets]
              projected ~7.2 conv/day, ~51/wk | reference cell, same rules
              C02_ANG-<concept-A>_HOOK-<TBD>_FMT-video_V01 | $325/day | [n] assets
              C03_ANG-<concept-B>_HOOK-<TBD>_FMT-video_V01 | $325/day | [n] assets
              each: projected ~51 conv/wk
              required for Powered (CPA, 50% rel. lift, ~2-5% baseline):
                n=1,500-3,800/cell (clicks) -> exceeds 4-6wk ceiling at this
                volume -> VERDICT: Directional read on cost per purchase
              kill: asset at $90 spend (2x CPA) with zero purchases
                    cell at day 7 with no clear directional leader
              scale: best cell +50-100% budget, done 2-3x; regression to the
                     mean expected on the first step - treat it as its own read
              iterate: cell with strong hook rate but weak CPA -> check
                        landing page / offer before touching the creative
schedule    : launch Mon 2026-09-17, all 3 cells same day
              earliest evaluation: day 3 (screening only - kill obvious
              losers at 2x CPA/no conversion; NOT a winner-declaration moment)
              hard stop: day 7 or $2,250 spend/cell, whichever first
              inconclusive -> keep control (champion)
              one pre-registered check at the stop date; no interim
              "shift budget on 95% significance" checks before then
naming      : C##_ANG-<angle>_HOOK-<type>_FMT-video_TAL-<creator>_V##
caveats     : manual cells share auctions - some contamination expected;
              divergent delivery means even the day-7 read is relative
              screening, not causal proof; CPA verdict will be reported to
              the team as a ranking ("B leads A on cost per purchase, not
              yet at significance"), never as "won at 95% confidence";
              return rate matters for hiking gear (sizing) - watch it as a
              guardrail, a cheap-CPA winner with a return spike isn't a win
```

## Anchor used: Denney

Chosen because it needs nothing the account doesn't already have (no benchmark library, no weekly reviewer), and its own budget formula (`CPA × 50`) independently reproduces the $325/day floor computed above — two different checks landing on the same number is a good sign the number is real, not an artifact of one method.

## What "morning check" should actually look like

Check daily if you want, but the only actions available before day 7 are: kill an asset that's burned 2×CPA with zero purchases, or note qualitative signal. Nothing gets paused-and-reallocated, and no confidence number gets said out loud, before the day-7 pre-registered stop.
