# Sanity-check verdict: don't restructure or refresh creative yet — this is an offer/page problem, not an account problem

Running your numbers through the standard diagnostic decomposition (CPM × CTR × CVR × AOV = ROAS) before naming a cause, per the ad-account-diagnostic method.

## Decomposition first

```
ROAS ≈ (CTR × CVR × AOV) / (CPM/1000)
```

Three of your four levers didn't move: CPM +1%, CTR -1%, search impression share flat at 68%. Only CVR moved, and it moved by a lot (-41%), starting on a single named date. That is the textbook single-failing-link pattern — "CVR fell, CTR and CPM held" points past the ad, onto the page and the offer, *not* onto structure, targeting, or creative.

Sanity-check the arithmetic: if AOV rose in line with your 12% price increase (units/order unchanged), the identity predicts ROAS ≈ 3.4 × (1 − 0.41) × 1.12 ≈ **2.25** — close to your observed 2.1. The residual ~7% gap is worth checking against actual AOV (a price increase doesn't always fully convert to AOV if mix shifts toward cheaper SKUs or discount usage rises), but the two knowns you gave already reconstruct most of the decline. That's a strong internal consistency check, not a coincidence.

## Layer screen

```
ROOT-CAUSE VERDICT - Lumen Desks, 2026-09-12
platform(s)    : Google + Meta | model: B2C/ecommerce
window         : 3 weeks post-Mar 3 vs prior baseline (lag maturity: likely yes - DTC purchase cycle is short; confirm day-of-week match)
volume         : ~$80K/month spend | reconciliation gap: 7% vs order system (unchanged from historical norm)

decomposition  : CVR -41% is the sole failing link; CPM +1%, CTR -1%, impression share flat - all within noise
localisation   : uniform across the funnel upstream of conversion (both channels' CPM/CTR/IS held); break dates exactly to Mar 3

layer screen
  measurement/tracking : pass - reconciliation ratio (7%) is unchanged from its historical norm; a broken pixel from
                          the new template would have widened this gap, not held it steady           [-, high]
  structure             : pass - no structural edits reported in the window; nothing in the evidence implicates
                          fragmentation, overlap, or optimization-event choice for *this* decline      [-, medium - no
                          per-campaign/ad-set breakdown supplied]
  targeting              : pass - CPM flat, impression share flat = no saturation or audience-mix signature        [-, medium]
  creative               : pass - CTR flat, not falling; the creative-decay signature (CPM up + CTR down, or CTR
                          down alone) is absent                                                       [-, high]
  bidding/budget         : pass - impression share stable at 68% (no lost-IS erosion); no bid/budget edits reported [-, high]
  offer & downstream     : FAIL - CVR collapse dates exactly to a shipped page-template change and a 12% price
                          increase on the same day; CPM/CTR/IS all held steady through it              [critical, high]
  external               : n/a - no cost-side anomaly (CPM flat); a dated internal cause already accounts for the move

confidence     : high - single break date, clean upstream/downstream split, tracking reconciliation independently
                 confirms the pixel didn't break, and the ROAS arithmetic reconstructs from the two known changes
verdict        : offer & downstream - the Mar 3 product-page template and/or the 12% price increase. The two shipped
                 together, so this is a compound *candidate*, not yet a resolved compound verdict - see finding #1.
evidence       : CVR -41% starting Mar 3 with CPM/CTR/impression share unmoved; reconciliation gap unchanged (rules
                 out a tracking break masquerading as a CVR drop); ROAS arithmetic reconstructs within ~7% from the
                 two dated changes alone
```

## Why not your plan, specifically

- **Account restructure**: screened `pass`. Nothing in the evidence points at fragmentation, overlapping campaigns, or a bad optimization event — that's a real thing worth doing eventually if the account is genuinely messy, but it isn't what broke ROAS in the last three weeks, and doing it now injects a learning-window reset on top of an already-declining number, making the real fix's effect impossible to isolate afterward.
- **Creative refresh**: screened `pass`. CTR is flat, not falling — the creative-decay signature (CPM up + CTR down, or CTR down alone) isn't present. New creative wouldn't touch CVR in this decomposition at all; you'd spend a production cycle and see no recovery, which would just send you hunting for the next reflex fix.

Both sit on low rungs of the standard efficiency order anyway (structure = rung 3, creative = rung 6) — but here they're additionally *ruled out by evidence*, not just lower priority. Doing either now adds confounding variables right when you need a clean read on the actual cause.

Two things push offer & downstream to the top of the queue instead of its usual rung 5: the decomposition localizes cleanly past the click (CPM/CTR/impression share all held), and the page/price owners sit on your own team next to you — the usual "coordination cost" that keeps this rung starved doesn't apply here.

## What to actually do, in order

1. **Isolate the two Mar-3 changes from each other.** They shipped same-day, so right now you can't tell if it's the template, the price, or both. Cheapest test: revert the page template only, for a short window, keeping the price increase in place. If CVR recovers, it's the page. If it doesn't, the price increase is the driver (or a bigger one than expected). *[critical, high-value, near-zero-to-a-day effort, in-house web team]*
2. **Walk the actual page yourself on a paid-traffic device/session** — the exact settling check for this layer: broken add-to-cart, slower load, missing trust signals/specs, mobile layout regression, checkout redirect issues. *[high, hours, you + web team]*
3. **Segment CVR by traffic source** (paid vs. organic/email) — if the drop is sitewide and uniform, it implicates the template broadly; if it's concentrated in paid sessions specifically, check message-match between your ad creative and the now-changed landing page. *[medium, hours]*
4. **Pull actual AOV** for the window and compare to the +12% price increase — confirms or corrects the assumption behind the arithmetic check above, and tells you whether buyers are also trading down in response to the price move. *[medium, near-zero, reporting pull]*

Once isolated, this hands to `mbfinotti/advertising-skills@paid-landing-page-audit` for the page-fix list — that skill picks up exactly where this one stops, at the click.

**Prediction to log**: once the page/price cause is isolated and fixed, CVR should recover most of the way toward its pre-Mar-3 baseline within one lag-mature window (roughly 7-14 days for a DTC purchase cycle) of the fix shipping, and ROAS should follow back toward the 2.9-3.4 range depending on whether the 12% price increase is kept.

**Two gaps worth closing before you fully sign off on this**: exact conversion counts for the window (to confirm you clear the statistical noise band — at $80K/month on ecommerce this is very likely fine, but worth confirming), and a per-campaign/ad-set breakdown to firm up "pass, medium confidence" on structure and targeting into "pass, high confidence."