# Fernway Travel — Ad Account Quick Wins (This Week)

**Order matters here.** The double-firing purchase event corrupts every other number in the account — CPA, ROAS, which campaigns "work," even the conversion-count problem in #2. Fix measurement before you touch budgets or campaign structure, or you'll be optimizing against fake data twice.

## 1. Kill the duplicate purchase event (Day 1-2, no engineering needed)

This is the highest priority and the fastest fix. It also means your real numbers are worse than reported: if the platform is counting ~2x bookings, your 11 "under-10-conversions" campaigns are actually closer to 5 or fewer real conversions each. The learning-phase problem in #2 is bigger than the audit shows.

**Do this week:**

- Check if the ad platform's conversion action is set to count "every" fire vs "unique" — most platforms (Meta, Google Ads) have a per-conversion-action toggle for unique/one-per-session counting. Flip it as an immediate stopgap. Takes minutes, no code touch.
- Open the booking confirmation page in GTM Preview mode (or browser dev tools network tab) and watch what fires on page load. Classic causes, all fixable by marketing/ops without an engineer:
  - Two tags firing the same event (legacy pixel never removed + newer one added).
  - Confirmation page reloading once due to a payment-gateway redirect bounce.
  - Pixel firing on both initial render and a client-side re-render.
- If you control GTM: add a firing-once guard (session storage flag, or dedupe on the booking reference number already visible in the page's DOM/URL — no engineering required to read it).
- If you don't control GTM and can't touch the page at all, this is the one item worth a direct, narrowly-scoped ask to the CTO: "one dedupe guard on one page" is a very different lift than "build a CRM export." Frame it that way — you may get 30 minutes even in a zero-availability quarter.

**Owner:** you or your teammate, via ad platform + GTM. **Visible by:** end of week, reported conversions should roughly halve and finally track the booking system.

## 2. Consolidate the 14 campaigns (Day 2-4)

11 campaigns starved of data means the algorithm never exits learning phase on most of your account — spend is being wasted on exploration, not delivery. With CRM/audience data unavailable this year, you can't fix this with better targeting signals, only with volume concentration.

- Merge overlapping campaigns (same objective, same audience type) into 3-5 broader campaigns instead of 14 thin ones. Target getting each surviving campaign to 15-20+ conversions/month minimum — real conversions, post-fix.
- Pause, don't delete, the campaigns you fold in — you may want the exclusion/audience data later.
- Keep the 2-3 highest-volume campaigns as-is if they're already clearing threshold; don't disturb what's working.

**Owner:** you. **Visible by:** restructure live within the week; performance signal takes 2-3 weeks to stabilize post-consolidation — tell the CEO that upfront so the "visible action" isn't mistaken for "visible results."

## 3. Fix the two underspending campaigns (Day 3-5)

Likely one of three causes, all diagnosable from the ad platform UI alone:

- Bid cap or target CPA/ROAS set too aggressively low for current auction pricing — loosen it.
- Audience too narrow / already exhausted — broaden or fold into the consolidation in #2.
- Creative fatigue suppressing delivery (ties directly to #4) — stale creative can tank relevance/quality scores and choke spend even with budget available.

Check delivery diagnostics first (most platforms flag "limited by budget" vs "limited by bid" vs "audience exhausted" directly) before changing anything — don't guess.

**Owner:** you. **Visible by:** same week, budget utilization should move within days of a bid/audience change.

## 4. Brief the creative studio (Day 1, in parallel — don't wait)

Idle retainer capacity plus 5-month-old creative is free upside sitting on the table. Kick this off same day as #1, not after — it's the longest lead time item (concepting + production), so starting it this week is itself the visible action, even though finished assets land later.

- Brief 3-4 new concepts against your surviving consolidated campaigns (#2), not the ones you're pausing.
- Ask for at least one format variant per concept (static + short video, or two aspect ratios) — you have the studio capacity, use it for testing surface area, not just refresh.
- Target first batch live in-platform within 10-14 days.

**Owner:** you/teammate to write the brief today. **Visible by:** brief sent this week; assets in 2 weeks.

---

## What to explicitly NOT chase this quarter

- **CRM/export-dependent optimization** (lookalikes from booking data, LTV-based bidding, customer lists) — not available until IT ships an export, possibly next year. Don't let this block the four items above; none of them need it.
- **Engineering-dependent fixes** — if the duplicate-fire root cause turns out to live in application code you truly can't touch (not GTM-controllable), don't escalate further this quarter. Apply the platform-side "unique conversion" toggle as the standing workaround and revisit when engineering has capacity.

## What to tell the CEO this week

All four actions are live or in motion by Friday: measurement fixed, account restructured, budgets rebalanced, new creative briefed. Frame the win as "stopped bidding on fake data and cleared 11 campaigns' worth of a stalled learning phase" — that's the real story, not just activity.
