This is a marketing analytics question, not something requiring repo access — I'm answering directly.

**Don't kill anything yet. The report is broken, not the campaigns.**

## Why the "-22% total conversions" number is meaningless

You're summing three attribution windows that measure fundamentally different things:

| Source | Window | What changed |
|---|---|---|
| Meta | 7-day click → **1-day click as of the 12th** | Window cut by 85% mid-month |
| Google Ads | 30-day click | Unchanged |
| GA4 | Last-click | Unchanged |

Shrinking Meta's attribution window from 7 days to 1 day doesn't mean fewer people converted — it means Meta now *credits* far fewer of the same conversions to itself. Someone who clicks a Meta ad on Monday and buys Thursday used to count as a Meta conversion; since the 12th, it doesn't. That conversion doesn't disappear — it typically resurfaces as GA4 "direct" or "organic," or under Google Ads if there was a later branded search click. It's a reporting shift, not a demand shift.

Since the 12th, Meta's reported conversions are structurally undercounted relative to the rest of the month and relative to Google Ads/GA4. Any campaign-level total that blends pre-12th and post-12th days, or blends Meta with the other two sources, will show a fake decline concentrated in whatever ran on Meta — even for campaigns whose real performance is flat or improving. That's very likely most or all of your "bottom 20%," since Meta campaigns are the ones mechanically penalized.

## What "kill the bottom 20%" would actually do right now

Ranking campaigns by this blended total and cutting the bottom fifth will disproportionately kill Meta campaigns — not because they perform worse, but because the ruler changed length mid-month for that one source. You'd likely be cutting good campaigns based on a measurement artifact, potentially cutting spend on channels that are still working.

## What to do instead, this week

1. **Split the analysis pre-12th vs. post-12th.** Never compare a blended month against last month while the Meta window changed partway through.
2. **Re-pull Meta data on a consistent window.** Either backfill this month's Meta numbers on 7-day click (Meta's Ads Manager can usually still report this retroactively), or refit last month's Meta comparison to 1-day click, so you're comparing apples to apples.
3. **Don't sum across sources at all for decision-making.** Cross-channel deduplication requires a single source of truth (GA4 with consistent conversion windows, or a CTV/MMM approach) — summing Meta + Google + GA4 already double-counts a customer who saw both ads before buying, independent of the recent attribution change. Use each platform's own numbers to judge that platform's campaigns, and use GA4 (unaffected by the change, last-click, consistent all month) as your health check across the board.
4. **Re-rank campaigns using the corrected Meta numbers** (from step 2) instead of the current report, then look at the bottom performers again.
5. **Only then decide on cuts** — and even at that point, look at CPA/ROAS trend over 4-6 weeks per campaign rather than a single month-over-month snapshot, since a single bad week can be noise (seasonality, stockouts, creative fatigue) rather than a structural problem.

**Bottom line:** the 22% drop is mostly (possibly entirely) an artifact of the Meta attribution window change on the 12th. Fix the measurement — get Meta back on a consistent window or exclude the affected days — before you touch budgets. Cutting the "bottom 20%" today means cutting campaigns based on a ruler that got shorter, not campaigns that got worse.