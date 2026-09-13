Read the skill (SKILL.md), the worked examples, and the sizing reference in full. Here's the restructured test plan — the freelancer brief as described breaks four rules in the skill (mixed concepts per cell, no control, ad-hoc naming, no pre-registered read standard), so I've fixed the structure, not just the paperwork around it.

---

## What's wrong with the current plan, before the plan itself

1. **Mixing all three concepts into every ad set "for fairness" contaminates the read.** One concept per cell is the rule — more concepts than cells means a result can't be attributed to any single concept. "Fairness" here actually destroys the ability to say anything at all.
2. **`tindra_final_v2_new1.mp4`-style naming will silently break your reporting roll-up.** Ad platforms and reporting tools parse names; without concept/version encoded in a fixed field order, you can't roll results up by concept later even if the test itself was clean.
3. **No control/champion cell.** Is there a currently-running Tindra Home ad? You didn't mention one. If yes, it must run concurrently as a 4th cell at the same budget (never compared against its own historical numbers — unequal delivery history and seasonality make old numbers incomparable). If no champion exists, say so explicitly below — it changes the inconclusive-outcome rule.
4. **"Launch to see what happens" has no decision, no hypothesis, and no pre-registered kill/scale rule.** That's exactly the setup that produces a peeked, after-the-fact story instead of a decision.
5. **The security cell only has 2 assets** — below the 3-6/cell band. Flagged below, not silently absorbed.

Two inputs I don't have and am assuming — confirm or correct:

- **Platform**: assumed Meta paid social (adjust naming/A+ creative note if it's TikTok/Google).
- **Click-to-purchase / CVR and CPC**: not given. I've used the skill's community-convention purchase-count bands instead of inventing a CPC, and flagged where the real number would sharpen this.

---

## CREATIVE TEST PLAN — Tindra Home smart lighting, 2026-09-12

```
decision    : the concept (movie night / wake-up naturally / security-away-mode)
              that wins on cost-per-purchase over the 2-week window gets scaled
              and the next production budget; losing concepts are retired from
              prospecting.

hypothesis  : Because [SUPPLY THE EVIDENCE — e.g. support tickets or reviews
              showing customers cite "forgot to turn lights off when leaving"
              as a pain point], the security/away-mode concept will lower
              cost-per-purchase by roughly 15-20% vs the wake-up-naturally and
              movie-night concepts, for [prospecting / cold audience — confirm],
              and we will know by day 14.
              >>> This hypothesis is a template. The bracketed "because" clause
              is a placeholder — you must supply the real observation before
              this plan is valid. A hypothesis with no evidence behind the
              magnitude is not falsifiable, it's a guess with decimal points.

isolation   : concept/angle, held one per cell (bundled at concept level -
              unlearnable at element level: a cell win tells you the angle won,
              not whether it was the hook, the visual, or the CTA). Promote to
              strict single-variable isolation only once a concept has settled
              as the winner across rounds and volume can power a single-element
              MDE - not before.

structure   : 3 test cells [+ 1 control cell if a current champion exists -
              CONFIRM] | manual fixed-budget cells, $220/day each;
              Advantage+ Creative / dynamic creative optimization: OFF in all
              test cells

cells       : C01_CON-movienight   | 3 assets | $220/day  [in band: 3-6 ✓]
              C02_CON-wakeup       | 4 assets | $220/day  [in band: 3-6 ✓]
              C03_CON-security     | 2 assets | $220/day  [BELOW band 3-6 -
                get one more security-angle asset from the freelancers before
                launch, or launch with 2 and treat the cell's read as thinner
                evidence than the other two - do not silently treat it as equal]
              C00_CON-control      | current champion assets | $220/day
                [ADD THIS if a champion ad exists - do not compare new cells
                to its historical numbers, it must run live, same budget,
                same window]

feasibility (per cell, all three test cells - same math applies to each):
              stable-delivery floor = $24 CPA x 50 / 7 ≈ $171/day
              $220/day clears the floor (~28% headroom) -> delivery-stable ✓
              projected conversions ≈ $220/$24 ≈ 9.2/day ≈ 64/week/cell
              projected over 14 days ≈ 128 purchases/cell
              required sample: at any realistic DTC baseline (2-5% CVR),
                even a large 50% relative lift needs ~1,500-3,800 observations
                in the metric's own denominator per cell (reference anchor
                table); a moderate 20% lift needs 8,000+. Community-convention
                screening band is ~100-400 purchases/cell for a legitimate
                Directional read - our projected 128/cell sits inside that
                band, which is exactly what confirms this is a screen, not a
                significance test.
              multiple comparisons: 3 concept cells run simultaneously against
                the control = 3 comparisons at once; disclosed here per the
                skill's rule even though it's moot while we're Directional -
                a standard correction would add ~30-40% more sample per cell
                if this were ever pushed toward Powered.
              -> VERDICT (all 3 cells): Directional read on cost-per-purchase.
                 Not Powered, not "Not testable" - delivery is stable, there's
                 just not enough purchase volume in 14 days at this spend to
                 clear significance. Report it as a ranking, never as a winner
                 "at 95% confidence."
              optional up-funnel power-up: if you have a verified add-to-cart
                or product-page-view event, tell me its rate and I'll rerun
                this - it may reach Powered, but a comparable-budget worked
                case needed ~22 days even on add-to-cart, so don't assume it
                fits inside your fixed 14-day window either.

metrics     : gate = 3-second hook rate vs. this account's own trailing
              median (not a published "30% is good" band - those conflict
              18-40% across vendors), read only after >=1,000-2,000
              impressions/asset, compared like-for-like by placement
              primary = cost per purchase (decision metric)
              guardrails = frequency, CPM vs. account baseline, return/refund
              rate (physical product - a cheap "purchase" that gets returned
              isn't a win)

decision rules (Dara Denney anchor - adopted as the single anchor; do not
              blend with any other kill rule):
              why Denney: no benchmark library/weekly reviewer exists here
              (rules out Hott), the hard 14-day date rules out Faris's
              no-manual-kill posture (slowest to answer) and rules out a
              tiered structure (needs two test windows), so Denney's
              numeric defaults are what's left and what this budget can run
              without new approvals.
              - no evaluation before day 3
              - kill an asset at 2x CPA spend ($48) with zero purchases
              - kill a cell after 5-7 days with no relative leader
              - scale the winning cell's budget +50-100%, done 2-3 times
              - test-budget checkpoint ≈ CPA x 50 = $1,200/cell (hit ~day 5.5
                at $220/day - a natural mid-test look, not a decision point)

schedule    : launch all cells the same day, including the control - never
              stagger a control's launch, it picks up day-of-week/seasonality
              contamination the test cells didn't see
              earliest evaluation: day 3 (no judgment before, and only past
              a minimum volume floor)
              hard stop: day 14 (your decision date) or the ~400/cell
              screening ceiling, whichever comes first
              inconclusive -> keep control [or: do not scale any concept and
              re-run with a champion added, if no control exists today]

naming      : C##_CON-<concept>_HOOK-<type>_FMT-<format>_V##
              C01_CON-movienight_FMT-video_V01 / V02 / V03
              C02_CON-wakeup_FMT-video_V01 / V02 / V03 / V04
              C03_CON-security_FMT-video_V01 / V02
              (fill in HOOK-<type> per asset once you know it - the field
              order stays fixed either way, or the reporting roll-up breaks)

caveats     : manual cells still share auctions against overlapping
              audiences - expect some cost inflation and blurred attribution,
              this is a known limitation, not a bug in the setup
              in-platform results (including any native split test) are
              relative screening, never causal proof - divergent delivery
              means even a clean-looking cell win can reflect who the
              algorithm served each ad to, not just the creative
              security cell is under-band on assets (2 vs 3-6) - its read
              carries less evidence than the other two cells by design
              open items to close before launch: confirm platform (assumed
              Meta), confirm whether a champion exists, supply the real
              "because" evidence for the hypothesis, supply CVR/CPC if you
              want the sample math sharpened past the community-convention
              band used above
```

---

**Bottom line:** three ad sets, one concept each (not mixed), a control if you have one, structured filenames, $220/day/cell clears the delivery floor comfortably, but 14 days at this spend gives you a **Directional read** on cost-per-purchase — a legitimate ranking, not a 95%-confidence winner. Don't let anyone present it as more than that at the readout.
