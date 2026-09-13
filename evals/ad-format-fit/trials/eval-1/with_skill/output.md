No web access granted, so per the skill's fallback I'll label the gating numbers "unverified-current" and tell you to confirm them in Ads Manager before spend commits. Here's the full report.

---

## Fienzo — Format-Fit Audit: Conversions Campaign (Demo Requests)

### 0. Before you build this — two mandatory unknowns

The skill this audit follows won't rank formats until objective _and platform_ are fixed, and it flags destination/tracking readiness as launch blockers. You didn't name the platform, so I'm running this as a **Meta (Facebook/Instagram) audit** — "lookalike audience," "carousel," "conversions campaign," and a $25/day budget are Meta Ads Manager's vocabulary and its typical testing scale, not LinkedIn's (LinkedIn CPCs would make $25/day barely buy a handful of clicks, and LinkedIn calls the objective "Website Conversions"). **Confirm this before you build** — if it's actually LinkedIn, everything below gets worse (spend floor problem _and_ format problem compound), not different.

Also unconfirmed, needed before launch regardless of the format verdict:

- Is there a dedicated demo-request landing page, and do you know its conversion rate? (Decides in-platform form vs. landing page — see §2.)
- Is the demo-request event verified firing (pixel/browser-side and Conversions API/server-side)?
- Any EU or consent-regulated geography in the lookalike source?

### 1. Inputs echoed

| Input                   | Value                                                    |
| ----------------------- | -------------------------------------------------------- |
| Objective               | Conversions, optimizing for demo-request submission      |
| Platform                | Assumed Meta (Facebook/Instagram) — **unconfirmed**      |
| Funnel stage / audience | Cold prospecting, lookalike                              |
| Offer                   | Demo request — sales-assisted, considered B2B deal       |
| B2B/B2C                 | B2B                                                      |
| Production capacity     | 5-card carousel built; other asset types not stated      |
| Destination / tracking  | Unconfirmed                                              |
| Budget / volume         | $25/day, target CPA ~$80 → ~2.2 conversions/week implied |
| Geography               | Unconfirmed                                              |

### 2. Per-format verdict table

| Format                                              | Verdict                                                                     | Reason                                                                                                                                                                                                                                                                                                                                                                              | Substitute                                                                                                                 |
| --------------------------------------------------- | --------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **Carousel (5-card, cold lookalike)**               | **Misfit — structural**                                                     | Carousel's fit band is _consideration, multi-product, warm audiences_; it's explicitly wrong for _cold first touch_ — sequential swipe attention nobody cold gives. A 5-card feature walkthrough is an awareness-shaped format pointed at a direct-response outcome on people who've never heard of Fienzo. This is the single most common format error in B2B paid social.         | Single image, or short vertical video if you can produce one                                                               |
| **Conversions objective @ $25/day, $80 target CPA** | **Ineligible at this budget** (hard-gate category: conversion-volume floor) | Optimization needs ~~50 events/ad set/week to exit learning phase and deliver efficiently. At $80 CPA and $25/day (~~$175/week), you're buying ~2.2 conversions/week — ~4% of the floor, and roughly in line with your current 2-3/week _company-wide_ total. An under-volume conversions objective doesn't fail gracefully; it pays more per click for a system that never learns. | Traffic / landing-page-view objective with manual funnel tracking, until budget or a proxy event clears the floor (see §3) |
| Single image                                        | **Fit**                                                                     | "Any stage, fast testing, direct response" — exactly this situation: cold, direct-response, low production budget. Pull one strong card from the carousel set or shoot one static.                                                                                                                                                                                                  | —                                                                                                                          |
| Short vertical video                                | **Conditional — fit if produced**                                           | Fits awareness-through-conversion and is the one format built to _show_ a workflow, which a static can't. Promotable here because "a workflow that needs demonstrating" is a named reason to move up a rung. Costs a shoot/screen-record, not just a re-crop.                                                                                                                       | —                                                                                                                          |
| In-platform lead form                               | **Misfit for this specific goal**                                           | Fits volume lead capture / content registration; structurally wrong for "high-value qualified pipeline, demo booking" — it removes the landing-page qualification step you need for a sales-assisted deal.                                                                                                                                                                          | Landing page with an embedded calendar                                                                                     |
| Display / retargeting                               | Ineligible for this brief                                                   | Fits cheap awareness/retargeting on warm audiences; wrong for cold direct conversion — passive, low-intent context.                                                                                                                                                                                                                                                                 | —                                                                                                                          |
| Document ads                                        | Not applicable                                                              | Fits B2B nurture/gated long-form; this is a top-of-funnel prospecting push, not a nurture sequence.                                                                                                                                                                                                                                                                                 | —                                                                                                                          |

Efficiency ranking driving the order above (cold, direct-response, B2B): single image > short vertical video (promoted for the demo-workflow reason) > carousel/lead form (both knocked out for this specific job). Carousel's effort is moderate (a card set, not a shoot) but that's irrelevant here — it's ineligible on structural fit, not on effort.

### 3. Launch-blocker list

Zero blockers is the threshold — none of these can be skipped:

1. **[blocker]** Confirm platform. The whole plan above assumes Meta; verify before building anything.
2. **[blocker]** Fix the volume math before turning on Conversions optimization. At $80 target CPA, the ~50-events/week floor needs roughly $571/day — not realistic against $25/day. Either: (a) launch on Traffic/landing-page-view objective and track demo requests manually until spend or CPA moves, or (b) keep Conversions objective but point it at a higher-volume proxy event (e.g., "landing page view" or a micro-conversion like "started the demo form") rather than final submission, so the algorithm has signal to learn on.
3. **[blocker]** Swap the format. Don't brief the 5-card carousel for this cold ad set — rebuild as single image (or short vertical video if you can shoot one in time). Save the carousel for a retargeting audience later (site visitors, video viewers) — that's exactly the "warm, consideration" band it's built for.
4. **[blocker]** Verify the demo-request event is firing and recently active, both browser-side (Pixel) and server-side (Conversions API), before spend starts.
5. **[blocker]** Confirm destination match: is the demo-request flow a landing page or Meta's native lead form? For a demo-booking goal, a landing page with an embedded calendar beats a form — a form adds a scheduling step afterward that a calendar-booking page skips. If you don't know your landing page's conversion rate, that's the tiebreaker to get before launch (≥5% → send to the page; <2% → native form is the fallback, but see the misfit note above for demo-booking specifically).
6. Preview whatever replaces the carousel across every surface it'll serve (feed, Stories/Reels) — a single image cropped for feed can get cut or letterboxed in vertical placements. Export separate 1:1/4:5 and 9:16 versions.

### 4. Post-launch watch list

Given the volume problem, format diagnostics will be hard to read cleanly for a while — you won't have enough events to isolate format from noise. Watch, in this order:

1. **Frequency out of band for a cold lookalike** (comfortable range ~1.0–2.5). If frequency climbs fast on $25/day, your lookalike is too narrow for the budget — an audience-size problem, not a creative one.
2. **Whether the ad set ever exits "learning limited."** If it sits there indefinitely, that confirms the volume-floor diagnosis in §3 rather than anything about the creative.
3. Once you do have a handful of events: **placement-breakdown divergence** (feed vs. Stories vs. Reels) — free to check, no spend required, and will show if one placement is quietly eating budget at a cheap CPM with no conversions.

Skip holdout tests entirely at this budget — they cost a week-plus of sacrificed reach and political capital you don't need to spend to diagnose a problem the math already explains.

### 5. Dated-numbers appendix

All figures below are an August 2026 snapshot per the reference material used for this audit and were **not** reverified against live platform documentation (no web access this session) — label them **unverified-current** and confirm in Ads Manager before spend commits:

- ~50 optimization events/ad set/rolling 7 days to exit learning phase and get efficient conversion-optimized delivery (~10/week exception applies to purchase/app-install objectives specifically, which demo-request likely doesn't qualify for).
- Budget-floor formula: (target CPA × 50) / 7 per day.
- Cold-prospecting frequency comfort band: ~1.0–2.5.
- Carousel/short-video typical creative lifespan: 21–35 days; static: 14–28 days.
- Safe-zone guidance for vertical placements: keep key elements out of ~top 14% / bottom 20–35%.

Keep this report as your canonical record — confirm platform, landing-page conversion rate, and tracking status, then re-run the volume math once you've picked the fallback objective/event, before this goes live.
