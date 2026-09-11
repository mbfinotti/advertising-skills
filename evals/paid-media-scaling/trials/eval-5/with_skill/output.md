# Media Scaling Ramp Plan — Board Briefing

*Prepared per `paid-media-scaling` methodology. This runs the skill's Interview only to the extent the brief already answers it — every unanswered input below is flagged as an **open item**, not guessed. Present this to the board section by section; each section names what would change your recommendation if the missing input comes back differently.*

---

## 0. The finding that has to lead the memo

Running your own proposed plan — **+20%/week, both accounts, no other conditions** — against the actual calendar:

$95K × 1.20⁷ ≈ **$340K in 7 weeks**, but you only have **18 days** until end of Q3 (Sep 12 → Sep 30, 2026). In 18 days you get roughly **2.5 weekly steps**: $95K → ~$147K. That is **less than halfway** to $300K, even under the most aggressive naive interpretation of your own rule.

There is no safe ramp mechanic — 20%/week, 15%/week, or any documented platform cadence — that closes a **3.16x** gap in 18 days. Closing it in that window requires either:

- **A single ~$205K jump in one move** (+216%), which every platform's documented reset behavior and every practitioner source in this skill treats as the textbook way to spike CAC and blow a "profitable" account into insolvency, or
- **Renegotiating what "committed to $300K by end of Q3" means** with the board — e.g., a run-rate/trajectory commitment reviewed at the Q3 board meeting, not $300K actually spent by Sep 30.

**Recommendation to open with the board:** treat Sep 30 as a **checkpoint date**, not a spend deadline. This plan gets you to a verified, gate-passing **~$150–165K/month by Sep 30** and **$300K/month by ~Oct 31–Nov 7**, on a ramp that's designed not to be rolled back halfway through. That's the honest trade the board is actually being asked to make.

---

## 1. Readiness gates — run before any budget moves

| # | Gate | Status | Why |
|---|------|--------|-----|
| 0 | Affordability (LTV → margin → max CAC) | 🔴 **FAIL — blocking** | No contribution margin, refund rate, or fulfilment cost given. "Blended ROAS 3.1" is a *revenue* multiple, not a *profit* signal — a 3.1 ROAS at 25% margin can already be underwater. **This must be fixed in week 1**, before step 2 fires. |
| 1 | Data maturity | ⚠️ Open item | How long has $95K held at ROAS 3.1? One good month isn't a baseline. |
| 2 | Marginal economics | 🔴 **FAIL — no data** | Only blended ROAS given. **documented/folklore note:** blended always trails marginal (Common Thread Collective) — the real question, "does the next $1 still make money," is unanswered. |
| 3 | Measurement health (5-area, 1–3 each) | 🟠 ~11/15, **estimated pending your confirmation** | GA4 (3) + platform dashboards (3) + assumed standard conversion tracking (2) + no unified blended dashboard (2) + no documented attribution/incrementality process (1). Clears the numeric floor but the **evidence bar is pure attribution** — see §2. |
| 4 | Creative supply | 🔴 **Likely the true binding ceiling** | See §4. |
| 5 | Business absorption (cash, inventory, fulfilment) | ⚠️ Open item — unanswered | A 3.16x spend increase means ~3x order volume. Nobody has confirmed the warehouse/fulfilment/cash float survives that. |
| 6 | Rollback pre-committed | 🔴 **FAIL under your plan** | "Raise 20%/week until we hit the number" has no down-move. Per this skill's failure-mode table, a scaling rule with no rollback trigger is the single most reliable marker of an unsafe plan. |

**Two gates fail outright (0 and 2).** The plan below is the *provisional* ramp — it runs using blended 3.1 as a stand-in floor (labeled **folklore/proxy**, not a real boundary) until finance supplies the real max-CAC. Do not let step 3 fire without gate 0 closed.

---

## 2. Evidence bar

**Current: attributed only** — platform reporting + GA4. No CRM/blended-revenue triangulation, no holdout, no incrementality study.

This matters specifically *because* the target is 3.16x current spend. Per this skill's pass threshold: **any ramp past ~2x current spend on purely attributed evidence needs a causal-measurement step, or an explicit board-acknowledged risk line.** Your target clears 2x at **~$190K**.

The two documented cases this skill exists to warn about — Meta/Google retargeting and branded search overstating incremental return — are exactly where blended ROAS 3.1 is most likely propped up. **research:** eBay's own experimental non-brand search test measured **–63% incremental ROI** against **+1,400% to +4,100%** from naive attribution (Blake, Nosko & Tadelis, *Econometrica*, 2015). **vendor data (Haus):** geo-holdout tests routinely show a "3x" attributed ROAS is closer to 1.8–2.2x incremental. Nobody's saying your 3.1 is fake — nobody knows, and that's the point.

**Plan includes:** a geo-holdout (or platform-native lift study) launched at the ~$150K tier, reading out before the $190K (2x) line, gating whether the ladder continues past it.

---

## 3. Approach — vertical ladder, with measure-first folded in, horizontal rejected for now

Default order for this skill: vertical ladder → measure-first → horizontal, then re-ranked against your inputs.

- **30-day penetration ~12%** sits well under the ~25% saturation band — real headroom remains on the existing audience. This **keeps vertical ladder as the base engine.**
- **Target is 3.16x current spend and evidence is attribution-only** — both conditions that this skill says should promote measure-first. It is **not promoted to lead**, because you have no live incrementality program today (instrumenting one from scratch costs a week you don't have before step 1). Instead it's **folded in as a gate**, not a leader: launched early, read out before the 2x line, and treated as a stop/go check rather than the thing that sets the target.
- **Horizontal expansion is rejected for now** — penetration is nowhere near the ~35% band that would force it, and your creative studio (10/month) can't currently feed a *second* set of new audiences without starving the primary line (see §4). If the creative ceiling ends up capping vertical velocity anyway, horizontal becomes the fallback — flagged, not deleted.

**Argument against this choice, stated out loud:** if the geo holdout comes back closer to eBay/Haus territory (1.8–2.2x incremental) than 3.1x attributed, the entire ladder above is oversized and should be re-cut to a lower target before the 2x gate, not after. That is the whole reason the holdout gates continuation instead of being a nice-to-have.

---

## 4. The real ceiling: creative, not budget

**folklore ratio (calibrate to this account):** proven, non-fatigued ad inventory ≈ monthly budget ÷ $5,000.

| Spend tier | Proven ads needed | You have / add |
|---|---|---|
| $95K (today) | ~19 | unknown starting count — **open item** |
| $190K (2x line) | ~38 | |
| $300K (target) | ~60 | studio ships **10 new creatives/month, total, across both platforms** — even at a generous 50% win rate, that's ~5 *proven* ads/month |

Getting from wherever you sit today to 60 proven ads at a net add rate of ~5/month, while old ads fatigue and roll off, is **the actual pace-setter here — slower than any budget mechanic in this memo.** This is very likely the first-binding ceiling, ahead of penetration and ahead of cash. **Open item, high priority:** confirm current proven-ad count per platform and the studio's real win rate; if it's below what's modeled, the Oct 31 date in §5 slips, full stop, regardless of what the auction lets you spend.

---

## 5. The ramp

Step size: no account change-history was given, so this uses the **concrete default (folklore): 15–20%/step, weekly cadence**, not the validate-then-push rung — you don't have a trusted causal target yet to push toward. **Recalibrate after step 3** once you have three real data points on how this account's efficiency responds.

| Step | Date | New budget | Δ | Hold until | Gate to advance |
|---|---|---|---|---|---|
| 0 | Sep 12–19 | *(no change)* | — | Sep 19 | **Gate 0 fix**: finance delivers margin → max-CAC / min-ROAS floor. No step 1 without this. |
| 1 | Sep 19 | $112K | +18% | Sep 26 | Marginal ROAS ≥ floor (proxy: 3.1 until gate 0 lands), frequency <3.0, delivery stable |
| 2 | Sep 26 | $132K | +18% | Oct 3 | Same, + launch geo holdout here |
| 3 | Oct 3 | $156K | +18% | Oct 10 | Same, + **recalibrate step size from steps 1–2's actual response** |
| — | **Sep 30 board checkpoint** | **~$150–165K interim run-rate** — report this against the original date, honestly | | | |
| 4 | Oct 10 | $184K | +18% | Oct 17 | Same + creative count check (≥30 proven) |
| **2x gate** | Oct ~17 | **$190K** | — | — | **Holdout readout required before advancing.** Incremental ≈ attributed → continue. Incremental materially lower → re-cut target, don't advance blind. |
| 5 | Oct 17 | $217K | +18% | Oct 24 | Marginal floor holds |
| 6 | Oct 24 | $256K | +18% | Oct 31 | Marginal floor holds, creative ≥50 proven |
| 7 | Oct 31 | $300K | +17% | Oct 31 | Target |

All edits batched once per week per platform — **documented:** platforms flag grouped changes as minimizing cumulative relearning versus drip-feeding several edits across the week.

**Rollback (practitioner convention, pre-committed now):**
- Marginal ROAS below the floor for a **full hold period** (not one bad day) → revert to prior step, hold 2 weeks flat, resume at +10%/week.
- Cost per acquisition >1.5x target after a step → cut 20–30%, stabilize 2 weeks, resume at +10%/week.
- **Before acting on either trigger**, check: sample size, GA4/platform tracking outages, seasonality, any concurrent test — a bad number on low volume with 5–7 days of purchase lag is noise, not a signal.
- **Instant cut** reserved only for: runaway spend past a hard cap, policy/legal exposure, broken checkout, confirmed tracking corruption.

---

## 6. Ceilings — checked cheapest-first

1. **Creative supply** — 🔴 likely binds first (§4). Near-zero-effort check, do it this week.
2. **Cash / working capital** — ⚠️ open item, unconfirmed. 3.16x spend means ~3x order volume; confirm fulfilment and payment-terms float survive it.
3. **Audience saturation** — 🟢 clear. 12% penetration is well under the ~25% band; doubling budget grows penetration ~50–70%, not 100%, so this alone won't bind before $300K.
4. **Marginal stop signal** — ⚠️ can't be checked at all until gate 0/2 are fixed. This is the ceiling most likely to be silently breached if the plan runs on blended numbers alone.

---

## 7. Exit condition

Ramp stops, permanently or pending replan, on the **first** of:
- $300K/month reached and holding through one full cycle, **or**
- Marginal contribution margin crosses ≤$0 on a spend band (even if blended still looks fine — blended always trails marginal), **or**
- Geo-holdout readout shows incremental return materially below the attributed 3.1 (eBay/Haus territory) — target gets re-cut, not abandoned silently, **or**
- Proven-ad inventory can't keep pace with the tier (§4) — ramp pauses at the creative-supported tier until supply catches up.

---

## 8. Open items — need answers before this becomes final

1. **Margin / max-CAC or min-ROAS floor** (gate 0 — blocking, needed this week).
2. Current proven, non-fatigued ad count per platform, and the studio's actual test-to-proven win rate.
3. Marginal ROAS on the last incremental spend band (not blended) — even a rough estimate.
4. Cash float and fulfilment/inventory capacity at ~3x order volume.
5. Whether "end of Q3" is a hard calendar commitment (Sep 30) or a trajectory reviewed at a board meeting — this single answer changes the entire shape of the plan.
6. Meta vs. Google split of the ramp — this plan treats them as one blended line; if per-platform penetration or marginal ROAS diverge, they should ramp on separate schedules.

---

## 9. What this replaces

Your original plan — 20%/week, both accounts, until the number hits — fails on five separate counts this skill checks for: no readiness gates, no marginal read (blended-only), no rollback trigger, no ceiling/exit condition, and a folklore step-size rule treated as platform law. It would also, per §0, arithmetically fail to hit the Sep 30 date anyway. This plan keeps the same weekly cadence you already wanted — it just adds the gate, the hold, the rollback, and the checkpoint that turn it from a budget edit into something the board can actually approve and you can audit afterward.

**Approval needed on:** the Sep 30 reframe (§0), the gate-0 deadline (this week), and the Oct 17 holdout gate before any step past $190K.