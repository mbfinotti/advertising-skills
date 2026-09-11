## Decision: do neither. Hold current settings, don't touch bidding strategy or budget today.

Both options on the table right now would make a second significant change to an account that is still absorbing the first one — and that stacking is exactly what would prevent anyone from ever knowing which change caused what.

Here's the diagnostic behind that call.

```
ROOT-CAUSE VERDICT — Harbor & Finch Google Ads, 2026-09-12
platform(s)    : Google Ads (search) | model: B2B (legal)
window         : last 7 days (6 requests) vs baseline (10-12/wk, prior weeks) — lag maturity matched: NO
volume         : ~$7K/month, ~6 conversions in window | reconciliation gap: unverified (no CRM access)

decomposition  : cannot be run — no impressions/CTR/CPM data supplied; the only dated event in evidence
                 is a 50% budget increase 9 days ago, which lands squarely inside the observed decline window
localisation   : not assessed — no per-campaign/ad-set breakdown available

layer screen
  measurement/tracking : unknown  - no CRM access to reconcile platform-reported requests against reality  [severity: high, confidence: low]
  structure             : unknown - conversion volume (~11/wk ≈ 44-48/mo) sits near Google's own ≥30-conversion
                           floor for evaluating automated bidding; a low-volume B2B account is exactly the
                           profile that runs underpowered even before anything "breaks"                     [severity: med, confidence: low]
  targeting             : unknown - no audience/keyword data supplied                                       [severity: unknown, confidence: n/a]
  creative               : unknown - no CTR/ad-level data supplied                                          [severity: unknown, confidence: n/a]
  bidding/budget         : FAIL (leading candidate) - a 50% budget increase is well above the ~20% threshold
                           practitioners treat as a "significant edit" that resets automated-bidding
                           learning; Google Smart Bidding can take up to 3 weeks or 1-2 conversion cycles to
                           restabilize. You are 9 days in. The drop you're seeing is inside the expected
                           volatility window of your own change, not necessarily a new steady state         [severity: n/a - self-inflicted, confidence: medium]
  offer & downstream     : unknown - no landing page/form data supplied                                     [severity: unknown, confidence: n/a]
  external               : not assessed - cannot claim exclusion while tracking and structure are unknown

confidence     : low-medium — no backend reconciliation, single week of post-edit data, but the timing
                 correlation (edit → volatility, still inside the documented recalibration window) is strong
verdict        : insufficient evidence for a definitive root cause — but sufficient evidence that the two
                 proposed actions are both premature and both would make things worse, not better
evidence       : (1) the only known dated change in the window is your own 50% budget increase 9 days ago;
                 (2) that magnitude of edit is textbook "significant" and resets learning; (3) 9 days is
                 still inside the up-to-3-week window where 20-50% CPA/output swings are normal, not signal
findings       : ranked below
prediction     : if left untouched, weekly consultation requests should trend back toward the 10-12 baseline
                 within roughly 1-2 more weeks (by day ~18-21 post-edit) as delivery exits learning; if it
                 hasn't by then, that's the trigger for a full diagnostic
handoff        : CRM/reconciliation access (today, whoever can grant it) → re-check date below
re-check       : 2026-09-26 (one full week past the 3-week learning ceiling from the budget change)
```

### Why not manual CPC

Switching bidding strategy is a bigger structural edit than the budget change that likely caused this — it fully discards whatever conversion history the automated strategy has accumulated and starts recalibration from zero. You'd be resetting the exact mechanism that's already mid-reset, on an account too low-volume (≈44-48 conversions/month) to feed a strategy switch a fast read anyway. You'd very likely see the drop get worse before you could tell if it was the fix or a second injury.

### Why not doubling the budget

This doubles down on the specific action already suspected of causing the volatility. A second budget jump this large is unambiguously another "significant edit," extends the learning-phase reset by another cycle, and — even setting learning aside — an ad account that's demand-capped isn't fixed by more money if the constraint is auction rank rather than budget (a distinction you currently have no data to make). "Big budget increase" is also the one move this kind of diagnostic exists specifically to catch as a reflex fix rather than a diagnosed one.

### The actual math on "6 vs. 10-12"

Weekly consultation counts for a lead-gen account this size behave like a noisy count, not a smooth rate. A true weekly average of ~11 has a natural week-to-week spread wide enough that a single week landing at 6 is not clearly distinguishable from ordinary variance — before you even bring the budget-change confound into it. One low week, nine days after a bidding disruption, is not yet evidence of a broken account.

### What to actually do today, ranked by effort-to-value

1. **Get reconciliation access back — today, from anyone, not just the office manager.** This is rung one regardless of what else happens: every number above is unverified without it. Ask whoever has admin/read access to the CRM or booking system to pull raw consultation-request counts by day for the last 3 weeks, even as a rough export. Near-zero effort, unblocks everything.
2. **Pull two free numbers from Google Ads itself, no CRM needed:** the lost-impression-share split (budget vs. rank) on your main campaigns, and daily (not weekly) request counts since the budget change date. This tells you in minutes whether you're even capped by budget at all — if lost-to-rank is the bigger number, doubling budget would have bought nothing regardless.
3. **Do nothing to bidding or budget until the re-check date.** Let the 9-day-old change finish playing out its own learning window before drawing any conclusion from it, let alone stacking a second change on top.
4. **Calendar the re-check for 2026-09-26.** If requests haven't recovered toward 10-12/week by then, that's a real signal — and at that point the diagnostic proceeds with tracking and structure properly screened instead of both sitting at "unknown."

If your partner needs something to *act* on today rather than *wait* on: the action is closing the CRM-access gap, not touching the ad account.