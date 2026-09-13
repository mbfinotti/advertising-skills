# Fernwald Outfitters — Creative Refresh Roadmap (Meta Advantage+ Shopping)

## The headline call: don't replace all 28 next month. Replace by concept, on evidence, staggered.

A campaign-level CPA rising 22% over three weeks is one lagging, aggregate number. It cannot tell you whether 1 of 6 concepts is dying and dragging the average, whether all 6 are fatigued, or whether nothing creative is wrong at all. Before any production brief gets written, run the diagnosis this way — it changes both _what_ gets replaced and _how fast_.

---

## Why "refresh all 28 next month" is the wrong default here

1. **Wrong unit of analysis.** You have 6 concepts, not 28 independent assets. Campaign-average CPA hides which concepts are healthy — replacing all 28 spends production capacity on concepts that don't need it and tells you nothing about which ones actually broke.
2. **Advantage+ masks the signal you need.** Advantage+ shopping auto-rotates and silently shifts budget away from decaying assets. Reading campaign CPA instead of the per-asset breakdown is exactly the trap the skill flags — you have to read asset-level spend share and response metrics, not the campaign roll-up.
3. **No confounder screen has run yet.** A 22%/3-week move is equally consistent with: a budget or bid change, a learning-phase reset from any recent edit, fall-season auction CPM inflation (outdoor apparel enters its highest-intent season right now, mid-September), attribution-window skew, or tracking drift. Any one of these, confirmed, ends the fatigue inquiry — no creative fixes it.
4. **Relaunching all 28 simultaneously resets learning campaign-wide.** Advantage+ treats a mass creative swap as a significant edit. You'd tank delivery right when you're trying to prove the refresh worked, and you'd have no clean baseline left to measure the "fix" against.
5. **It skips cheaper rungs that may already fix most of the decay.** If 3 of 6 concepts show hook-rate decay with hold rate and CVR holding, that's a same-day hook swap, not a full rebuild — the Action Ladder puts hook swap and iteration well ahead of new-concept production in return per unit of effort.

---

## What's still needed before verdicts can be finalized

The prompt gives platform, campaign type, ad/concept count, and a 3-week CPA trend — enough to route the plan, not enough to issue a verdict yet. Before Phase 1 below runs, get:

| Missing input                                                                                                  | Why it matters                                                                                        |
| -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Funnel stage (cold prospecting vs retargeting) — Advantage+ shopping is usually broad/prospecting, but confirm | Tolerated exposure and the saturation read differ sharply by stage                                    |
| Daily spend & conversion volume per creative                                                                   | Decides whether the confidence gate can clear on CPA, or has to run on engagement signals only        |
| Change log: any budget, bid, audience, or optimization-event edits in the last 3 weeks, with exact dates       | Single biggest false-positive generator — a learning-phase reset alone can produce this exact pattern |
| Audience size / broad vs narrowed targeting                                                                    | Sets the saturation read (first-time impression ratio, reach trend)                                   |
| How many of the 28 sit in the same ad set, and whether any sibling was added/removed in-window                 | Sibling-mix shift can produce this same CPA move with zero creative decay                             |
| Target CPA/ROAS                                                                                                | Sets how far "22% up" actually is from the line that matters                                          |
| Effort ceiling: in-house editing capacity, brief lead time, who signs off                                      | Deletes rungs from the ladder — this is what makes "next month" realistic or not                      |
| B2C confirmed (assumed here — outdoor apparel D2C ecommerce)                                                   | Sets which signals carry the call; assumed correct, flag if wrong                                     |

Treat these as day-1 asks to your growth/media team — they cost nothing to pull and gate everything downstream.

---

## Phase 0 — Confounder screen at campaign level (this week, Sep 12–16)

Run before touching any creative. Any FAIL here ends the fatigue inquiry and redirects the fix — it does **not** greenlight a refresh.

| Confounder                | Check                                                                         | Priority given this case                                                                         |
| ------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Budget/bid change         | Overlay ad-set change history on the CPA series                               | Check first — cheapest, biggest false-positive source                                            |
| Learning-phase reset      | Last significant edit date on the campaign/ad sets                            | Advantage+ is edit-sensitive; check first                                                        |
| Sibling-mix shift         | Any of the 28 added/removed/resized in the window                             | Check first — free from the same change log                                                      |
| Seasonality / auction CPM | CPM trend vs account's other campaigns; fall apparel season starting now      | Outdoor apparel enters peak intent in Sept–Oct — real risk of CPM-driven cost rise with flat CTR |
| Audience saturation       | First-time-impression ratio, reach trend                                      | Advantage+ broad delivery can plateau reach without anyone noticing                              |
| Attribution-window skew   | Compare only lag-mature windows                                               | 3-week trailing window is exactly where this artifact shows up                                   |
| Tracking breakage         | Platform-reported conversions vs order system, ratio stability                | Standard check, low cost                                                                         |
| Landing page/offer        | Any site/offer change in the window; CVR from other traffic to the same pages | Rules creative in or out fast                                                                    |

If nothing fails here, proceed to Phase 1. If something fails, the fix targets that cause — not the creative — and this roadmap pauses on the affected scope.

---

## Phase 1 — Per-concept diagnosis (Sep 15–22)

1. Pull the per-creative-per-day export (you already have this granularity — it's the best case the method assumes).
2. Roll the 28 assets up to their 6 parent concepts. Compute each concept's own baseline: 3-day moving average vs its trailing 14-day baseline (or 7-day vs 30-day, whichever the export supports cleanly).
3. Read Advantage+ per-asset breakdown specifically — never the campaign roll-up — since the platform is already reallocating spend away from anything it's deprioritizing, which is itself a leading signal (spend-share loss) you'd otherwise miss.
4. For each concept, pull in this order: link CTR → hook rate/thumbstop → spend share within its ad set → first-time impression ratio → hold rate → CPM → CVR → frequency → CPA. Apply the noise check and require ≥2 signals, ≥1 leading, moving together across ≥2 periods before calling anything.
5. Issue one Fatigue Verdict block per concept (template below), not per individual ad. A concept with several fatigued creatives and one still-healthy one tells you the exhaustion is real; a concept where only the oldest asset decayed points at that asset, not the concept.

```
FATIGUE VERDICT - <concept name>, <date>
platform      : Meta Advantage+ shopping | funnel stage: <confirm>
window        : <comparison window> vs baseline <baseline definition>
volume        : <spend> spent, <impressions>, <conversions> in window

signals
  link CTR              : <current> vs <baseline> (<±x%>)   [leading]
  hook rate / thumbstop  : <current> vs <baseline> (<±x%>)   [leading]
  spend share (ad set)   : <current> vs <baseline>            [leading]
  first-time impr. ratio : <current> vs <baseline>            [leading]
  CVR                    : <current> vs <baseline>            [lagging]
  frequency               : <current> vs <baseline>           [lagging]
  CPA                    : <current> vs <baseline> (<±x%>)    [lagging]

confounder screen: pass/FAIL per Phase 0, re-checked at concept level
confidence    : high | medium | low
verdict       : fatigued | saturating | confounded | insufficient data | healthy | wear-in
action        : <Action Ladder rung>
ruled out     : <rungs deleted by capacity/deadline, with reason>
expected      : <what recovers, roughly how much>
re-check      : <date>
```

---

## Phase 2 — Route each concept by its own verdict, not by decree (Sep 22–26)

Once the 6 blocks are filled, sort concepts into buckets. Expect a mix — this is the point of doing it per concept instead of blanket-replacing:

- **Healthy** → leave running, no production spend, next scheduled review.
- **Hook-decayed only** (hook/thumbstop down, hold rate and CVR stable) → hook or thumbnail swap on the same body, shipped as a **new ad ID** if negative-feedback rate is elevated. Same-day-to-48h turnaround, no brief cycle.
- **Fully fatigued** (leading + lagging signals down together, CVR holding) → iterate the winner: same concept, new execution (hook, format, aspect ratio, copy). This is where most of the 28→fewer-but-fresher assets should come from; practitioner-reported recovery on iteration runs 60–80% of original performance, treat as directional.
- **Repeatedly iterated with no recovery** → the concept itself is spent. This is the only bucket that should get genuinely new-concept production — promote it above the efficiency default specifically because cheaper rungs already failed on it.
- **Saturating** (CVR degrading with engagement, flat/falling reach, first-time-impression ratio down) → do not commission creative at all. Audience expansion or exclusions is the fix; new creative here wastes production budget on a pool problem.
- **Confounded** → no refresh; fix the actual cause (budget/learning/seasonality/tracking) and re-baseline before judging creative again.

This is also where the head of growth's "all 28 replaced" mandate should get renegotiated to "6 concepts triaged, N replaced" — likely fewer new assets, shipped faster, with the ones that don't need replacing left alone to keep earning.

---

## Phase 3 — Staggered production & launch (Sep 26 – Oct 17)

- **Never edit a live ad to refresh it.** Launch every replacement as a new ad alongside the incumbent; pause the incumbent only once the replacement has ramped.
- **Stagger by concept**, don't drop all replacements the same day — a simultaneous mass swap resets Advantage+ learning across the whole campaign at once and destroys your ability to attribute recovery to any one change.
- **Keep still-profitable fatigued concepts running** while their replacements ramp — never pause a producer with nothing staged.
- Sequence production by effort: hook swaps ship first (days 1–3 of this phase), iterations next (production brief + days), any genuinely new concept last (full brief, longest lead time) — this is what makes "next month" achievable instead of a 28-asset pile-up in the last week.
- Route production briefs to `ad-copy-variants` / `ugc-ad-scripts` / `ad-creative-brief` per concept once the verdict and rung are set.

## Phase 4 — Ramp, re-check, scorecard (Oct 17 onward)

- Re-check each replaced concept one full comparison window after its individual launch date (not one shared date for all 6).
- Log per-concept: verdict, action taken, and outcome, building the refresh win-rate / false-positive scorecard — target ≥60% of refreshes beating the retired concept's pre-decline baseline, <20% false positives. If several concepts fail to recover post-refresh, stop and check the offer/landing page before touching creative again.
- Report back to the head of growth with the per-concept breakdown, not a single campaign-wide "refreshed" checkbox — this is the artifact that lets next quarter's decision start from evidence instead of a hunch.

---

**Bottom line for the head of growth:** the campaign-level 22% is a real signal worth acting on, but it's not yet a diagnosis. Two weeks of confounder screening and per-concept verdicts (Phases 0–1) either confirm a targeted refresh of the concepts that actually earned it, or catch a seasonality/learning-phase/budget cause that a full creative rebuild would not have fixed — either way, cheaper and faster than committing production capacity to all 28 up front.
