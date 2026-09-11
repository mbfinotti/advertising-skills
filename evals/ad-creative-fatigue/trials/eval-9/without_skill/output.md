# Fernwald Outfitters — Meta Advantage+ Creative Refresh Roadmap

## 0. Challenge the brief first

⚠️ "Replace all 28 next month" treats symptom (visible ad count) as if it were the diagnosis. Two problems with a blind swap:

- **No counterfactual.** If CPA drops after a full swap, you can't tell whether it was the creative, seasonality, iOS/attribution noise, or competitive CPMs shifting. You'll repeat the same panic next quarter.
- **Advantage+ learning reset.** Swapping 100% of creative at once forces the whole campaign back into learning phase simultaneously — CPA usually spikes *further* for 1–2 weeks before it improves.

🎯 Recommendation: **refresh all 28, but in waves with one held-out control concept**, not a single big-bang swap. This still hits "all replaced within a month" while protecting signal.

## 1. Diagnose before building (Days 1–3)

Pull the per-creative-per-day export and roll it up to the 6 concepts (spend-weighted). For each concept, trend by day:

- Frequency (fatigue proxy #1 — rising frequency + falling CTR = real fatigue)
- CPM (rules out "it's just gotten more expensive to buy this audience")
- CTR / outbound CTR
- Hook rate (3s video views ÷ impressions) and hold rate, if video
- CPA and spend share (Advantage+ often concentrates >70% of budget on 1–2 winners — check if the CPA rise is driven by those winners fatiguing, or by budget spilling into weak ads)

Classify each of the 6 concepts:

| Tier | Signal | Action |
|---|---|---|
| 🟢 Keep-live | Frequency flat/low, CTR stable, carries most spend | Do NOT touch yet — becomes the control |
| 🟠 Fatigued winner | Rising frequency, falling CTR, still gets spend | Refresh first — highest CPA impact |
| 🔴 Dead weight | Low spend share, poor CTR from day 1 | Kill immediately, don't bother refreshing |

Expect roughly 1 concept in 🟢, 3–4 in 🟠, 1–2 in 🔴 — confirm with your actual numbers.

## 2. Roadmap structure (4 weeks)

**Week 1 — Diagnose + brief**
- Finish the tiering above (Days 1–3).
- Kill 🔴 concepts' ads immediately — frees budget, no downside.
- Brief new concepts (see §3). Production starts.

**Week 2 — Wave 1 launch**
- Launch new creative for the 🟠 (fatigued winner) concepts only — call it ~12–14 assets.
- Keep the 🟢 concept's ads untouched and live as control.
- Cap Wave 1 at a soft budget or use CBO minimums so Advantage+ doesn't dump 80% of spend into one new asset before it has signal.

**Week 3 — Gate + Wave 2**
- Day 5–7 of Wave 1: check CTR, hook rate, CPA vs. the concepts they replaced. Graduate winners to full budget; kill anything below threshold (e.g., CPA >20% worse than the concept it replaced after ≥$X spend or ≥3 days).
- Launch Wave 2: refresh the 🟢 control concept last, plus any replacements still needed for killed 🔴 concepts — remaining ~14–16 assets.

**Week 4 — Full coverage + read**
- All 28 replaced. Compare blended CPA trend against baseline, isolating the effect of Wave 1 (already has 2 weeks of clean data by now) from Wave 2 (still fresh).
- Decide keep/kill on Wave 2 the same way.

## 3. What to actually brief (concept mix, not just re-skins)

Don't reshoot the same 6 concepts with new colors — that reproduces fatigue on a delay. Split new production:

- **60% iterate on what worked** (the 🟢 and best-performing 🟠 concepts): new hooks, new opening 3 seconds, new UGC talent/voice, new offer framing. Same proven angle, new execution.
- **40% net-new angles**: different value prop entirely (e.g., if current 6 concepts are all product-demo, add a problem/solution or social-proof/review-style angle, a founder-story angle, a comparison angle).

Target **8–10 concepts total** (not 6) replacing the current 28, with 3–4 format variants each (1:1, 4:5, 9:16; static + at least 2 video) for Advantage+ placement flexibility ≈ 30 assets.

## 4. Guardrails to set before launch

- **Naming convention** for the per-creative-per-day export: `concept_variant_format_launchdate` so Wave 1 vs Wave 2 and concept-level rollups stay analyzable — this is the only way the daily export stays usable once you're juggling waves.
- **Kill threshold** written down in advance (e.g., CPA >20% above account average after $150 spend, or CTR <50% of account median after 3 days) — removes the "gut feel" fights later.
- **Frequency ceiling** (e.g., 2.5–3 depending on funnel length) as an early-warning trigger for the *next* refresh, so you're not back here in another 3-week fatigue spiral.

## 5. After this refresh: stop doing big-bang refreshes

The root cause of "22% CPA spike, panic, replace everything" is that creative was iterated in one big batch, so it all fatigues on the same clock. Going forward:

- Move to a **rolling refresh**: replace ~20–25% of active creative every 2 weeks instead of ~100% once a quarter.
- Stand up a lightweight weekly check (frequency + CTR trend per concept from the same daily export) so fatigue is caught at the 🟠 stage, not discovered as a 3-week CPA trend.

**Bottom line:** kill the dead weight now, refresh the fatigued winners in Wave 1, hold the best concept as a control until Wave 2, and land at 8–10 sharper concepts (not just 6 reskinned) by week 4 — with kill/graduate thresholds set before launch so the rollout doesn't just recreate the same fatigue cycle in Q4.