## What's actually going on

Your colleague's explanation is backwards. View-through and modeled conversions **inflate** a platform's numbers — they add credit for people who saw (not clicked) an ad, or credit statistically imputed conversions. That mechanism explains a platform reporting *more* purchases than reality, not 41 vs. 67 actual orders. So that's not your gap — three other things are, and they're compounding:

**1. You're comparing two different populations, not two counts of the same thing.**
The ad platform only reports purchases it can attribute to *its own* ads (via click IDs, pixel/cookie matching). The store backend's 67 paid orders include everything — organic, direct traffic, email, other ad channels, returning customers with no ad touchpoint. There is no reason to expect 41 (ad-attributed) to equal or even approach 67 (all orders). Checking "platform vs. total store orders" every morning as if they should reconcile 1:1 is the wrong comparison and will always show a "gap," tracking bugs or not.

**2. Timezone mismatch is shifting orders across day boundaries.**
Store = UTC‑8, platform = UTC, an 8‑hour offset. The platform's "Tuesday" (00:00–23:59 UTC) does not cover the same real-world window as the store's "Tuesday" (00:00–23:59 UTC‑8). Concretely: the platform's Tuesday includes Monday 4pm–midnight Pacific, and excludes Tuesday 4pm–midnight Pacific (which lands in the platform's Wednesday bucket). Any day-by-day comparison between the two systems will be skewed by this 8-hour slice — worse on days with uneven order volume through the day, which is exactly when you'd notice a "shortfall."

**3. The new campaign's 7-day click window means Tuesday's number isn't final yet — and may not even belong to Tuesday.**
Two separate effects here:
- **Attribution lag:** with a 7-day click attribution window, a purchase can be credited to a click up to 7 days earlier. Ad platforms typically report conversions by **click date**, not purchase date, in day-by-day breakdowns — so a Tuesday purchase from someone who clicked Monday (or even before launch, if the audience overlapped with an older campaign) can show up on a *different* day's row than the one you're checking.
- **Reporting/matching lag:** conversions keep trickling in and getting backfilled for the length of the attribution window (and click-to-purchase always lags click-to-report by pixel matching, dedup, etc.). Checking "yesterday's" number the next morning — one day after a campaign launch — is checking a number that is still actively being populated. It will look artificially low almost every time, independent of any tracking bug.

Put together: even with flawless tracking, 41 vs. 67 on the very first full day of a new campaign, across a timezone-misaligned comparison of attributed-vs-total orders, is not evidence of "missing" conversions. It may be entirely expected.

## How to fix the tracking / reconciliation process

1. **Align timezones.** Set the ad platform's reporting timezone to UTC‑8 to match the store (most platforms let you set this at the account level). Until you do, never compare "Tuesday" on one system to "Tuesday" on the other.

2. **Stop comparing platform-attributed purchases to total store orders.** Instead, tag store orders with UTM parameters / click IDs (gclid, fbclid, ttclid, etc., or the platform's own attribution parameter) and pull the *subset* of store orders that carry that platform's tag. Compare that subset to the platform's reported purchases — that's an apples-to-apples reconciliation. Total store orders vs. total platform purchases will never be a meaningful number to track daily.

3. **Don't judge a day's number until the attribution window has closed.** With a 7-day click window, treat any day younger than 7 days as provisional. Build your morning dashboard to show a rolling, lagged view (e.g., "Tuesday's finalized number, as of 7 days later") alongside the live number, so you're not reacting to numbers that are still filling in.

4. **Separate "optimization" numbers from "reconciliation" numbers.** Keep view-through and modeled conversions on for campaign optimization (the platform's bidding needs them), but when reconciling against the store backend, pull the platform's *click-through, observed-only* conversion count — that's the closest like-for-like comparison to a real completed checkout.

5. **Set up server-side tracking with order-ID matching (Conversions API / Enhanced Conversions) if you haven't.** This reduces reliance on browser pixels (which lose events to ad blockers, ITP/Safari, consent banners on checkout) and lets you match by order ID rather than by aggregate day-count, which is the only way to actually find *true* tracking gaps if they exist once the above three effects are accounted for.

6. **Re-run this comparison after the 7-day window closes on the new campaign**, with timezones aligned and using the UTM-tagged subset of orders. If a real gap still exists at that point, that's your actual tracking-loss number worth investigating (pixel firing, consent-mode blocking, checkout redirect losing click ID, etc.) — right now you don't have enough clean signal to say a gap exists at all.