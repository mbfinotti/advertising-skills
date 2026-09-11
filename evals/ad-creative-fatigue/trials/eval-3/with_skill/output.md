## Bottom line

This is **not** creative fatigue. The data you gave me fails the fatigue call on two independent grounds, and it matches one of this skill's known trap patterns almost exactly. Don't brief a new ad yet — there's a funnel/tracking problem to run down first, and it likely explains both the checkout release *and* the expired promo code you mentioned as an afterthought.

## Why fatigue doesn't fit

Fatigue's signature (per the skill's own decision rule) is **leading signals decaying while CVR holds** — link CTR and/or hook rate sliding down while conversion rate stays put, because the people who still click still buy. You have the exact inverse:

- Link CTR: steady (~1.4%) — leading signal, flat
- Hook rate: hasn't moved — leading signal, flat
- CVR: 3.2% → 1.1% (-66% relative) — lagging signal, collapsed

The skill's two-signal rule requires at least two signals moving together, one of them leading. You have **zero leading signals moving** — only one lagging signal. That alone disqualifies `fatigued` regardless of how big the CVR drop is. This exact pattern has its own row in the skill's failure-mode table: *"Reading CVR collapse with healthy CTR as fatigue → that pattern is landing page, offer, or tracking — no creative will fix it."*

Seven weeks old isn't diagnostic by itself — age is a plausible-sounding prior, not a signal.

## The two suspects you buried in the question

You mentioned the Sept 2 checkout release and the expired 20%-off code almost as an aside ("dev team says it was minor"). Both land right at the onset of the CVR collapse, and both are named confounders that produce **exactly this signature**:

1. **Landing page / offer change downstream of the ad** — telltale is "CTR and engagement healthy, CVR down... onset aligned to a site deploy or offer calendar. All traffic sources to that page degrade together, not just this creative." If your ad's hook/copy references or implies the 20%-off code (or the audience has learned to expect it), people still click at the same rate — the ad hasn't changed — but bail once the discount doesn't apply at checkout. That ties your two "minor" facts into one causal story.
2. **Tracking breakage** — a checkout release is the single most common trigger for a broken purchase event (pixel firing on the wrong step, a changed confirmation URL, a consent-mode shift). "Minor" from an engineering-scope perspective says nothing about whether the conversion tag still fires correctly. This would produce the identical signature — clicks fine, reported conversions gone — without real revenue actually falling as much as the dashboard shows.

These aren't mutually exclusive and you can tell them apart cheaply (below).

## Verdict block

```
FATIGUE VERDICT - Peakform top Meta ad, 2026-09-12
platform      : Meta | funnel stage: not specified - confirm cold vs warm before re-check
window        : ~Sep 02-12 (10 days) vs pre-Sep-02 baseline (~3.2% CVR steady state)
volume        : not provided - get daily clicks/conversions to formally clear the noise gate

signals
  link CTR      : ~1.4% vs baseline steady (no material change)   [leading]
  hook rate     : unmoved vs baseline                              [leading]
  CVR           : 1.1% vs 3.2% (-66%)                              [lagging]

confounder screen
  budget/bid change        : pass - none reported
  learning-phase reset     : pass - no creative/targeting edit reported on the ad itself
  audience saturation      : pass - would show CTR/hook decaying too; both flat
  auction CPM inflation    : pass - not implicated; CTR flat rules out the usual pairing
  seasonality/window mix   : needs check - confirm day-of-week-matched windows
  tracking breakage        : FAIL (suspected) - checkout release Sep 02 coincides exactly
                             with CVR collapse onset; reconcile platform-reported
                             conversions against orders/Shopify for the same window
  attribution-window skew  : needs check - last 2-3 days of the 10-day window aren't
                             lag-mature yet; don't over-read the most recent days alone
  placement/device mix     : pass - no reported shift
  statistical noise        : likely clears (see note) - confirm with actual click volume
  landing page/offer change: FAIL (suspected) - 20%-off code expired ~Sep 02, same onset;
                             check whether the ad copy/creative references the discount
  sibling-mix shift        : pass - not reported

confidence    : medium - the signature is unambiguous (1 lagging signal only, both
                leading signals flat, exact onset alignment to two dated events), but
                I'm working from your summary stats, not a day-level export, and click
                volume wasn't given so the noise gate isn't formally cleared yet
verdict       : confounded - landing-page/offer and/or tracking breakage, NOT fatigued
action        : do not commission a refresh yet - run the two checks below first
ruled out     : hook swap, rotate, budget shift, iterate, new concept - all Action
                Ladder rungs are creative fixes; none of them touch a funnel or
                tracking cause, so none apply until the confounder screen clears
expected      : if tracking is the cause, CVR should show a step-function jump back
                once the fix ships, not a gradual recovery; if it's the offer, CVR
                should recover only after the ad's message matches what checkout
                actually delivers
re-check      : 2-3 days after the diagnostic checks below, then a full window
                after whatever fix ships
```

Note on the noise gate: even at a fairly low volume — say 2,000 clicks in the comparison window — the noise band around a 3.2% baseline CVR is roughly 2.4%–4.0%. Your observed 1.1% sits nowhere near it. Unless this "top ad" is running on unusually thin volume, a 66% relative drop clears the noise check by a wide margin — I just can't sign off on the exact number without your click count.

## Two checks, do these before touching creative (hours, not days)

1. **Reconcile platform-reported conversions against your order system** (Shopify/whatever sits behind checkout) for Sep 2–12 vs the prior window. If the ratio of platform-reported to actual orders has shifted, that's tracking breakage from the checkout release — full stop, fix the tag/event, no creative work needed. "Minor" release notes don't clear this; ask specifically whether the purchase event, its trigger URL/step, or consent defaults changed.
2. **Pull CVR for *other* traffic hitting the same checkout in the same window** — other ads, other channels, email, direct. If everyone's CVR fell together, it's funnel-wide (tracking or checkout UX), not this creative. If only this ad's CVR fell while other traffic to the same page is fine, that points specifically at message-mismatch (i.e., this ad's audience specifically expected the 20%-off and the others didn't).
3. **Pull the actual ad creative and check for any discount reference** — headline, primary text, overlay text, even an implied "today only" urgency cue. This is the fastest single check and directly disambiguates.

## If it comes back as offer-message mismatch (not tracking)

This is the one branch where your original question — "what should the new ad say" — becomes the right question, but for a different reason than wear-out: the ad would be selling a deal that no longer exists, so even a perfect hook keeps buying clicks that convert at checkout-disappointment rates. That's a copy fix, not a full creative rebuild, and production is cheap. Directions to brief, once confirmed:

- **Drop price-led messaging entirely.** Replace "20% off" with a benefit or proof-led hook: third-party lab-tested purity, specific performance outcome, or a customer-result stat. Removes the expectation mismatch at the source.
- **Swap the offer, don't retire it.** If discount-led creative has been your best performer, a live, non-expired offer (free shipping over $X, bundle discount, first-order code) preserves the "deal" hook without lying to the checkout page.
- **Urgency without price.** "Restocking Friday" / limited-batch framing keeps the urgency mechanic that made the original ad work, without referencing a number that's now false.
- **Social proof / stack-based angle.** Lean on repeat-purchase rate or review volume as the new hook — orthogonal to pricing entirely, so it's immune to future promo-calendar changes.

Route the actual copy variants through `ad-copy-variants` / `ad-creative-brief` once you've confirmed which branch you're on — that's outside what this diagnostic skill does, and the angle you brief should be written to the confirmed cause, not guessed at now.