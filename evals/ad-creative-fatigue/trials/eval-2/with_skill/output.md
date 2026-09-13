# Fatigue call: Brightfern cold-prospecting video

**Short answer: don't pause it tomorrow morning on this data.** What you've described doesn't clear this skill's Confidence Gate, and the one signal you're leaning on — frequency 3.4 — is explicitly the least trustworthy input for this decision. Below is the full verdict, then what I'd do instead.

## Why frequency 3.0 isn't the trigger you think it is

That "kill at 3.0" number is folklore, not a platform rule — Ben Heath's own drop-off range for cold Meta traffic is 2.0–2.5, other sources say 2.5–3.0, none of it is Meta-sourced. More importantly, frequency is a **lagging, confirming** signal only: it's reported at ad-set level while fatigue happens per-creative, and it's a period average, not the marginal effect of the next impression. A creative at 3.4 can be perfectly healthy while a sibling at 5.0 is spent. Acting on frequency alone is the #1 failure mode this method exists to prevent.

## What your actual response signals say

- **Link CTR: 1.24% vs 1.21% trailing month → +2.5%.** That's _up_, not decaying. The leading signal that should move first in true fatigue hasn't moved against it.
- **CVR: 3.1% vs 3.2% → -3%.** Directionally flat; almost certainly inside noise, though I can't confirm without your impression/click volume.
- **CPA: +~4%.** Modest, and fully explainable by normal auction movement (CPM drift) given CTR and CVR are essentially flat — this is not the "costs rise while CVR holds and CTR falls" fatigue signature.

A real fatigue read needs **two-plus signals moving together, in the same direction, across two-plus consecutive periods**, against the creative's own baseline. You have one period (this week vs. a trailing-month blend) and the two signals you do have are contradicting a decay story, not confirming one.

## Fatigue Verdict

```
FATIGUE VERDICT - Brightfern cold-prospecting video, 2026-09-12
platform      : Meta | funnel stage: cold prospecting
window        : this week vs trailing-30-day blend (not day-matched, single period)
volume        : not provided - impressions/spend/conversions needed to run the noise check

signals
  link CTR    : 1.24% vs 1.21% (+2.5%)    [leading]   - moving the WRONG way for fatigue
  CVR         : 3.1% vs 3.2% (-3%)        [lagging]   - likely noise, unconfirmed
  CPA         : +~4%                      [lagging]   - consistent with normal CPM drift
  frequency   : 3.4                       [lagging]   - not causal; ad-set-level average
  hook rate   : not provided              [leading]   - MISSING - critical on video
  hold rate   : not provided              [leading]   - MISSING
  first-time impression ratio : not provided [leading] - MISSING
  CPM trend   : not provided                          - needed to separate auction vs. creative

confounder screen
  budget/bid change        : unknown - need change history
  learning-phase reset     : unknown - need last-edit date on the ad/ad set
  audience saturation      : unknown - need first-time impression ratio + reach trend
  auction CPM inflation    : unknown - need CPM vs. account's other ad sets
  seasonality/window mix   : unknown - "this week vs trailing month" isn't day-matched
  tracking breakage        : unknown - platform-to-order reconciliation not checked
  attribution-window skew  : unknown - most recent days of "this week" are attribution-immature
  placement/device mix     : unknown
  statistical noise        : cannot compute - no impression/click volume supplied
  landing page/offer change: unknown
  sibling-mix shift        : unknown - how many other creatives in this ad set, any recent adds?

confidence    : low - single period, no leading video signal (hook/hold rate), noise check
                un-runnable without volume, and the one clean signal (CTR) contradicts decay
verdict       : insufficient data, leaning healthy - do not call this fatigued
action        : do NOT pause. Launch the new video as a NEW ad ID alongside the current one
                (rung 2/rotate posture), splitting a modest amount of budget to it rather than
                replacing the incumbent. This is cheap, reversible same-day, and doubles as
                the discriminating test (Meta: recovery on the same audience = fatigue signal;
                no lift = the incumbent probably wasn't the problem).
ruled out     : pause (rung 8) - no verdict supports retiring a producer whose CTR is flat-to-up
                and whose CPA move is small enough to be auction noise, on a threshold this
                skill treats as folklore.
expected      : within the next full comparison window you'll have hook rate, first-time
                impression ratio, and a real two-period read - enough to actually clear the gate
                either way, plus real performance data on the new video.
re-check      : 2026-09-19 (one week out - your video runs fast on cold traffic, so this is a
                tight window, not the usual 14/30-day one)
```

## What to do tomorrow morning, concretely

1. **Don't pause the running video.** It's not showing you a fatigue signature — CTR is up, CVR is flat, CPA's move is small.
2. **Launch the new video as a separate ad ID in the same ad set, same audience**, at a modest starting spend split (e.g. 20–30%). Don't edit the live ad to swap creative — that resets learning and destroys your baseline mid-read.
3. **Pull before you decide anything else:** hook rate / hold rate trend on the current video (this is the one signal most likely to actually explain a video creative's wear, and you don't have it yet), first-time impression ratio, CPM trend vs. the rest of the account, and last-edit/budget-change date on this ad set.
4. **Check if Meta's own "Creative fatigue" / "Creative limited" delivery status is firing** on this ad — if it is, that's a backstop confirming signal (though by the time it fires you're already late).
5. **Re-check in ~1 week** with a real two-period, day-matched comparison. If hook rate has decayed while hold rate held, that's a hook-swap problem, not a full-creative-replacement problem, and would change what you ship next.

If it turns out the new video _does_ outperform on the same audience, you've validated the swap with real data instead of a frequency number, and you can retire the old one without wondering later if you killed a healthy ad. Producing the replacement asset itself is outside this skill — that's `ad-copy-variants` / `ugc-ad-scripts` territory — but you already have that in hand, which is exactly why the "run it as a challenger, not a replacement" move costs you nothing.
