# Fatigue Read: before-after-hero-v2 (Lumo Home, Meta)

## Short answer

**Don't confirm the fatigue read, and don't brief the two UGC replacements today.** This pattern — CTR down ~14%, CPA up ~33%, frequency up, onset within days of a single-step budget jump, and **all three creatives in the ad set degrading together** — is the textbook signature of a budget-scale confounder, not creative wear-out. Lockstep decline across every creative in the ad set is the single strongest tell here: true fatigue is creature-specific; a scale/learning shock hits the whole ad set at once, which is exactly what you're describing.

I ran this through the fatigue-vs-confounder workflow below. Treat the verdict as provisional — I'm working from the aggregate numbers in your message, not a full per-creative-per-day export, so I've flagged what would tighten it.

## Assumptions taken (confirm or correct these)

Interview items you didn't specify, assumed for this pass:
- **Funnel stage**: cold prospecting (typical for a DTC "hero" acquisition ad) — confirm; if this is retargeting, the frequency reading changes completely.
- **Data granularity**: only aggregate before/after numbers, not per-creative-per-day — weakens the noise-band math below to an estimate.
- **CPA/CTR figures**: read as the hero creative's own numbers, not ad-set blended.
- **No creative edits** to the hero ad itself in this window (only the budget step) — confirm nothing else changed same day.

## Baseline

- Hero creative: 5 weeks of strong, stable performance before the budget step (~Jul 21 – Aug 31, 2026).
- Budget step: $600/day → $1,050/day (+75%), single step, 2026-09-01 (11 days ago).
- Comparison window: 2026-09-01 → 2026-09-12 (today), vs the pre-step baseline.

## Noise check (estimated — confirm with real export)

Back-of-envelope from spend and stated rates: ~$11,550 spent in the comparison window at $1,050/day; at a ~3% CVR (typical DTC range) and 1.19% CTR, that implies roughly 700-750k impressions in-window. At that volume, the baseline CTR's noise band (1.38% ± 2×√(p(1-p)/n)) is roughly **1.35%–1.41%**. Observed 1.19% sits well outside it — this is a real decline, not noise. But this estimate substitutes for actual impression counts; pull the real number to close the gate formally.

## Confounder screen

```
budget/bid change        : FAIL - ad-set budget +75% in one step, Sep 01; decline onset
                            same day; all 3 sibling creatives degraded together, which is
                            an ad-set-level signature, not a creature-specific one
learning-phase reset      : FAIL - a 75% single-step increase exceeds normal daily-budget
                            tolerance and is a significant edit; delivery is volatile for
                            ~7 days post-edit per Meta's own guidance; 11 days in, you're
                            barely past that window, not into a clean re-stabilized read
audience saturation       : insufficient data - need first-time-impression-ratio and reach
                            trend to check; not needed to reach a verdict here since #1
                            already explains the pattern
auction CPM inflation     : insufficient data - need CPM trend vs account average
seasonality/window mix    : pass, assuming no holiday/promo skew in this window (confirm)
tracking breakage         : insufficient data - no reason to suspect it from what's given
attribution-window skew   : partial - last 2-3 days of the 11-day window aren't lag-mature;
                            CPA is somewhat overstated at the margin
placement/device mix      : insufficient data - worth checking; budget scale-ups often push
                            more spend into Audience Network / lower-CTR placements
statistical noise         : pass (estimated) - delta likely outside the noise band, but
                            confirm with real impression counts
landing page/offer change : pass, assuming no site/offer change in this window (confirm)
sibling-mix shift         : pass - no creatives added/removed; the lockstep decline across
                            the existing 3 is itself evidence for #1, not a mix artifact
```

Budget/bid change and learning-phase reset both **FAIL** and fully explain the observed pattern on their own. Per the skill's rule, any confounder fail that explains the decline ends the fatigue inquiry right there — the screen doesn't need to run to exhaustion once the cause is found.

## Verdict

```
FATIGUE VERDICT - before-after-hero-v2, 2026-09-12
platform      : Meta | funnel stage: cold prospecting (assumed - confirm)
window        : Sep 01-12 (11 days) vs baseline Jul 21-Aug 31 (trailing 5-week)
volume        : ~$11,550 spent in window (ad set, $1,050/day); conversions/impressions
                estimated, not confirmed - pull the real export

signals
  link CTR    : 1.19% vs 1.38% (-14%)   [leading]
  frequency   : 2.6 vs 1.8              [lagging]
  CVR         : not provided - pull this; it's the key separator
  CPA         : $44 vs $33 (+33%)       [lagging]

confidence    : medium - the qualitative pattern (onset-at-edit, whole-ad-set lockstep,
                magnitude matching a known scale-effect signature) is strong enough to act
                on, but the noise-band and CVR numbers are estimated, not pulled from a
                real export
verdict       : confounded (budget scale-up + learning-phase reset), NOT fatigued
action        : no refresh. Do not brief new creative off this data. Re-baseline the ad
                set at the new $1,050/day spend level starting from stabilization
                (~Sep 08), then judge future decay against THAT baseline, not the
                pre-scale peak.
ruled out     : n/a - a confounded verdict acts on the cause, not the Action Ladder;
                nothing was deleted from it
expected      : CTR/CPA settle at a new, slightly worse-than-peak level once learning
                restabilizes (some efficiency loss at 1.75x spend is the normal cost of
                scale, not decay); if decline continues past that on a clean window, the
                fatigue case reopens
re-check      : 2026-09-22 (14-day clean window starting after Sep 08 stabilization)
```

## What to actually do today

1. **Kill the brief, or at minimum pause it.** Commissioning two UGC videos now would burn production capacity, reset learning again on launch, and then "confirm" fatigue when metrics settle back down for reasons that have nothing to do with new creative — the exact trap this pattern is known for.
2. **If you need a same-day, reversible move to show movement**: step the ad-set budget back down (e.g. to ~$800/day) rather than holding at the full +75% jump, or hold flat and stop touching it. That's zero-cost, reversible, and targets the actual cause instead of the symptom. Pacing/scaling mechanics for how to re-scale properly are outside this skill's scope — that's a `paid-media-scaling` / `ad-budget-pacing` call.
3. **Don't edit the three live creatives.** Editing a creature you're trying to measure destroys the baseline mid-read.
4. **Pull the real export** (per-creative-per-day CTR, CVR, impressions, CPM, first-time-impression ratio, negative-feedback rate) so the noise check and CVR-stability check stop being estimates.
5. **Re-check 2026-09-22** on a clean 14-day window post-stabilization. If CTR/CPA are still degraded at that point *and* CVR has held stable while frequency keeps climbing, that's when a real fatigue case opens — and at that point, hook-swap on the hero ad (not a full new UGC concept) is the first rung to reach for, since a single tired hook is cheaper to fix and faster to ship than two ground-up videos.

## What to tell your growth lead

"The timing lines up with the budget increase, not five-week wear-out — all three creatives in the set dropped together the same day we scaled spend 75% in one step, which is a scale/learning-phase signature, not creative-specific decay. I want to re-baseline at the new spend level and re-check in ~10 days before we commit production time to two new videos. If the hero ad is still declining on a clean window at that point, I'll brief a hook-swap on it first, since that's a faster, cheaper test than two new concepts — and we hold the UGC brief in reserve if the swap doesn't recover it."