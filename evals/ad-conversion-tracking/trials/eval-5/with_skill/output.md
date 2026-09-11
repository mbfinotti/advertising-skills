# Duneport Legal Software — Conversion Tracking Fix Order (pre-relaunch)

Funnel: B2B lead gen. Launch: hard, T-9 days. Dev: unavailable until next quarter (fix list capped at settings/tag-manager work). Traffic: US-only.

## Fix these 3, in this order, before launch

| # | Defect | Fix | Impact | Effort |
|---|--------|-----|--------|--------|
| 1 | (b) Lead action counts "every" instead of once per click | Flip counting method to "one" on that conversion action | High | Near-zero — one setting |
| 2 | (c) Internal traffic filter stuck in "testing" | Flip filter state from testing → active | Medium | Near-zero — one toggle |
| 3 | (a) Lead tag fires on every page load, not just submission | Re-trigger the tag in the tag manager on the actual submit/success event | Critical | ~1 hour — no dev needed |

Why this order and not impact order: settings-class toggles (1, 2) clear before trigger corrections (3) even though (3) is more severe — same near-zero effort tier goes first, then the one-hour fix. Do 2 before... 1 before 2 by impact (High beats Medium) within the same near-zero tier.

Batch all three into one tag-manager release, then re-verify once (debug mode → real test lead → payload check → platform UI status) — don't re-verify after each individual fix, or you reset the algorithm's learning phase three times instead of once.

## Deleted from the pre-launch fix list — not deferred, struck

**(d) No shared event ID (browser/server double-count).** Critical impact, but the fix needs dev coordination across both senders plus a redeploy. No engineering resource exists before launch → this is deleted from the list per the "no dev, no legal, no coordination before launch" rule, not silently dropped. **Effect the launch knowingly accepts:** lead volume will be inflated by duplicate counting, and smart bidding will optimize against the inflated number until fixed. Someone at Duneport needs to sign off in writing on accepting that.

**(f) Redirect strips gclid before landing.** High impact, week-to-quarter fix (redirect chain + storage), no dev available. Also deleted, not deferred. **Effect accepted:** attribution loss on any click that goes through that redirect.

**(e) Cookie banner blocks the tag on reject.** Traffic is US-only and doesn't touch a consent-regulated region, so this row is deleted as not applicable — not ranked, not risk-accepted, just out of scope for this account. (Flag it separately if Duneport ever runs EU/UK traffic — it'll need to come back.)

## What this means for GO/NO-GO

- Fixing 1–3 clears the automatic NO-GO conditions (wrong trigger, wrong counting method, internal traffic polluting data).
- (d) means the dedup gate (≥90% dedup rate, one counted conversion per test action) will **not** pass at launch. That's a documented, named exception to the normal gate — not a clean GO. Get an explicit approver at Duneport to sign off on launching with double-counted leads, dated, in writing.
- Don't try to patch (d) by disabling the server-side event to "stop" the double-count — that's the backwards fix the skill explicitly warns against; it just throws away the more resilient signal.

## First thing to schedule once the developer returns

1. Shared event ID (d) — top priority. It's Critical and it's the one your bidding algorithm is actively poisoned by right now.
2. Click-identifier persistence through the redirect (f) — for a B2B funnel, this is what lets the CRM import offline lead-to-deal outcomes at all, not a nice-to-have.

Re-run the full verification sequence (steps 1–9) once both land, before trusting the numbers for optimization decisions.