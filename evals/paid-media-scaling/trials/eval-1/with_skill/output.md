Quick correction before the schedule: there is no "official Facebook rule" here — that's worth fixing because it changes how aggressive you can safely be with a 4x jump.

## The "20% every 72 hours" claim, checked

- **Meta has never published a budget-change percentage.** Their documentation says significant edits *can* reset learning "depending on the magnitude of the change" — no number given. *(documented)*
- The 20%/72-hour figure traces to Charlie Lawrance, Social Media Examiner, Sept 2021 — a second-hand relay of unverified account-rep advice. *(folklore)*
- Two real things hardened it into a "rule": Meta's automated-rules UI has a preset literally called *"Increase budget by 20%"* — a default button, not a law *(documented)*. And Google really does document 20% cadence — but only for **bids on Display campaigns**, not budgets, not Meta *(documented)*.
- So "official rule, safe to $2,000/day" isn't a thing you can rely on. What *is* real: your own change history. You've already run this campaign through three step-ups (Jan +30%, Apr +15%, Jun +25%) and it's still healthy at $38 CPA — that's a far better basis for sizing the next steps than a folklore percentage, but I need the actual before/after CPA numbers from those three events to use it (see Open items). Until then I'm shipping the 15–20% concrete default, which is explicitly a placeholder to be recalibrated, not a final answer.

Also flagging: $500→$2,000/day is a **4x jump**, not the "just keep adding 20%" case people picture when they cite this rule. Crossing 2x on attributed-only evidence is exactly the point where this method requires either a causal check or an explicit acknowledged risk — built into the schedule below.

---

## MEDIA SCALING RAMP — Velora Skincare prospecting, $500 → $2,000/day over ~12 weeks (holiday push)

**Gates**
| Gate | Status | Note |
|---|---|---|
| 0. Affordability | PASS (assumed) | $55 max CPA treated as your already-approved boundary. Confirm it still holds for holiday AOV/margin mix (bundles, discounts often shift this). |
| 1. Data maturity | PASS | 8 weeks stable at flat spend clears learning + lag easily. |
| 2. Marginal economics | PROVISIONAL PASS | $38 vs $55 is currently blended = marginal (spend hasn't moved in 8 weeks). Need Jan/Apr/Jun before/after CPA to confirm the *marginal* band held under real step-ups, not just that it recovered. |
| 3. Measurement health | UNKNOWN | Not scored. Needed before scaling past step 2. |
| 4. Creative supply | UNKNOWN — likely binding | Folklore ratio: proven ads ≈ monthly budget ÷ $5,000. At $500/day (~$15K/mo) that's ~3 ads; at $2,000/day (~$61K/mo) that's ~12. How many proven, non-fatigued ads do you have running now, and what's your test throughput/month? |
| 5. Business absorption | UNKNOWN — likely binding | Skincare = physical inventory. Confirm stock can cover 4x volume through the holiday window, and that cash float covers the spend before revenue lands. |
| 6. Rollback pre-committed | set below | — |

**Gates 3–5 are unverified, not failed — but I'm capping the plan at Step 2 until you confirm them.** Steps 3+ are drafted but held pending that data, per the "a failed/unverified gate stops the ramp" rule rather than shipping the full ramp on faith.

**Evidence bar:** attributed (Meta-reported CPA) — not stated as triangulated against actual revenue/refunds. Upgrade planned: triangulate against store-level CAC before Step 4 (the 2x line), since attributed numbers are exactly where they most overstate — this reframes as attributed→triangulated by the point it matters, not full causal, because a geo-holdout at this spend/timeline is likely too slow for a holiday deadline.

**Approach:** Vertical ladder, default rung — you have real headroom evidence (stable CPA, no audience/penetration data given but no red flags either) and a hard date, which favors speed over instrumenting a holdout test. Measure-first isn't dropped, just demoted to a checkpoint at the 2x line rather than leading — flag this explicitly since the account is scaling 4x on attributed-only evidence, which the pass bar treats as a real risk, not a technicality. Horizontal expansion isn't ruled out, just not needed yet — no penetration/reach data was given, so it's an open item, not a deletion.

**Steps** *(15–20% default, hold 10 days pending your actual conversion-lag figure — using 10 as a conservative placeholder over Meta's ~7-day learning exit; tighten or extend once you confirm click-to-purchase lag)*

| Date | New budget | % change | Hold until | Monitor | Rollback trigger | Rollback action |
|---|---|---|---|---|---|---|
| 2026-09-12 | $500 (current) | — | — | baseline | — | — |
| 2026-09-22 | $600 | +20% | 2026-10-02 | CPA, freq, CPM, delivery status | CPA > $55 sustained through full hold | revert to $500, hold 2 wks, resume +10% |
| 2026-10-02 | $720 | +20% | 2026-10-12 | same | same | revert to $600, same protocol |
| **— gate check —** | | | | Confirm measurement score, creative count, inventory/cash before proceeding | | |
| 2026-10-12 | $864 | +20% | 2026-10-22 | same | same | revert to $720 |
| 2026-10-22 | $1,037 | +20% | 2026-11-01 | **+ triangulate against store CAC/revenue here — 2x line** | CPA > $55 sustained, or triangulated CAC disagrees materially with platform CPA | revert to $864, re-check triangulation before re-attempting |
| 2026-11-01 | $1,244 | +20% | 2026-11-11 | same, watch frequency/CPM trend | same | revert to $1,037 |
| 2026-11-11 | $1,493 | +20% | 2026-11-21 | same | same | revert to $1,244 |
| 2026-11-21 | $1,792 | +20% | **hold flat through 11/27–11/30 (Black Friday/Cyber Monday)** | same — expect CPM to rise market-wide, don't misread this as ramp failure | CPA > $55 *net of the seasonal CPM baseline* | revert to $1,493 |
| 2026-12-01 | $2,000 | +11.6% (trimmed) | ongoing | confirm at target | same | revert to $1,792 |

Deliberately parking a step over Black Friday/Cyber Monday rather than pushing into it — changing budget into the highest-CPM week of the year is how you'd misattribute normal seasonal cost spikes to a botched step.

**Rollback discipline (all steps):** Before acting on any trigger, check sample size, conversion lag, tracking/pixel outages, refund/return rate (skincare returns can quietly rot the real CAC), and whether the "spike" is just the market-wide holiday CPM rise rather than your step. Emergency instant cuts reserved for runaway spend, a broken landing page/checkout, or confirmed tracking corruption — not for one bad day of data.

**Ceilings:** Creative supply is the most likely first binder (unknown count vs. ~12 needed at target) — check this before Step 3. Cash/inventory absorption is the second-most-likely, given this is a holiday push for a physical product. Audience penetration/saturation can't be assessed — no reach or frequency-trend data given; treat as open item, not cleared.

**Exit condition:** $2,000/day reached by ~Dec 1, OR marginal CPA crosses $55 on a full-hold basis and doesn't recover after one rollback-and-retry, OR creative/inventory ceiling binds first and caps the ramp below target — whichever comes first gets reported, not silently absorbed into "just hold longer."

**Open items (need these before I'd sign off on Steps 3–8 as final, not just drafted):**
1. Actual CPA before/after for the Jan +30%, Apr +15%, Jun +25% changes — this is what upgrades the step size from folklore default to your own account's derived number.
2. Current count of proven, non-fatigued ads and monthly creative test throughput.
3. Measurement maturity score (blended dashboard / per-channel / conversion tracking / analytics / attribution process, 1-3 each).
4. Cash float and inventory capacity to cover 4x spend through the holiday sell-through window.
5. Actual click-to-purchase conversion lag (to replace the 10-day hold placeholder with a real number).
6. 30-day audience penetration / frequency trend, if you can pull it — needed to know if vertical stays viable all the way to $2,000/day or saturates first.

Send me #1 and I'll immediately recompute the step size off your own account's history instead of the 15-20% placeholder — that's the single highest-leverage number missing here.