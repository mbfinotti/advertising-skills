# Fernbox Consolidation Plan (Meta, B2C)

## Classification

| Campaign                   | Spend (30d) | Purchases      | Verdict                           | Why                                                                                                                                                                                                                                                                                                                              |
| -------------------------- | ----------- | -------------- | --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Broad prospecting**      | $5,400      | 41             | **Keep** (merge destination)      | Best-performing, no preserve rule needed — it's where the others land. Still under Meta's ~50/wk exit-learning threshold (9.6/wk) and under its own budget floor ($180/day vs $286/day floor at $40 target CPA) even alone.                                                                                                      |
| **Interest stack 2023**    | $1,350      | 6 (unreliable) | **Insufficient evidence**         | Attribution window changed mid-window (7-day → 1-day click, day 12/30). That breaks the Evidence Gate's "no tracking change mid-window" rule — the 6 purchases blend two incompatible counting methods and understate the true rate for the back two-thirds of the window. Don't merge, keep, or count it against threshold yet. |
| **Premium tier**           | $2,100      | 11             | **Keep, structurally separate**   | Protected by two preserve rules at once: unit economics differ materially (3x margin → its own target CPA), and the offer/product genuinely differs. Pooling it into the $40-target budget would optimize it against the wrong number.                                                                                           |
| **Spring 2024 launch**     | $750        | 0              | **Merge** into Broad prospecting  | Archaeological (no one can state a live reason). $750 spend = 6.25x the Evidence Gate's 3x-target-CPA minimum ($120) — zero purchases here is real signal, not noise. Highest-confidence merge in the account.                                                                                                                   |
| **Podcast listeners test** | $90         | 0              | **Prune** (pause, fold budget in) | Also archaeological/unowned. Budget-starved by two orders of magnitude ($3/day vs $286/day floor) — that alone is conclusive regardless of purchase count. Spend is below the 3x-target minimum, so the zero-purchase reading alone would be inconclusive, but the budget test doesn't need it to be.                            |

## The merge, concretely

1. **Pause** Spring 2024 launch and Podcast listeners test today. Don't delete — pausing doesn't reset learning, deleting destroys the history.
2. **Raise Broad prospecting's budget** $180 → $208/day (+15.6%). That's under Meta's ~20% significant-edit threshold, so it's a safe in-place bump, not a rebuild.
3. **Leave Premium tier alone** — separate budget, separate target CPA. Action item: nail down its actual target number from the 3x-margin figure (not just "about 3x") so its own budget floor and pass/fail can eventually be judged.
4. **Fix Interest stack's data before deciding it.** Cheapest option: check whether the platform can re-pull the whole 30-day window under 1-day click; otherwise hold the setting steady and take a fresh 14–21 day read. Only then run the volume/budget test. If it turns out archaeological too (nobody has stated why "2023" is still separate either), it becomes a second ≤20% budget step into Broad prospecting a few days later — don't stack it onto the +15.6% move already done.

## Measurement

- **Baseline to beat:** blended CPA of the three folding-in branches pre-merge = $6,240 / 41 = **$152.20**.
- **No-touch window:** 14 days minimum before reading anything, 30 days for the real verdict (short B2C sales cycle).
- **Re-check dates:** interim read ≈ **2026-09-26**, full verdict ≈ **2026-10-12**.
- **Rollback trigger:** blended CPA worse than 1.5x baseline (~$228) after the no-touch window — shift budget back to the paused campaigns if hit.
- **Pass bar:** blended CPA at or better than $152.20. The real target ($40) is a separate, bigger problem — see caveat.

## Two things this merge won't fix — flagging, not solving

- **Broad prospecting's real CPA is $131.71 against a $40 target** (3.3x over). Consolidation recovers divided learning signal; it can't close an economics gap this size by itself. If CPA is still 3x+ target after the merge clears its pass bar, that's a creative/audience/landing-page problem — route to `ad-account-diagnostic`, not another restructure.
- **Even fully merged, the $40-target volume (~41–47 purchases/month ≈ 9.5–11/wk) still sits well below Meta's ~50/week exit-learning threshold.** Structure alone likely won't clear it. Worth testing a higher-funnel proxy event (e.g. Initiate Checkout) alongside Purchase once the structure settles — but confirm structure wasn't the bigger lever first, don't jump straight there.

## Open items I assumed my way past

No answer was given on: budget control/external mandates, contractual reporting needs, whether any branch is currently learning-limited or mid cost-spike, peak season timing, and effort ceiling. None of these change the prune/merge calls above (those are math- and archaeology-driven), but they'd matter if Interest stack turns out to need a `keep but re-parent` instead of a plain merge — worth a quick gut-check with whoever owns the account before phase 2.
