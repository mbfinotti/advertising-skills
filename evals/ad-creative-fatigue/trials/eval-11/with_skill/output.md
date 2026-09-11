# Green-light: No.

**Verdict: `confounded` — auction CPM inflation (Q4 seasonal), not creative fatigue.** The data you've given is close to a textbook version of the confounder screen's #4 case, and it fails the fatigue signature on the one signal that's supposed to lead: link CTR isn't declining, it's flat-to-up (1.35% vs 1.33% baseline, +1.5% relative). Fatigue requires at least two signals decaying together, with CTR usually first. You have exactly one signal moving — CPA — and it's fully lagging and fully explained by CPM.

The arithmetic backs this up: CPA ≈ CPM / (CTR × CVR). With CPM +24%, CTR flat, CVR flat, pure auction-price math predicts CPA up ~22%. You're seeing +28% — close enough that the residual is more likely attribution-window skew on a trailing 3-week window (recent days under-report conversions) than any creative effect. There's no CTR decay to pin the gap on the ad.

And the timing writes its own explanation: mid-November is exactly when Q4 holiday-auction pressure hits — every advertiser in a gifting category (jewelry is a peak BF/CM vertical) is bidding up the same inventory at once. That's the auction getting more expensive, not your creative wearing out.

```
FATIGUE VERDICT - Glintwork Meta prospecting video, 2026-11-13
platform      : Meta | funnel stage: cold prospecting
window        : last 3 weeks (~Oct 24-Nov 13) vs prior trailing baseline
volume        : not provided - required before this can fully clear the confidence gate

signals
  link CTR      : 1.35% vs 1.33% (+1.5%, i.e. IMPROVED, not declined)   [leading]
  CVR           : flat                                                  [lagging]
  CPM           : +24%                                                  [leading, ambiguous]
  CPA           : +28% (~matches CPM-driven prediction of ~+22%)        [lagging]
  frequency     : not provided                                          [lagging]

confounder screen
  budget/bid change        : UNKNOWN - pull change log; confirm nothing changed on this ad set
  learning-phase reset     : UNKNOWN - confirm last significant edit date is outside the window
  audience saturation      : pass (tentative) - CVR flat + CTR not falling is the wrong
                              signature for saturation (which degrades CVR alongside CTR);
                              confirm with first-time-impression ratio / reach trend if available
  auction CPM inflation    : FAIL - CPM up 24% while CTR holds/improves is the exact telltale;
                              confirm by comparing this ad set's CPM trend against the account's
                              other ad sets/campaigns over the same 3 weeks (should move together)
  seasonality/window mix   : FAIL (same event as above) - mid-Nov holiday auction ramp,
                              consistent with a jewelry/gifting vertical
  tracking breakage        : pass (tentative) - CVR flat implies conversions are still
                              reconciling; confirm platform-vs-order-system ratio is stable
  attribution-window skew  : PARTIAL - most recent days of a 3-week trailing window aren't
                              lag-mature yet; likely inflates the CPA delta slightly
  placement/device mix     : UNKNOWN - not provided
  statistical noise        : the CTR "decline" doesn't exist - it's a small increase, so this
                              confounder is moot for CTR; CPA/CPM deltas need impression/spend
                              volume to noise-check formally (not provided)
  landing page/offer change: pass (tentative) - CVR flat argues against a funnel break;
                              confirm no BF-prep page/offer changes landed in this window
  sibling-mix shift         : UNKNOWN - confirm no creatives added/removed in the ad set recently

confidence    : medium-high on the confounded call (CPM-up/CTR-flat is the specific pattern
                this skill exists to catch, reinforced by calendar timing), but NOT high enough
                to call this fully closed - budget/bid history, FTIR/reach, and spend/impression
                volume weren't supplied. None of the gaps point back toward fatigue; they only
                affect how tightly "confounded" is nailed down vs "insufficient data."
verdict       : confounded (auction CPM inflation / Q4 seasonality) - NOT fatigued
action        : no refresh. Re-baseline expected efficiency at the new Q4 CPM level; treat
                this as a bid/budget-pacing question for the holiday auction, not a creative
                question. Hand to mbfinotti/advertising-skills@ad-budget-pacing and
                @paid-media-scaling for how to pace spend/bids through BF/CM.
ruled out     : entire Action Ladder - a `confounded` verdict doesn't enter it. Specifically:
                do not touch the live ad. Editing or replacing a 9-week creative resets Meta's
                learning phase, and a reset landing during Black Friday week is the single
                worst timing available - you'd be manufacturing the volatility everyone would
                then blame on "fatigue."
expected      : CPA settles at a new, moderately-higher plateau that tracks the account's
                broader Q4 CPM trend, not this ad specifically. If CTR ever genuinely starts
                falling on a lag-mature window, reopen the fatigue case then - the evidence for
                it doesn't exist yet.
re-check      : confirm the open items (budget/bid log, FTIR/reach, CPM vs. other ad sets)
                within the next few days: cheap checks, no production cost. Formal re-check
                on a lag-mature window after Cyber Monday closes (~Dec 4, 2026).
```

**On the team's plan specifically:** don't spend the two highest-value weeks of the year producing new creative for a problem the numbers say isn't there. If leadership wants insurance, stage one challenger asset *alongside* the current ad (never edit it) so you have something ready if real decay shows up post-BF — but that's a hedge, not this week's emergency, and it shouldn't come out of the same lead time you'd need for actual Black Friday assets.

If you can pull the missing pieces (change log, spend/impression volume, FTIR or reach trend, CPM broken out by ad set), send them over and I'll tighten the confidence line and close the loop properly — but nothing in what's missing looks likely to flip this verdict, because the one signal that would have to move to support fatigue (CTR) is moving the wrong way.