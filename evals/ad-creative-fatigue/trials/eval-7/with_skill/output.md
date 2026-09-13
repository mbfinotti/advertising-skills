# Answer: No — do not rewrite the ad this sprint.

The account manager's diagnosis is built on a signal that doesn't diagnose fatigue. Ad Strength is not a performance metric — it scores asset _diversity and completeness_ (headline/description variety, keyword repetition, pinning), not how the ad is actually performing. Optmyzr's analysis of live accounts found "Average"-strength RSAs posting the best CPA/CVR in the set, and "Poor"-strength ads posting the best ROAS. A Good→Average drop tells you Google's diversity checker is less satisfied with the asset mix — it says nothing about wear-out. This is the single most common RSA misread this discipline sees, and it's exactly what happened here.

The signals that _do_ measure performance say the opposite of "fatiguing":

- **CTR flat for two months** — fatigue's signature is a gradual, sustained decline in a leading signal across multiple periods. Flat for eight-plus weeks is the shape of a healthy, stable ad, not a decaying one.
- **CVR flat for two months** — the ad's job on click-through is doing what it always did once someone lands.
- **9 of 10 assets rated Good/Best** — the legitimate Google Ads freshness signal (asset performance labels, not Ad Strength) says the ad copy itself is working.

Nothing here clears even the first bar of a fatigue call: at least two signals decaying together across two-plus periods, against the ad's own baseline. You have zero signals decaying.

## What's actually true in the data

One real, narrow finding: a single headline stuck at **Low** for five weeks. Google's Low/Good/Best label is the legitimate per-asset performance signal, and letting a persistent Low sit for five weeks is past the common 2–4 week replacement cadence practitioners use. That's a genuine, actionable item — but it's a one-asset swap, not evidence the ad is fatiguing. Nothing indicates that headline _used to_ perform and decayed; "stuck at Low" describes a consistently weak variant, not a wearing-out one. Treat it like a hook swap: replace that one headline, leave the other nine assets and the ad structure untouched.

## Fatigue Verdict

```
FATIGUE VERDICT - Norvane primary RSA, 2026-09-12
platform      : Google Ads (Search, RSA) | funnel stage: not specified (assume mixed/cold)
window        : trailing 8 weeks (CTR/CVR) vs the ad's own history | asset labels: 5-week persistence
volume        : not provided (spend/impressions/conversions unspecified)

signals
  CTR                 : flat, 2 months                [leading]  - no movement, no decay
  CVR                 : flat, 2 months                [lagging]  - stability is itself the informative read
  asset labels         : 9/10 Good/Best, 1 Low (5 wks) [leading, Google-native] - one weak component, not a wearing whole
  Ad Strength          : Good -> Average               [NOT A SIGNAL] - measures diversity/completeness, not performance; excluded from this call by design

confounder screen
  budget/bid change        : not checked - no change history provided; ask before acting further
  learning-phase reset     : not checked - last significant edit date unknown; check before touching the ad
  audience saturation      : n/a on Search in the classic sense; low priority given flat CTR/CVR
  auction CPM inflation    : not checked - no CPM trend provided
  seasonality/window mix   : plausible given 2-month flat read across multiple week-compositions - low risk
  tracking breakage        : not checked - reconcile platform conversions vs CRM/orders before trusting CVR
  attribution-window skew  : not checked
  placement/device mix     : n/a (Search)
  statistical noise        : cannot compute (p ± 2sqrt(p(1-p)/n)) without impression/click volume - flag as a gap
  landing page/offer change: not checked
  sibling-mix shift        : not checked - was anything added/removed from this ad group recently?

confidence    : medium - high confidence the Ad Strength trigger is invalid (definitional, not data-dependent);
                medium confidence on "healthy" for CTR/CVR since exact volumes/noise band aren't in hand yet
verdict       : healthy (ad level) — one Low asset flagged for routine replacement, not fatigue
action        : swap the single Low-labeled headline only (adjacent to Action Ladder rung 1: same body,
                one weak component replaced). Leave the other 9 Good/Best assets untouched. No full rewrite.
ruled out     : new concept / full rewrite - deleted by the evidence itself: no decaying performance signal
                exists to justify it, and executing it would edit a live ad with 9 proven assets, triggering
                Google's learning-phase reset and destroying the very asset-performance history (the Good/Best
                labels) that's currently the strongest evidence this ad is healthy. That's a self-inflicted
                confounder, not a fix.
expected      : replacing the one Low headline should either lift it to Learning/Good within a few weeks or
                confirm it as a genuinely weak variant; CTR/CVR should stay flat-to-better since the other
                9 assets aren't touched
re-check      : 2026-10-10 (one month out — enough for the new headline to accumulate a label, and a second
                full month of CTR/CVR to confirm nothing is actually declining)
```

## What to tell the account manager

Ad Strength moving is not evidence to act on — it's Google grading your asset variety, not your results. The metric that would actually tell you if this ad is fatiguing (CTR, CVR, per-asset Learning/Low/Good/Best) says it's healthy: flat response for two months and nine of ten assets rated Good or Best. Rewriting all the assets this sprint would mean editing a live, working ad, forcing it back through Google's learning phase, and throwing away the nine assets currently proven to perform — for a problem the data doesn't show.

The one legitimate action: replace the single headline that's been stuck at Low for five weeks. That's a five-minute edit, not a sprint-long rewrite.

Before closing this out, get answers to the four confounder gaps above (last edit date, any budget/bid change, CPM trend, and platform-vs-CRM conversion reconciliation) — cheap checks that would either reinforce "healthy" further or surface something concrete. If those come back clean too, this is closed as `healthy` with a routine one-asset swap, re-checked in a month.
