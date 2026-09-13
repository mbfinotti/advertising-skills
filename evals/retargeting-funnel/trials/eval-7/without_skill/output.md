# Vessel & Vine — Meta Ads Audience Diagnosis & Fix Plan

Both problems trace back to the same mistake: your exclusion logic is set at the wrong **grain** (customer-level, not product-level) and the wrong **recency** (permanent/all-time, never refreshed). Fix that mismatch and both symptoms resolve.

## Problem 1: Retargeting the exact grinder someone just bought

**Root cause**: your past-purchasers exclusion suppresses _prospecting_ campaigns at the account/customer level. It does nothing for Dynamic Product Ads (DPA), which retarget based on catalog-level events (viewed, added to cart) — not on whether that specific SKU was already purchased. Unless you explicitly wire product-level suppression into the DPA audience, Meta keeps showing that grinder.

**Fix**:

1. Split your catalog into two sets: **durables** (grinders, brewers, scales) and **consumables** (beans, filters, capsules).
2. On durables DPA/Advantage+ Catalog campaigns, enable the native "exclude people who already purchased this product" setting, or build it manually: a custom audience of `Purchase` events with matching `content_ids`, excluded from that product's ad set — set the lookback window to the max (365 days, effectively permanent for a durable good).
3. On consumables, do the opposite: suppress for ~50 days (just under your 2-month reorder cycle), then deliberately **let it lapse** so a reorder-reminder ad picks the customer back up around day 55–60. This turns your retargeting into a reorder engine instead of a nuisance.
4. Verify your Purchase event (pixel or CAPI) actually passes `content_ids` matching the catalog product ID. If match keys are missing or mismatched, Meta can't suppress at SKU level no matter what audience you build — this is the single most common cause of this exact complaint.
5. Check event delivery latency: if you're pixel-only with no Conversions API, there can be a 1–3 day lag between purchase and suppression taking effect, which is long enough to trigger an angry email the next day. Add/verify server-side CAPI for `Purchase` to close that gap.

## Problem 2: Prospecting reach shrinking every quarter for a year

**Root cause**: the agency's past-purchasers exclusion is almost certainly an **unbounded, all-time list** that was set up once and never revisited. Every quarter you acquire new customers, so the excluded pool only grows. If your prospecting targeting (interests, geography, lookalikes) hasn't been widened to match, the _eligible_ population inside a fixed targeting pool shrinks steadily — even though total site traffic (driven by returning customers, not new prospects) stays flat. This is consistent with a full year of decline with no other visible cause.

A second-order effect: someone who bought once 18 months ago and never reordered is a **churned** customer, not an active one. If they're still sitting in that exclusion list forever, you're permanently locking real prospects out of your own acquisition funnel.

**Fix**:

1. Pull the audience size history for the past-purchasers exclusion in Ads Manager (Audiences tab). Confirm it's been climbing steadily — that's your smoking gun.
2. Replace the all-time exclusion with a **rolling active-customer window**, e.g. trailing 12 months (roughly 6x your reorder cycle). Anyone who hasn't repurchased in that window drops out of the exclusion and re-enters the prospecting pool automatically.
3. Check for **stacked exclusions**: ask the agency whether prospecting also excludes site visitors, email subscribers, or engaged-with-page audiences on top of purchasers. Overlapping exclusions compound the shrinkage — audit and trim to just what's needed.
4. Use the **Audience Overlap** tool to check whether prospecting and retargeting/DPA campaigns are competing for the same people in auction — this alone can look like "shrinking reach" when it's really internal cannibalization.
5. Refresh lookalike seed audiences quarterly from recent purchasers, not a static seed from years ago — stale lookalikes drift and shrink in practical reach even if the settings look unchanged.
6. Test broadening: enable Advantage+ audience / broad targeting on at least one prospecting campaign. Meta's algorithm searches the full eligible population instead of a fixed interest bucket, which is far less sensitive to a growing exclusion list.

## Priority order (do this first)

1. **This week**: verify Purchase event `content_ids` match the catalog, add CAPI if missing — fixes the angry emails fastest.
2. **This week**: pull exclusion audience size history to confirm the growth hypothesis for reach.
3. **Next 2 weeks**: split catalog into durables/consumables suppression logic; rebuild past-purchasers exclusion as a rolling 12-month window.
4. **Ongoing**: quarterly audit — exclusion list size, lookalike refresh, audience overlap check.

## Questions to put to the agency

- Is the past-purchasers exclusion all-time or windowed, and when was it last touched?
- Are DPA/catalog campaigns using a native purchase-suppression setting, or none at all?
- Is Purchase event match quality/coverage being monitored (Events Manager diagnostics)?
- Are any other exclusion audiences stacked on top of past-purchasers in prospecting?
