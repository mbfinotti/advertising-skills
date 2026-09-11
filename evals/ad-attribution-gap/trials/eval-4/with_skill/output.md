# Attribution Gap Reconciliation — Vanterra Skincare, Tuesday

## Headline

**Anchor: store backend, 67 paid orders.** Ad platform reports 41 — a gap of 26 units (39% of the anchor). Verdict: **not yet classified as a defect** — the data available today can't separate timing from a real problem, because you're comparing a single immature day across two misaligned clocks. Two structural causes almost certainly explain most of the gap on their own. Your colleague's explanation is backwards and should be dropped.

## Your colleague's theory is directionally wrong

View-through and modeled conversions are a **platform-high** cause — they add conversions the store never sees, so they push the platform's number *above* the anchor, never below it. Your platform number is *below* the anchor (41 vs 67). A cause that inflates the platform's count cannot explain a count that's too low. Apply the direction rule and strike it.

If anything, a campaign that launched yesterday has too little history for the platform's modeled-conversion engine to have kicked in yet, so today's 41 is probably closer to bare click-tracked conversions than a modeled/inflated number. That makes the real gap, not smaller than 26, but a fact you can't fully see yet.

## What's actually going on: two Bucket 1 (timing) causes, both pointing platform-low

**1. Timezone misalignment shifts what "Tuesday" means by 8 hours.**
Store day (UTC-8): Tue 08:00 UTC → Wed 08:00 UTC.
Platform day (UTC): Tue 00:00 UTC → Wed 00:00 UTC.

These windows overlap for only 16 of 24 hours. The platform's "Tuesday" pulls in 8 hours of orders the store books as *Monday* (Tue 00:00–08:00 UTC), and the store's "Tuesday" runs 8 hours into what the platform will book as *Wednesday* (Wed 00:00–08:00 UTC). A same-labeled-day comparison across two different clocks is comparing two different windows, not the same day — this alone can account for a meaningful slice of the 26-unit gap, in either direction, without any tracking defect. Single-day comparisons are the worst case for exactly this reason.

**2. The attribution window hasn't closed — and this is a brand-new campaign.**
The new campaign launched Monday with a 7-day click window. Ad platforms stamp conversions on the *click* date and backdate them as they land, not on the purchase date. So a person who clicked Monday or Tuesday and buys on Thursday will eventually get counted back onto Monday or Tuesday — but not yet, because it hasn't happened.

In a mature, steady-running campaign this washes out: today's under-count from immature recent clicks is offset by older cohorts finally landing. This campaign has no such backlog — it's one day old. There is no prior cohort feeding today's number, so the platform's Tuesday count is structurally at its most incomplete right now and will keep rising for up to 7 days as Monday's and Tuesday's clicks finish converting.

Between these two, expect a meaningful share — plausibly most — of the 26-unit gap to close on its own once the window matures and the comparison is redone on aligned clocks.

## What I can't classify yet — and what to check

I only have one day of counts, no revenue, and no history, so I can't compute an explained share against the skill's 80% pass bar today. Two things to verify before trusting whatever residual is left:

- **New landing page / new pixel risk.** New campaigns often ship new landing page templates. If the purchase-confirmation tag wasn't copied onto the new template, or a redirect on the new URL is stripping the click ID, that's a real Bucket 3 defect (broken/missing tag) — it would show up as platform-low, same direction as the two timing causes above, so it can hide behind them right now. Worth a manual test purchase through the new campaign's actual path.
- **Attribution model / counting rule mismatch**, if the platform is set to a shorter effective reporting window than the 7-day click window you launched with, or "one conversion per click" vs "every" — check the platform's own settings rather than assume.

Neither can be distinguished from the timing effects using a single day's totals. That's the whole reason not to chase this to zero today.

## Fix — in order

1. **Stop comparing single raw days.** Re-run this comparison at weekly grain going forward; day-level pulls amplify exactly the timezone and lag effects above into false alarms.
2. **Align the clocks.** Either set the platform account's reporting timezone to UTC-8 to match the store, or manually re-bucket the platform pull to the store's UTC-8 day boundaries before comparing. Do this once, as a config change — it removes the 8-hour noise permanently, not just for this campaign.
3. **Wait for the window to mature before re-judging.** Re-pull Tuesday's platform number again after the 7-day click window fully closes (i.e., a week from launch) before drawing any conclusion. Expect the 41 to have grown by then.
4. **Do a manual test purchase through the new campaign's actual ad → landing page → checkout path today**, and confirm in the platform's real-time event log that a conversion fires. This is the fast, cheap check that rules the tag-breakage risk in or out without waiting a week.
5. **Only escalate as a defect** if, after steps 2–4, the gap is still large, hasn't shrunk as the window matured, or the test purchase didn't fire a tracked conversion. At that point this becomes a `mbfinotti/advertising-skills@ad-conversion-tracking` handoff (tag/pixel fix), not a reconciliation problem.

## Known delta to carry forward

Once the timezone alignment is fixed, expect a small, stable, *platform-low* delta on any given day going forward, driven purely by attribution-window lag (a purchase from an old click lands days after the click was originally tracked). That's expected and not a "missing third of your sales" — it's the same mechanism that made today's 26-unit gap look worse than it likely is, just at steady-state size instead of new-campaign size.