# Ostrena Spend Rules: Test → Prove → Scale Framework

## The core problem

A single 2.8x ROAS bar applied to everything conflates two different questions: "is this audience/channel fundamentally profitable?" and "has this test even exited the noise?" New campaigns get killed by week two because platform algorithms haven't finished learning, sample sizes are too small to mean anything, and new prospecting traffic structurally converts worse than an optimized, retargeting-heavy account average — before it's had time to build its own retargeting pool. You're not filtering out bad channels. You're filtering out anything new.

Fix: stop using one bar for everything. Use a staged framework where the bar and the metric both change as a test matures.

---

## Stage 1 — Test (weeks 1–3)

**Purpose:** find out if this audience/channel/angle has a pulse. Not a profitability decision.

- **Ring-fenced budget:** 12% of monthly spend (~$10K/month) set aside for new channels, audiences, and angles. This budget is never measured against the 2.8x bar. Treat it as R&D, funded whether or not it "pays for itself" this month.
- **Per-test minimum:** don't evaluate any test below $1,500 spend or 40 purchase-equivalent events (use add-to-cart/initiate-checkout as proxy events if purchase volume is too thin), whichever comes later. Below that, you're reading noise.
- **Metric:** leading indicators only, not ROAS — CTR vs. account average, CPC vs. account average, cost per add-to-cart, cost per initiate-checkout, hook rate on video. These predict where ROAS lands in 4–6 weeks; ROAS in week one doesn't.
- **Kill rule:** kill only if leading indicators sit meaningfully below account benchmarks (e.g., CPC >2x average, cost-per-ATC >2x average) after hitting the spend/event minimum above — not on a single bad day or a raw ROAS number.

## Stage 2 — Prove (weeks 4–8)

**Purpose:** confirm the funnel actually converts to revenue, at a lower bar than mature spend.

- **Bar:** ramp, not a cliff. Week 4: 1.5x ROAS. Week 6: 2.0x. Week 8: 2.5x. Graduate to Stage 3 only after hitting the current step's target for **two consecutive weeks** — one good week doesn't graduate a test, one bad week doesn't kill it.
- **Metric:** marginal ROAS on incremental spend within this test cell, using the analyst's existing methodology — not blended account ROAS, which will always look weak next to mature campaigns competing for the same pool.
- **Budget:** can flex up to 20% of the ring-fenced test pool per winning candidate, but stays outside the core $85K's 2.8x reporting until it graduates.

## Stage 3 — Scale (week 9+)

**Purpose:** this is now core spend, judged like everything else.

- **Bar:** full 2.8x ROAS, evaluated on marginal returns as the analyst already does weekly.
- **Budget:** moves out of the ring-fenced test pool into core spend. Scale per the existing marginal-ROAS curve — stop adding budget where marginal ROAS crosses 2.8x, same as any mature line item today.

---

## Two structural fixes underneath the stages

**1. Two-strikes kill rule, everywhere.** No campaign — test or mature — gets killed off a single week below bar. Require two consecutive weeks below threshold before pulling spend. Weekly variance in a $85K/month account is large enough that one-week kills are mostly reacting to noise, which is almost certainly why nothing has survived.

**2. Quarterly incrementality check on Meta prospecting.** Platform-reported ROAS overstates true lift, especially top-of-funnel on Meta post-iOS14. Run a geo holdout or conversion-lift test once a quarter on your biggest prospecting line. If true incremental ROAS is meaningfully below platform-reported ROAS, adjust the Stage 2/3 bars down to match reality rather than continuing to gate decisions on an inflated number.

---

## What the analyst's weekly review should look like going forward

Same cadence, three columns instead of one:

| Stage | Metric reviewed weekly                    | Action trigger                               |
| ----- | ----------------------------------------- | -------------------------------------------- |
| Test  | CTR, CPC, cost/ATC vs. account benchmark  | Kill only after spend/event minimum met      |
| Prove | Marginal ROAS vs. that week's ramp target | Graduate/hold/kill after 2 consecutive weeks |
| Scale | Marginal ROAS vs. 2.8x                    | Scale/hold/cut, same as today                |

## Bottom line

Keep the 2.8x bar — it's fine for mature spend. The fix isn't loosening standards, it's stopping the practice of judging week-one tests against a week-52 number. Ring-fence ~$10K/month that's explicitly allowed to "underperform" ROAS while it's proven on funnel metrics, ramp the bar over 8 weeks instead of applying it as a cliff, and require two bad weeks before anything gets killed. That's what's been preventing every new channel and audience from surviving long enough to become one of the wins the 2.8x bar was designed to protect.
