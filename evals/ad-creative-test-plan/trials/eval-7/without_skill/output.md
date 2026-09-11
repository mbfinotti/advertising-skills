# Vantail — Hook Rate Creative Test Plan

## 1. Objective
Identify which of 5 new video creatives earns the scale budget, using 3-second hook rate as the primary decision metric, since purchase volume won't reach significance fast enough to decide on CPA/ROAS alone.

## 2. Structure: fix the placement problem first

Hook rate benchmarks are **not comparable across placements**. Reels (full-screen, autoplay, sound-on default) structurally scores higher on 3-second view rate than Feed (partial-screen, often sound-off, more competing content). A single 30% bar applied to both groups will systematically favor the Reels videos regardless of creative quality.

**Fix: run two separate leaderboards, not one.**
- Cell group A — Reels: 2 videos, compared against each other only.
- Cell group B — Feed: 3 videos, compared against each other only.
- The winner is decided *within* each group first. If you need one final winner across both, compare each video's hook rate to its own group's baseline/median (relative lift), not to the other group's raw number.

## 3. Campaign setup
- One ad set (cell) per video — 5 cells total. Isolates the creative variable; no other variable (audience, placement mix, bid) should differ within a group.
- Use ABO (ad set budget), not CBO — CBO will silently reallocate spend before you have a valid read, defeating the test.
- Same audience, same optimization event, same bid strategy across all 5 cells.
- Placement forced per group: Reels-only for the 2 Reels cells, Feed-only for the 3 Feed cells. Don't let automatic placements blend the signal.

## 4. Budget & duration
- $400/day × 5 cells = $2,000/day total spend.
- Run minimum 3 full days before any read — 3-second view events accumulate fast, but you want to smooth out day-of-week and early-delivery volatility.
- Minimum sample size before trusting a hook rate: **≥5,000 impressions per cell**. Below that, a few outlier viewers can swing the % by several points. At $400/day this threshold should clear within 24–48 hours per cell; confirm before reading results.

## 5. Metric definition
- **Hook rate = 3-second video plays ÷ impressions** (not ÷ reach, not ÷ link clicks). Lock this formula in the reporting template so every cell is measured identically.
- Pull it from the platform's native video metrics, not a proxy.

## 6. Success criteria

**Primary gate:** ≥30% hook rate to qualify as "strong" and be eligible for scale.

**Decision logic:**
1. Within each placement group, rank cells by hook rate.
2. Any cell below 30% is disqualified regardless of rank.
3. Among qualifying cells, the highest hook rate in each group wins that group's placement budget.
4. If a group has zero cells clearing 30%, do not force a winner — hold that group's scale budget and iterate on the hook (first 1–2 seconds) rather than scaling a weak opener.

**Guardrail (don't let hook rate override common sense):** even with slow purchase accumulation, check two downstream signals before committing scale budget:
- Hold rate / 15-second view rate — a video can hook fast and drop off fast, which doesn't sell.
- CPA trend so far, even directionally — if the top hook-rate video is tracking at 3x your $28 target while another qualifying video is tracking near target, flag it for the next round rather than an automatic override. Hook rate decides *among videos that aren't already showing a red flag on cost*, not in spite of one.

## 7. Timeline
- Day 0: Launch all 5 cells simultaneously.
- Day 1–2: Monitor for delivery issues only (disapprovals, learning phase stalls). No creative decisions yet.
- Day 3: First valid read once each cell clears 5,000 impressions. Check hook rate + guardrails.
- Day 3–4: If results are clear (a real gap, not noise), reallocate: pause non-winners, shift their daily budget into the winning cell(s) per group.
- Day 5: Confirm the scale decision is holding (hook rate stable, no CPA blowout) before fully committing the week's budget to the winner(s).

## 8. Reporting template (per cell)
Video ID | Placement group | Impressions | 3-sec plays | Hook rate | Hold rate (15s) | Spend | Purchases | CPA so far | Qualifies (Y/N)