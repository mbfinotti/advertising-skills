# Merge plan — Pinemarten Goods Meta account

## Verdict first

The literal ask — collapse all 11 ad sets into one campaign by Friday — fails the skill's Evidence Gate and shouldn't ship as written. Two independent rules both trip:

- **Panic restructuring.** The account is mid cost-spike *and* 2 ad sets are inside the learning phase right now. Restructuring on top of that is a reflex, not a diagnosis — a second learning reset stacked on an unresolved first one almost always costs more than the spike itself.
- **Big-bang is explicitly ruled out for live accounts.** Merging all 11 at once resets every branch's learning simultaneously. If CPA moves afterward — better or worse — you won't be able to attribute it to anything. You'd be handing the CEO a number with no explanation next month, which is worse than this month's problem.

That doesn't mean "do nothing by Friday." It means the fast, real fix and "one campaign" are two different things — see **This week** below.

## Diagnosis: what's actually driving $38 → $81

Before merging anything, isolate how much of the CPA jump is fragmentation vs. the bid tweak. These are very different problems with very different fixes:

- Editing bids on a live ad set is a learning-resetting edit. Two ad sets relearning simultaneously will run visibly worse for 3-7 days on their own — smaller reach, higher cost-per-result, more volatile delivery — and that alone inflates blended CPA even if the other 9 ad sets didn't move at all.
- Your 10-day panic window is barely one attribution cycle. It's too short to tell "structural fragmentation" apart from "two ad sets mid-relearn skewing the blend," and Meta counts conversions with lag, so the most recent 1-3 days aren't even fully counted yet.

**Before touching structure, get the split:** pull daily CPA for the 2 relearning ad sets vs. the other 9, for the full 10 days. If the spike is concentrated in the 2 that got bid edits, the story is "we caused a relearning dip," not "the account is fragmented" — and the fix is *stop editing, wait it out*, not *merge everything*.

## This week (Friday-compatible, doesn't reset anything)

This is the actual "stop the bleeding" move — `prune`, rung 1 of the ladder. Near-zero build, instantly reversible (pausing ≠ resetting learning), no learning cycle to wait out:

1. **Freeze all edits** on the 2 ad sets currently relearning. No more bid changes, no budget changes beyond routine pacing. Let them exit on their own — Meta's documented exit signal is ~50 optimization events per ad set per rolling 7 days.
2. **Pause, don't merge, anything archaeological.** Any ad set nobody can currently defend with a live business reason — leftover from a past launch, a segment a past media buyer split out and never revisited — gets paused this week. Its budget moves to the survivors in ≤20% steps over the following days (a single large reallocation is itself a learning-resetting edit).
3. **No structural rebuild goes live before Friday.** That's the line to hold with the CEO.

## What I need from you to build the real merge plan

Send these and I'll turn them into the classification table below. Per ad set, for the last 30 days (not just the last 10 — the panic window is too short to judge against):

| Field | Why it matters |
|---|---|
| Ad set name, parent campaign | Confirms whether these 11 are already under 1 campaign or spread across several — changes the whole plan |
| Daily spend | Feeds the budget-floor test |
| Daily conversions on the event it actually optimizes to | Feeds the volume test — never a downstream event Meta doesn't see |
| Daily CPA | Isolates which ad sets are actually driving the spike |
| Optimization event, bid strategy, budget type (ABO/CBO) | Determines what "merge" even means here |
| Audience definition | Needed for the overlap and preserve-rule checks |
| Why it was split out (best guess is fine) | Separates deliberate splits from archaeology — this is the single most load-bearing answer in the whole plan |
| Date of last significant edit | Confirms which ad sets are clean vs. mid-relearn |

Also answer these — short, one-line answers are enough:

- Is $38 CPA a real target derived from margin/AOV on cookware, or an inherited dashboard number? (If inherited, the whole merge math is provisional.)
- Are the 11 ad sets under one campaign today, or spread across several campaigns?
- Any of the 11 running distinct offers, landing pages, geographies, or currencies?
- Any brand-search or retargeting ad set in the mix, or is this all prospecting?
- Total monthly spend and total monthly conversions across the account?

## Classification (fill in once export lands)

Every ad set gets exactly one state — `merge`, `keep`, `keep but re-parent`, or `insufficient evidence`. The 2 relearning ad sets are `insufficient evidence` by default until they've run a clean, unedited 7-day window — judging them now, mid-reset, would misclassify them either way.

| Ad set | 30-day conversions | Clears 50/7-day threshold? | Clears budget floor? | Preserve rule applies? | State |
|---|---|---|---|---|---|
| (the 2 relearning) | — | — | — | — | `insufficient evidence` — wait for clean window |
| (other 9) | pending export | pending export | pending export | pending export | pending |

Budget floor per ad set: **daily budget ≈ target CPA × 50 ÷ 7**. At a $38 target that's ~$271/day minimum to realistically reach the exit threshold; at $81 it's ~$579/day. Any ad set funded below its floor is fragmented by *money*, independent of what its audience looks like — that's usually the cheapest thing to fix and often explains more of the spike than audience overlap does.

## Preserve-rule check (run before merging anything)

Don't merge an ad set just because it's under threshold — check first whether a real reason protects it:

- Different margin or AOV per product line (e.g., a premium cast-iron line vs. an entry nonstick set) — keep split, one CPA target can't serve both.
- Any brand-search or retargeting ad set — keep separate from prospecting, or it eats the pool and prospecting goes blind while blended CPA looks great.
- Distinct offers or landing pages per ad set — one merged ad set can't carry two promises.
- Geography/currency differences, if any.

Anything that clears none of these is a real merge candidate.

## Phase 2 — the actual consolidation (conditional, not this week)

Runs only after: (a) the export confirms genuine fragmentation, not just relearning noise, and (b) the 2 relearning ad sets have cleared a clean 7-day window.

1. **Build new, don't edit in place.** Create merged ad sets fresh for each group of unprotected, sub-threshold ad sets; shift budget over; pause (never delete) the originals.
2. **Start with the archaeological merges** — no one defends the split, so no sign-off fight, and it's the highest-confidence win.
3. **Keep segmentation in creative, not structure.** If any merged group still needs to speak to different customer segments (e.g., gift-buyers vs. home-cooks), run one creative variant per segment inside the merged ad set rather than keeping separate ad sets.
4. **Pool only comparable-cost ad sets.** Merging a cheap and an expensive ad set into one budget typically sends 70-90% of spend to the cheaper one within days — that's a second starvation problem, not a fix.
5. **One no-touch window per phase:** 7 days minimum, 14 for a real read. No edits, no "just nudging the bid," during that window — that's how merges get reverted on day 3 before they can prove anything.
6. **Never launch a phase mid cost-spike or right before a peak week.** If cookware has a holiday-adjacent peak coming, time phase 1 to land fully clear of it.

## Measuring it

- Baseline: pre-merge blended CPA over the full 30-day window, not the 10-day panic window.
- Pass threshold at re-check (1 learning cycle + enough days for a real read, ~14-21 days post-phase): every surviving ad set clears its volume and budget floor, and blended CPA is at or better than the 30-day baseline — not just better than $81.
- Rollback trigger, agreed before phase 1 goes live: blended CPA worse than ~1.5x baseline after the no-touch window, or budget starves an ad set you decided to protect. Rollback = unpause the old structure, not delete anything.

## What to tell the CEO

"Single campaign by Friday" would blow up the learning phase on top of itself and we'd have no way to tell if it worked. What actually stops the bleeding by Friday is freezing edits on the 2 ad sets our media buyer just reset and pausing anything we can't justify — that's real, fast, and doesn't gamble the account. The full merge is 2-3 weeks out, once we can tell fragmentation apart from the relearning dip we caused ourselves.

Send the export and I'll fill in the classification table and give you exact phase dates.