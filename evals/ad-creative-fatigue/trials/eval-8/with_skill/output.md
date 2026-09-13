## No — don't force it. This reads as wear-in, not fatigue, and your agency's policy is the exact failure mode this diagnosis exists to catch.

**Why:** a calendar-triggered rotation ("every ad wears out every 4 weeks, no exceptions") is a universal threshold applied without reading the account's own signals. Fatigue is diagnosed from decay in the creative's own leading indicators — and yours are moving the opposite direction. View rate and aided recall improving together, over multiple weeks, is close to the textbook definition of **wear-in**: performance strengthening with repeated exposure, a real and separate effect from fatigue (Les Binet), documented specifically for brand-objective campaigns. Meta's 2023 research found _no_ wear-in effect for direct-response — but you're explicitly optimizing for lift and view metrics, not conversions, so that caveat doesn't disqualify your read; it's the case where wear-in is the legitimate call.

Frequency is the one number your agency is leaning on, and it's the wrong one to lean on. In this method frequency is a **lagging, confirming signal only** — it's measured at ad/ad-set level while fatigue happens at creative level, and it's a period average, not the marginal effect of the next impression. A creative at frequency 4.1 can be perfectly healthy; the rule here is explicit: _do not build the call on frequency._ 4.1 also isn't extreme for a brand-awareness buy spanning YouTube + Meta unless it's concentrated in a narrow warm segment — worth splitting cold vs. warm before treating it as a red flag at all.

```
FATIGUE VERDICT - Aurelia Waters 60s brand film, 2026-09-12
platform      : YouTube + Meta | funnel stage: brand awareness (not split cold/warm - recommend doing so)
window        : Weeks 1-8 running, trend read (exact baseline windows not supplied)
volume        : not supplied - spend/impressions/reach needed to firm this up

signals
  view rate         : improving, sustained            [leading]
  aided recall (lift): improving, sustained            [leading, survey-based]
  frequency          : 4.1, rising                     [lagging, confirming only]

confounder screen
  budget/bid change        : not screened - no change history supplied
  learning-phase reset     : not screened - no last-edit date supplied
  audience saturation      : pass, provisionally - saturation degrades view rate and recall
                             together with reach flattening; both are IMPROVING, the opposite
                             pattern, so saturation doesn't fit what's reported
  auction CPM inflation    : n/a to this call - awareness objective, not cost-per-result
  seasonality/window mix   : not screened - window composition not supplied
  tracking breakage        : pass, provisionally - survey-based recall isn't pixel-dependent
  attribution-window skew  : n/a - not a conversion-attributed metric
  placement/device mix     : not screened
  statistical noise        : not screened - recall survey sample size/CI not supplied
  landing page/offer change: n/a - awareness objective, no funnel step in question
  sibling-mix shift        : not screened - creative count/rotation history not supplied

confidence    : medium - two leading signals (one platform, one survey) moving the same
                direction across multiple weeks is real evidence, but noise bands, reach
                trend, and change history weren't supplied to fully clear the gate
verdict       : wear-in (brand objective - Meta's "no wear-in" finding applies to DR, not here)
action        : leave it running; do not rotate on the frequency number
ruled out     : rotation (agency's mandatory rung) - ruled out by evidence, not by capacity:
                nothing in the data says this ad is spent, and forcing it would trade a
                still-improving asset for an unproven one
expected      : view rate and recall continue holding or improving on the same audience;
                if that reverses, re-open the case
re-check      : ~4 weeks out (2026-10-10) - re-pull view rate, recall, and reach trend,
                split cold vs. warm frequency before that read
```

**What would actually change this call:**

- View rate or recall flattening or reversing over the next comparison window.
- Reach flattening while impressions keep climbing (early saturation) — different problem, different fix (audience expansion, not rotation).
- Frequency concentrated in a narrow warm/repeat-viewer segment rather than spread across a growing cold pool.

**What to do instead of forcing rotation:**

- Keep the film live — pulling a still-strengthening asset burns a working brand vehicle for no evidence-backed reason.
- If you want a hedge against the agency's discomfort, stage a challenger concept in parallel (rung 2/7 territory) without retiring the incumbent — test it against the same audience rather than swap it in.
- Push back on the "every ad wears out every 4 weeks" policy itself: replace it with a data-triggered rotation rule (two-plus leading signals decaying, two-plus consecutive periods, on the creative's own baseline) so future calls aren't made off a calendar.
- To sharpen this from "medium" to "high" confidence: get the recall survey's sample size/confidence interval, split frequency cold vs. warm, and confirm reach is still growing (not just impressions) — that closes the saturation question definitively.
