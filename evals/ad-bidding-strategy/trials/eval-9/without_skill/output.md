# Nockboard — Meta Ads Bidding & Optimization Rules

## Why results have been swinging

Qualified signup lag is ~3 weeks (click → signup) plus a few days of reporting lag. That means CPA numbers seen in the first ~25 days after a change are structurally understated on results and inflated on cost — not a true read. Three CPA goal changes in two weeks ($60→$48→$55→$50) were reactions to immature cohorts, not to real performance. Volatility is partly self-inflicted: changing inputs faster than the system can report outputs.

Fix: separate a **fast, automated safety net** (protects spend, can act early) from **goal-setting** (must wait for mature data). Never let the same clock govern both.

---

## 1. Attribution & maturity setup

1. Use Meta's **28-day click** attribution window (not the 7-day default) for the qualified signup conversion event, synced via Conversions API from the CRM. A shorter window will show a conversion count that's structurally too low.
2. Define **data maturity** = 21 days (signup lag) + 5 days (reporting buffer) = **26 days from spend date**. Round up: treat any ad set's data as immature until **day 28**.
3. Tag every reporting view and rule with maturity in mind. A "bad" CPA on a 10-day-old ad set is not evidence — it's an incomplete cohort.

## 2. Automated rule — hard circuit breaker (spend protection)

This is the only rule allowed to act on **immature** data, because it exists to stop runaway spend, not to judge performance.

**Rule A — Zero-result burn:**

- **Condition:** Lifetime amount spent ≥ $200 AND qualified signups = 0.
- **Action:** Pause ad set.
- **Why $200:** roughly 4x the $50 target CPA — enough spend that zero signups even accounting for lag is a real red flag, not noise.
- **Check frequency:** daily.

**Rule B — Hard CPA ceiling ($90):**

- **Condition:** Lifetime cost per result (28-day click) > $90 AND lifetime spend ≥ $450 (≈5 conversions' worth at target) AND ad set age ≥ 28 days.
- **Action:** Pause ad set + Slack/email alert to team.
- **Why gate on age and spend:** without these, the $90 rule will fire on immature cohorts and kill ad sets that are actually fine — reproducing the exact whipsaw this doc exists to stop.
- **Check frequency:** daily.

Do not build a version of Rule B without the age/spend gates. An ungated ">$90 → pause" rule is the automation equivalent of what's been happening manually for two weeks.

## 3. Goal-setting rules (target CPA)

1. **One target CPA at a time.** Current target: $50.
2. **Minimum change interval: 28 days.** Do not adjust the target CPA more than once per maturity cycle. If it's been changed in the last 28 days, the next data point to react to is the day-28 mark of the _most recent_ change — not today's feed.
3. **Evidence required to change the target:** at least 2 full maturity cycles (56 days) of stable spend showing consistent over/under-shoot, across at least 3 ad sets, before permanently moving the target. A single volatile cycle is not evidence.
4. **Direction of change is capped:** ±$10 per adjustment. No jumping $12 in one move ($60→$48).
5. **Log every change** (date, old value, new value, reason, who approved) in a shared doc — not just in Meta. Anyone about to change the target checks the log first for "haven't we just done this."

## 4. Creative and audience rules

1. **Creative refresh cadence:** every 4–6 weeks, or on clear frequency/fatigue signal (frequency > 3.5 and CTR down >25% vs its own first-2-week baseline) — not on a bad week of CPA.
2. **Audience changes:** treat like target CPA changes — one variable at a time, minimum 28-day evaluation window before judging, logged in the same doc.
3. **Never change creative, audience, and target CPA in the same week.** If more than one lever moved, a later CPA read cannot be attributed to any single cause — the next 28 days are lost to attribution ambiguity, not just extended.

## 5. Weekly review process (replaces ad-hoc adjustments)

1. **Weekly check-in:** review spend, results, circuit-breaker triggers. No target/creative/audience decisions made here — just monitoring.
2. **Maturity-gated review, every 28 days:** this is the only meeting where target CPA, creative, or audience can change. One change max per cycle.
3. **Between reviews:** only the two automated rules (Section 2) may act. No manual pauses or budget shifts based on early CPA reads. If someone wants to override this, it goes in the change log with a reason — not silently.

## 6. What "improvising" looked like vs. what changes now

| Before                                                       | Now                                                                              |
| ------------------------------------------------------------ | -------------------------------------------------------------------------------- |
| CPA target changed 3x in 2 weeks                             | Max 1 change per 28-day cycle                                                    |
| Reacted to <2-week-old ad set data                           | No action on data younger than 28 days (except circuit breakers)                 |
| Creative + audience + target all touched near-simultaneously | One lever per cycle, logged                                                      |
| Manual pause on "looks bad"                                  | Automated pause only on Rule A (zero-result burn) or Rule B (mature $90 ceiling) |
| No record of what changed when                               | Every change logged with date/reason/owner                                       |

---

**Bottom line:** the $90 pause rule is a safety net for genuinely broken ad sets, not a performance judgment — it only fires past day 28 with real spend behind it. Everything else waits for the 28-day maturity window. That's the fix for the swinging: stop reading the scoreboard before the game's a quarter of the way done.
