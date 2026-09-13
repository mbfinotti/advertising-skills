# Paid Media Scale-Up Plan: $95K → $300K/Month

**Prepared for:** Board of Directors
**Prepared by:** [Growth/Performance Marketing]
**Date:** September 12, 2026
**Re:** Path to $300K/month blended paid media spend (Meta + Google) by end of Q3

---

## Executive Summary

The board's target and the proposed mechanism don't fit inside the time remaining. Assuming Q3 ends September 30, 2026, there are **18 days** left. A flat 20%/week increase on both accounts, compounding from $95K, reaches roughly **$152K by quarter-end — about half the target** — and wouldn't actually cross $300K until early-to-mid **week of October 20**, three weeks into Q4. Before deciding how to scale, the board needs to resolve the timeline question, because it changes the entire plan (see Decision Required, below).

Separately, "raise budgets 20%/week until we hit the number," used as the sole mechanism, is undercapitalized against real constraints in this account: platform auction relearning, creative supply, audience saturation dynamics, and measurement reliability. Those aren't reasons to reject scaling — they're reasons to scale with guardrails instead of a blind percentage rule. This memo lays out both the math problem and a revised plan that gets as close to the board's number as is defensible, with explicit checkpoints and a floor on efficiency.

---

## 1. Where We Are Today

| Metric                                | Value                                  |
| ------------------------------------- | -------------------------------------- |
| Current monthly spend (Meta + Google) | $95K                                   |
| Target monthly spend                  | $300K (3.16x)                          |
| Blended ROAS                          | 3.1x                                   |
| Measurement stack                     | Platform reporting (Meta/Google) + GA4 |
| 30-day core audience penetration      | ~12%                                   |
| Creative output                       | 10 new assets/month, in-house          |

Two things worth naming plainly:

- **12% penetration is genuine headroom on paper**, but it doesn't mean the next dollar buys inventory at the same 3.1 ROAS. The first 12% is, by definition, the highest-intent, cheapest-to-convert slice the algorithms found. The next dollars go into audiences with structurally lower intent — ROAS compression as spend scales is the expected case, not a failure mode, and the plan needs to say how much compression is tolerable.
- **Platform-reported ROAS and GA4 are both biased in ways that get worse as spend scales.** Meta and Google each attribute conversions using their own models, and both platforms tend to claim overlapping credit for the same conversion (double-counted in a naive "blended ROAS" sum). GA4 undercounts on top of that (consent mode, ITP/cookie loss, cross-device gaps). Neither source, alone or added together, tells you the _incremental_ revenue a new dollar of spend produces — which is the only number that matters when deciding whether to keep scaling.

---

## 2. The Timeline Math

Assuming calendar Q3 (ends September 30, 2026) and today's date (September 12), there are 18 days / 2.6 weeks remaining.

| Week                                 | Cumulative spend at +20%/week      |
| ------------------------------------ | ---------------------------------- |
| Today                                | $95K                               |
| +1 week                              | $114K                              |
| +2 weeks                             | $137K                              |
| Quarter-end (2.6 weeks)              | **~$152K**                         |
| Weeks needed to actually reach $300K | **6.3 weeks (~44 days) → ~Oct 27** |

**Under the proposed mechanism, the board's number is not reachable inside Q3.** It's reachable about a month into Q4, and only if ROAS holds at every step, which is the part most likely to break under this much velocity.

This is the fact that needs to go to the board before anything else: either the deadline moves, the definition of "hit $300K" moves, or the mechanism changes to something more aggressive than +20%/week — which brings its own, larger risks (below).

---

## 3. Why "+20%/Week, Both Accounts, No Other Changes" Is Under-Specified

This isn't a reason to abandon the ramp — it's a list of what the plan is currently missing.

- **Auction relearning risk.** Both Meta and Google's own delivery systems treat budget jumps above roughly 20–30% within a learning-phase window as a reset trigger — CPA/ROAS typically degrades for 3–7 days after each jump while the algorithm re-explores. A _weekly_ 20% bump on both platforms simultaneously means the accounts may never fully exit relearning before the next jump hits, which compounds inefficiency rather than compounding spend efficiently.
- **Creative supply is fixed while spend isn't.** 10 new assets/month was sized for a $95K/month account. At $300K, the same creative pool absorbs 3x the frequency, which accelerates fatigue (rising CPMs, falling CTR) — especially on Meta. Scaling budget without scaling creative variety usually shows up as ROAS decay within 2–3 weeks, exactly the symptom the naive plan has no way to distinguish from "the market is saturated."
- **No efficiency floor is defined.** The plan says "raise budgets until we hit the number," with no stated point at which the team stops because ROAS has dropped too far. Without a floor, this plan can technically "succeed" (hit $300K) while destroying contribution margin.
- **Moving both channels in lockstep removes diagnosis.** If blended ROAS drops, a synchronized 20%/week increase on both platforms gives no way to tell whether Meta or Google (or both) is the one degrading — so there's no way to correct mid-flight.
- **No incrementality check.** At this scale of increase, it's worth validating that platform-reported ROAS reflects real lift before betting the full ramp on it — a geo holdout or conversion-lift test run in parallel costs little and de-risks the rest of the spend.

---

## 4. Recommended Plan

### 4.1 Decision required from the board (this is the gating step)

Pick one — the operating plan below is written to support all three, but the target and the risk the team is asked to carry are different in each:

| Option                       | What it means                                                                                            | Tradeoff                                                                                                                                                                                                                                                                                      |
| ---------------------------- | -------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **A. Extend the deadline**   | Treat $300K as an exit run-rate reached by a stated date in Q4 (e.g., end of October), not a Q3 average. | Lowest execution risk; matches the math above.                                                                                                                                                                                                                                                |
| **B. Redefine "hit $300K"**  | Reach a $300K/month *run-rate* in the last week of Q3 (not $300K averaged across the month).             | Achievable closer to the original deadline; monthly Q3 spend total will still land well under $300K.                                                                                                                                                                                          |
| **C. Compress the timeline** | Push hard for $300K inside Q3 regardless.                                                                | Requires jumps larger than 20%/week, an explicit board-approved ROAS floor (e.g., "we will accept blended ROAS falling to X before pausing"), and diversifying beyond Meta+Google (see 4.4) since two accounts likely can't absorb a 3.16x increase this fast without severe relearning cost. |

Recommendation: **Option A or B.** Option C is achievable but should be entered with eyes open on margin impact — it trades CAC efficiency for speed, and the board should set the acceptable ROAS floor explicitly rather than discover it in the P&L.

### 4.2 Ramp mechanism (replaces the flat 20%/week rule)

- Cap increases per platform at **≤20–25% per step**, gated on a **minimum 5–7 day observation window** post-increase before the next step — not a fixed weekly clock. If ROAS hasn't stabilized, hold, don't raise.
- Set a **floor**: pause further increases on a platform if trailing 7-day ROAS drops below an agreed threshold (tie this to contribution margin, not to 3.1 — the board should approve the specific number).
- Move Meta and Google independently, sized to where each platform's marginal efficiency is holding best, not in lockstep.

### 4.3 Creative velocity

- Scale creative supply roughly in proportion to spend growth, not leave it fixed. Rule of thumb: budget for meaningfully more net-new assets per month as spend approaches 2–3x current levels.
- Supplement in-house output with freelance/UGC/agency support for the ramp period rather than permanently resourcing for a peak — this is a burst need tied to the scale-up, not a steady-state one.
- Track frequency and CTR decay per asset weekly; retire fatigued creative proactively instead of waiting for ROAS to show it.

### 4.4 Measurement and validation

- Run a **geo holdout or conversion-lift test** in parallel with the ramp on at least one platform to validate that platform-reported ROAS reflects real incremental revenue, not just claimed conversions.
- Report blended ROAS **de-duplicated** for cross-platform double-attribution, alongside GA4, alongside the incrementality read — three numbers, not one blended figure, so the board sees where they agree and where they don't.
- If timeline pressure is real (Option C), diversify acquisition beyond Meta+Google (YouTube, TikTok, retail media, affiliate) rather than forcing two auctions to absorb a 3.16x increase in under three weeks — spreading the increase across more channels reduces relearning shock on any single platform.

### 4.5 Weekly board reporting, for the duration of the ramp

- Spend by platform vs. plan
- Blended ROAS (platform, GA4, and incrementality estimate)
- CAC / contribution margin
- Core audience penetration trend
- Creative fatigue indicators (frequency, CTR trend, active asset count)
- Any pause/hold triggered by the ROAS floor, and why

---

## 5. Bottom Line for the Board

The team can get close to $300K/month, but not inside Q3 under the mechanism as proposed, and not without an explicit answer on how much ROAS compression is acceptable in exchange for speed. Recommend the board choose Option A or B above at this meeting, approve a ROAS floor, and approve incremental creative budget to support the ramp — then this plan executes starting this week.

---

If you want this turned into a formatted document (Word/PDF) or a slide deck for the actual board meeting, say the word and I'll produce it.
