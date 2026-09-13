# Meta Account Diagnostic — Juniper Wellness

## Bottom line for the board

The premise "the account is underperforming badly" doesn't survive contact with the account's own data. Before recommending a single fix, the diagnostic method this audit follows requires comparing the account against its own history, never against a purchased industry-benchmark report — and by that standard, this account isn't broken. It's a stable, profitable system that has been misread through the wrong yardstick.

**Why the benchmark comparison is invalid on its own:**

- **Break-even ROAS ≈ 1 / contribution margin = 1 / 0.55 ≈ 1.82.** Your ROAS (2.3–2.5) and blended MER (2.1) have both sat comfortably above break-even for 12 straight months. This account has been profitably paying for itself every month of the window you're describing.
- **12 months flat is not a "collapse," it's a steady state.** ROAS in a 0.2-point band and CTR pinned at ~0.9% for a full year, with no break date and no change log, means there is no failing link to localize. A diagnostic decomposes a _move_ — CPM, CTR, CVR, or AOV shifting versus the account's own baseline. Nothing here has moved. There is nothing to trace to a root cause.
- **A benchmark CTR/ROAS figure is not a like-for-like number.** Industry averages blend unknown mixes of objective (traffic vs. conversion), placement (feed vs. Reels vs. Stories), funnel stage (cold prospecting vs. warm retargeting), CTR definition (link-click vs. all-click), attribution window, and even which advertisers chose to submit data to the report (self-selection tends to skew published averages upward). A DTC supplements brand running cold-audience prospecting at scale will structurally show a lower CTR than a benchmark blended across remarketing-heavy or smaller accounts — with no implication for profitability.
- **Flat CTR for 12 months without decay is actually a good sign.** Creative fatigue shows up as CTR eroding over time on an aging creative. A CTR that holds steady for a year says the creative refresh cadence already in place is working, not that it's broken.

This is a textbook case of **benchmark shopping** — one of the standard auditor bias traps: industry averages carry different mix, geography, and definitions, and the account's own history is the only valid baseline. Treating "we're below the benchmark" as a mandate to find things broken also risks the **pitch-audit incentive** trap: a board mandate to "identify everything that's broken next week" structurally biases toward manufacturing findings. I'm not going to hand you a list of red flags to satisfy that framing — only what the evidence actually supports.

---

## ROOT-CAUSE VERDICT — Juniper Wellness (Meta), 2026-09-12

```
platform(s)    : Meta (paid social) | model: B2C/ecommerce
window         : trailing 12 months, no comparison baseline needed - metric has not moved
volume         : spend, conversion count, and attribution settings not provided | reconciliation gap: unverified

decomposition  : CTR flat ~0.9% x 12mo; CPM, CVR, AOV not supplied - cannot isolate a failing link because
                 nothing has moved against the account's own history. ROAS (2.3-2.5) and MER (2.1) both
                 sit ~1.15-1.3x above break-even (≈1.82, from 55% contribution margin) throughout.
localisation   : not assessable - no per-campaign/ad-set/ad breakdown supplied

layer screen
  measurement/tracking : unknown - no backend/CRM reconciliation supplied; ratio stability unverified   [medium, low]
  structure             : unknown - no per-campaign spend/conversion breakdown; cannot check for pooled
                           averages masking a starved or self-competing sub-segment                       [medium, low]
  targeting             : unknown - no frequency/reach/overlap data supplied                              [medium, low]
  creative               : pass-with-note - 12mo of non-decaying CTR is inconsistent with active creative
                           fatigue; refresh cadence appears to be working                                  [-, medium]
  bidding/budget        : unknown - no lost-impression-share split, no bid strategy, no edit log supplied  [medium, low]
  offer & downstream    : pass - CVR/AOV not supplied, but stated "nothing changed" rules out a dated break [-, low]
  external               : n/a - no cost-side anomaly to explain; no move to attribute externally           [-, -]

confidence     : low on any FAIL - not because the account is clean, but because the four Evidence Gate
                 checks (volume, learning-phase state, window comparability, attribution consistency)
                 cannot be run on ratios alone
verdict        : insufficient evidence to declare a defect - and the one number that IS gate-clean
                 (12mo of stable ROAS/MER above break-even) argues against "badly underperforming"
evidence       : ROAS and MER both hold ~15-30% above break-even continuously; CTR shows no decay pattern;
                 no break date exists to anchor any of the seven layers to a cause
prediction     : none issued for a "fix" - there is no confirmed defect to predict a recovery from
handoff        : see Findings below - this diagnostic itself, re-run once the data gaps are closed
re-check       : after the data below is supplied and a first real per-layer screen runs
```

---

## What's actually missing to run this properly

A defensible board deck needs a real screen, not ratios. To turn "unknown" into "pass" or "FAIL" on the layers above, get:

- **Per-campaign, per-day exports** (minimum granularity) for the last 12 months — spend, impressions, CPM, clicks, conversions, revenue. Per-ad-set and per-ad breakdowns unlock the localization step.
- **Backend/CRM revenue reconciliation** against platform-reported conversions, on a lag-mature window (7+ days), checked for a _stable_ ratio over time — not a single snapshot.
- **Attribution window and counting settings**, and confirmation they haven't changed in the last 12 months (a silent settings change can manufacture a phantom trend).
- **Edit log**: any budget, bid, targeting, creative, or optimization-event changes in the window, with dates — "nothing changed" is a strong claim worth confirming against the actual account change history, not memory.
- **Conversion volume and spend figures** (not just ratios) — needed to compute whether any future observed delta clears the statistical noise band, and to check units are above the volume gates automated bidding needs.
- **The benchmark report's own methodology**: CTR definition (link vs. all-click), objective/placement mix, and sample composition. Without this, "1.6% vs 0.9%" isn't a comparable pair of numbers.

## Findings, ranked by efficiency (not by how alarming they sound)

1. **Reconciliation check** — confirm platform-reported revenue against backend/order-table truth over a lag-mature window. _[severity: informational until run; confidence: n/a yet; outcome: buys trust in every other number, including the ones already reported above; effort: hours; owner: whoever holds ad platform + backend access]_
2. **Pull the real per-campaign/ad-set breakdown** and check whether the flat blended average is hiding a strong sub-segment being starved by budget next to a weak one absorbing spend — a reallocation opportunity that a blended 2.4 ROAS can't reveal. _[severity: unknown until pulled; confidence: low; outcome: unquantified, plausibly the single highest-value action available here; effort: a few hours of export + review; owner: media buyer]_
3. **Re-scope the board narrative before the deck ships**: replace "underperforming vs. industry benchmark" with "stable and profitable at 1.15-1.3x break-even for 12 months; investigating whether reallocation within the account can lift it further." Presenting the current framing to the board risks funding a rebuild — new creative, restructured campaigns, budget increases — against a problem that the account's own data doesn't show. Per this diagnostic's own reasoning: budget increases beyond ~20% reset Meta's learning phase and run CPAs 20-50% hotter the following week for no proven gain; that's a cost paid for chasing a benchmark number, not fixing a defect. _[severity: high if skipped - this is the actual risk in front of you next week; confidence: high; outcome: prevents committing spend/creative budget against a false premise; effort: near-zero, it's a framing change; owner: you]_
4. **Only after 1-2 above**: if the per-segment pull in (2) surfaces a genuine concentrated weak spot, that becomes a real, localized finding worth a targeted fix (targeting redesign, structural consolidation, or a bid-strategy check) — diagnosed on its own evidence, not on a benchmark gap.

**What this list deletes, explicitly:** a creative overhaul and a budget increase, both of which the "CTR is low" framing invites by reflex. Deleted because a full year of non-decaying CTR is inconsistent with creative fatigue, and because increasing budget against a stable, non-capped-looking account mainly risks a learning reset with no identified upside. Revive either only if the per-segment pull in Finding 2 turns up a concentrated, dated cause that points there specifically.

## For the board, in one sentence

Juniper Wellness's Meta account has been profitably clearing break-even by 15-30% every month for a year with no defect currently evident in the data provided — the fix list this week is "pull the real exports and reconcile against backend truth," not a creative or budget overhaul chasing a benchmark number that isn't measuring the same thing as this account's ROAS.
