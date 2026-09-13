# Fernway Travel — Ad Account Diagnostic: Quick Wins, Ranked

## Layer screen (based on what the audit surfaced)

```
ROOT-CAUSE VERDICT - fernway-travel, 2026-09-12
platform(s)    : unspecified | model: B2C (travel/tour bookings, order table = source of truth)
window         : not yet windowed - findings below are point-in-time audit observations, not a before/after comparison
volume         : 14 campaigns; 11 of 14 under 10 conversions/month each | reconciliation gap: ~100% (reported ≈ 2× booking system)

decomposition  : not yet run - CPM/CTR/CVR breakdown by campaign wasn't in the audit; do this once tracking is fixed, not before
localisation   : tracking gap is uniform (every booking counted twice) - classic tracking signature, not a targeted internal cause

layer screen
  measurement/tracking : FAIL - reported purchases ≈ 2× booking-system count, confirmed              [critical, high]
  structure             : FAIL - 11/14 campaigns below the ~15-30 conversions/month volume gate        [high, high]
  targeting              : unknown - not screened, no evidence supplied                                 [-, -]
  creative                : unknown-likely - 5+ months old is a staleness signal, not a measured decay (no CTR-vs-baseline data given) [medium, low]
  bidding/budget       : unknown - 2 campaigns underspend; lost-to-budget vs lost-to-rank not yet pulled [medium, low]
  offer & downstream   : not screened - no CVR/page data supplied                                        [-, -]
  external                : not screened - no market/seasonality data supplied                           [-, -]

confidence     : mixed - tracking and structure are high-confidence (the numbers you already have confirm them directly); creative and budget findings are directional only until you pull the underlying data
verdict        : compound - (1) measurement/tracking, (2) structure - both confirmed, both corrupting every other read in the account
evidence       : ~2x reconciliation gap vs booking system; 11/14 campaigns starved below the volume any bidding algorithm needs to learn
```

**One consequence to brace the CEO for:** once you fix the double-count, reported conversions will roughly halve and reported CPA/ROAS will look like they got worse overnight. They didn't — the dashboard just stops lying. Say this out loud before you ship the fix, or the fix itself gets read as a performance collapse.

## What your two stated constraints kill or change

- **No CRM/export, booking system has none, IT says next year** → deletes the "feed booking outcomes back to the ad platform" fix entirely. Not parked, not deferred — deleted from this quarter's plan. Revive it the day an export exists.
- **Zero engineering this quarter (CTO-confirmed)** → does **not** delete the tracking fix, because tracking is the confirmed root cause and root-cause fixes escalate rather than disappear. But it changes _how_ you fix it: don't file an engineering ticket and wait. Duplicate purchase-fire is very often a tag-configuration problem (same pixel firing twice on the confirmation page, or both a client-side and server-side tag sending the same event with no dedup key) — fixable inside your ad platform / tag manager by marketing, no code change. Try that path first this week. Only escalate to the CTO as a hard ask if you confirm the duplicate call is baked into the booking system's own page code.
- **Creative studio on retainer, idle capacity** → this is the one condition the skill explicitly calls out as promoting creative refresh ahead of its normal place in the queue. Use it — it's capacity you're already paying for.

## Quick wins, in order

1. **Fix the double-firing purchase event.** [critical severity, high confidence, restores every other number in the account, ~a day of marketing-ops/tag-manager work — not engineering, owner: whoever has tag-manager/ads-platform admin access]
   Check for a duplicate tag/pixel on the booking confirmation page first (two tags, or client+server both firing untagged). Add a dedup key (order/booking ID as the event ID) if the platform supports it. This is rung 1 for a reason: every number below is currently unreadable until this ships.

2. **Consolidate the 11 sub-10-conversion campaigns.** [high severity, high confidence, gets your smaller campaigns above the volume any automated bidding needs to exit learning, a few hours inside the ad platform UI, owner: you or your teammate]
   No engineering needed — this is campaign-structure work inside the platform itself. Group by shared audience/objective rather than by whatever logic created 14 in the first place. Note: once the tracking fix ships, the true conversion counts on these campaigns will likely look even lower than reported (since half of what's counted now is duplicate), which only strengthens the case for merging.

3. **Pull the lost-impression-share split (budget vs. rank) on the 2 underspending campaigns.** [medium severity, low confidence until pulled, near-zero effort — it's a native platform report, owner: whoever runs the account]
   Underspend is not automatically a "raise the budget" problem — it's just as often a bid set too low or an audience too narrow to spend into. Diagnose before touching either budget. If it turns out lost-to-budget and everything else above passes, that's a legitimate, fast, reversible fix — but do it last, not first, and only after step 1-2 give you real numbers to judge it against.

4. **Brief the creative studio and start production now.** [medium severity, low-to-medium confidence on decay itself, standing job not a one-time fix, owner: creative studio + you]
   You have the capacity sitting idle and 5-month-old creative is a real flag even without a CTR breakdown yet — this is exactly the situation where promoting creative refresh ahead of its default queue position is justified. Start the brief this week for visible motion, but hold off judging whether it's _working_ until you can read CTR against a tracking signal you actually trust (i.e., after step 1).

**Deleted, not deferred:** offline-outcome feedback loop (booking system → ad platform). No export exists anywhere in scope this quarter. Revive when IT ships one.

**Re-check:** 2026-10-10 — gives the tracking fix and campaign consolidation time to clear a lag-mature window, and the merged campaigns time to start re-accumulating volume before you judge anything by the new (correct) numbers.
