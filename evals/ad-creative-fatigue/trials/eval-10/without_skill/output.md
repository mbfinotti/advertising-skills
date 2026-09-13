# Bexley Books — Evergreen Carousel: Diagnosis & Refresh Plan

## Bottom line

The 25%-CPA-spike-then-fades pattern is very likely a **measurement artifact, not real fatigue**. Don't refresh creative off this signal alone — fix the measurement first, then refresh on a real basis.

## Why this looks like conversion-lag, not fatigue

1. **The "shrinks by next pull" pattern is the signature of conversion lag.** Trailing-7-day CPA pulled on Monday is immature — clicks from Thu–Sun haven't finished converting yet. A week later, that same period has "cooked" and CPA drops. This repeats every Monday because you're always comparing a fresh, unsettled week against a fully matured prior week.
2. **The mid-month attribution change amplifies exactly this artifact.** Moving from 7-day to 1-day click shortens the attribution window, so more of the true conversion volume now depends on same-day clicks — making the dashboard _more_ sensitive to lag and less able to "catch" multi-day purchase paths (typical for considered DTC purchases like books).
3. **CTR (all) is flat.** Real creative fatigue shows up first as declining CTR (ad blindness) and rising frequency — not as CPA alone. Stable CTR argues against genuine fatigue and points to a downstream (conversion-side) measurement issue.
4. **Timing lines up.** The fatigue narrative started being visible right around the same period as the attribution-window change — correlation, not evidence of creative wear-out.

## Step 1 — Fix measurement (do this before any creative work)

1. Never report CPA on a window younger than the conversion-lag horizon. Add a **T-3 to T-5 day buffer** before finalizing weekly numbers (exclude the freshest 3–5 days, or report them as "provisional").
2. Build a **lag curve**: % of conversions landing at day 0, 1, 2...7 post-click, for the carousel specifically. This quantifies exactly how much of the "gap" is timing vs. real.
3. Report CPA **on a consistent attribution window across compared periods** — don't compare a 1-day-click week against a 7-day-click week, even implicitly through backfilled history.
4. Add **platform-reported conversions** (Meta/Google's own attributed number) as a second line next to the 1-day-click number, to separate "true performance" from "window choice."
5. Track **frequency and reach** alongside CTR — the real leading indicators of fatigue that attribution changes can't distort.
6. Re-pull the last 6 weeks of history using a matured (T-7) window only, and compare like-for-like. This tells you if there's any real trend once the lag artifact is stripped out.

## Step 2 — Refresh plan (run in parallel, evaluated on fixed measurement)

Evergreen creative should be refreshed periodically regardless — but scope it as a controlled test, not a reaction to a false alarm.

1. **Hold out a control**: keep the current carousel running unchanged in one ad set/campaign as baseline.
2. **Ship 2–3 challenger variants**: new imagery/covers, updated copy angles (e.g., seasonal, bestseller-driven), refreshed CTA — same targeting, same budget tier.
3. **Run for at least 2 full conversion-lag cycles** (≥14 days) before reading results, using the matured-window CPA only.
4. **Primary metric**: matured CPA (T-7). **Secondary**: CTR, frequency, reach, hold-out ROAS.
5. Roll winner(s) into the evergreen rotation; retire the rest.

## Step 3 — Prevent recurrence

1. Change the weekly deck template: last-7-days figures shown as "provisional," matured T-7 figures shown as "confirmed."
2. Document the attribution-window change and its expected effect in the deck footnote so it's never mistaken for a performance trend again.
3. Re-evaluate in 4 weeks whether the matured, apples-to-apples trend still shows any real CPA drift — only act on creative fatigue if it does.
