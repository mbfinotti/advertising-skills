# Meta Ads Consolidation Plan — Pinemarten Goods

## The risk in doing this blind by Friday

CPA more than doubling (2.1x) in 10 days is too large to be explained by 2 of 11 ad sets resetting learning. Merging everything into one campaign _without_ diagnosing first means:

- You compound two variables (the bid change + the merge) — you'll never know which one fixed it.
- Merging resets learning phase for **all 11 ad sets at once**, which typically causes 3-7 days of _worse_ CPA before it stabilizes. If the CEO is watching daily, that reads as failure.
- Blending retargeting/warm traffic into one CBO with cold prospecting usually starves prospecting of budget — CPA looks great, volume collapses.

Do a 2-hour diagnosis today. Then merge — but merge _smart_, not literal ("all 11 into 1 ad set").

## Step 1 — Diagnose today (before touching anything)

Pull these from Ads Manager, broken out by ad set, last 10 days, daily granularity:

1. CPM trend — rising CPM = market/competition/seasonality, not a structural account problem.
2. CTR and frequency — falling CTR + rising frequency = creative fatigue.
3. Landing page conversion rate (site sessions → purchase) — flat CTR but falling CVR = pixel, checkout, or landing page issue, not a Meta problem at all.
4. Learning phase status per ad set — how many are "Learning" vs "Learning Limited" vs "Active" right now.
5. Whether the CPA jump is spread across all 11 ad sets or concentrated in the 2 that got re-tweaked.

**If CPA rose account-wide (not just the 2 reset ad sets):** the bid changes aren't the main driver. Look for a tracking break (check Events Manager for a drop in matched conversions), a checkout/pricing change, or a seasonal CPM spike. Merging campaigns won't fix a broken pixel.

**If the jump is concentrated in the 2 reset ad sets:** revert their bid strategy to what it was before the buyer's change, _first_, and watch 48 hours before deciding you also need a structural merge.

## Step 2 — The actual merge (once diagnosis rules out a tracking/pixel issue)

"Merge into one campaign" = consolidate onto Advantage+ Campaign Budget (CBO), not one giant ad set. Structure:

1. **Kill the bottom 40-50% of ad sets by spend-weighted CPA first.** Don't carry dead weight into the new campaign — 11 ad sets is already too fragmented for the account's spend level; consolidating underperformers just dilutes signal.
2. **Rebuild as 3-4 ad sets max** in one CBO campaign, segmented by audience _type_, not by product or creative:
   - Prospecting (broad/Advantage+ audience)
   - Retargeting (site visitors / cart abandoners / past purchasers) — **keep this separate**, never merge retargeting into the same CBO as prospecting, or CBO will overspend on the cheap warm audience and starve new customer acquisition.
   - Lookalike, if it's been a stable performer historically.
3. Set **ad set spend limits** (min/max) inside the CBO so the algorithm can't dump 90% of budget into one ad set on day one of the reset.
4. Carry over only the winning creatives (top 3-5 by CTR/CPA) — don't drag 11 ad sets' worth of stale creative into the reset; fresh creative in a fresh campaign learns faster.
5. Launch the new campaign, pause the old campaigns same-day (don't run both — split budget defeats the point of consolidating signal).

## Step 3 — Timeline to Friday

| Day           | Action                                                                                   |
| ------------- | ---------------------------------------------------------------------------------------- |
| Today (Fri-8) | Pull diagnostics, revert the 2 bid-tweaked ad sets, confirm pixel/CVR is healthy         |
| Mon           | Build new CBO campaign structure (3-4 ad sets), QA tracking, do not launch yet           |
| Tue           | Launch new campaign, pause old campaigns                                                 |
| Wed-Thu       | **Do not touch.** Let learning phase run — edits restart the 50-events clock             |
| Fri           | Report early CPA trend to CEO with an explicit caveat: full read takes 10-14 days, not 3 |

## Step 4 — What to tell the CEO now

Set the expectation before Friday, not after: consolidation is the right long-term move, but it triggers a fresh learning phase across the account, so **CPA may look worse for the first 3-5 days before it improves.** Promising a Friday fix when the mechanism you're deploying is known to dip first is the fastest way to lose credibility — frame Friday as "new structure live and stabilizing," not "CPA back to $38."

## What to export for me to sanity-check this before you execute

- Ads Manager: ad-set-level breakdown (spend, CPM, CTR, CPA, frequency), daily, last 30 days
- Events Manager: conversion event match quality / diagnostics, last 30 days
- The specific bid changes the media buyer made (bid strategy before/after, bid cap values) on those 2 ad sets
