## Answer: Don't cut anything from this report. The "22% down" number is a measurement artifact, not a performance signal — the Evidence Gate stops it before it reaches a kill list.

Two separate problems compound here, and either alone would already block a verdict:

**1. The "total conversions" column is a category error.** Meta (7-day click), Google Ads (30-day click), and GA4 (last-click) count the same customer journey under three different rules — different windows, different models, one of them multi-touch-blind (last-click), two of them click-only. Summing them was never valid, even before anything changed. A campaign leaning on longer consideration cycles (which is normal for outdoor equipment — tents, packs, gear people research over days) gets more credit under a 30-day window than a 1-day one for identical buyer behavior. You can't rank campaigns against each other on a column built this way; the ranking reflects each campaign's platform/attribution mix, not its performance.

**2. The mid-month Meta setting change makes it worse, not just "also wrong."** Moving from 7-day to 1-day click on the 12th mechanically shrinks Meta's conversion count going forward — a shorter click window credits fewer conversions, independent of whether the ads got worse. Since the switch landed mid-month, every Meta-attributed number this month is itself a blend of two incompatible measurement regimes (pre-12th under the old window, post-12th under the new one), and it's being compared to a full prior month entirely under the old window. Any campaign that is Meta-heavy will show a mechanical decline in the total column this month that has nothing to do with ad performance. That's exactly the pattern that would land Meta-heavy campaigns in your "bottom 20%" and get them killed for a change your own team made, not for underperforming.

```
ROOT-CAUSE VERDICT - cobalt-gear, 2026-09-12
platform(s)    : Meta, Google Ads, GA4 | model: B2C/ecommerce
window         : this month vs last month (lag maturity matched: unknown - not stated)
volume         : not stated | reconciliation gap: unverified (no order-table join described)

decomposition  : not performed - the input metric itself is invalid, so no CPM/CTR/CVR/AOV read can be trusted yet
localisation   : not meaningful - "total conversions" mixes three incompatible attribution definitions per campaign

layer screen
  measurement/tracking : FAIL - conversions summed across 7-day click, 30-day click, and last-click; Meta's own
                          window changed 7-day→1-day mid-month, splicing two measurement regimes into one column [critical, high]
  structure             : unknown - cannot screen fragmentation/optimization-event validity until the metric is fixed [-, low]
  targeting              : unknown - same blocker                                                                  [-, low]
  creative               : unknown - same blocker                                                                  [-, low]
  bidding/budget         : unknown - same blocker                                                                  [-, low]
  offer & downstream     : unknown - same blocker                                                                  [-, low]
  external               : unknown - same blocker                                                                  [-, low]

confidence     : high (on the tracking FAIL itself) - the attribution-window mismatch and the mid-window
                 settings change are both stated facts, not inferred
verdict        : measurement/tracking - the reported total is a category error (summed incompatible attribution
                 windows) compounded by a mid-window Meta settings change; no downstream layer is readable yet
evidence       : three attribution models summed into one column; Meta's own window changed on the 12th,
                 inside the very month being compared to last month
findings       : 1) rebuild the report: report Meta, Google, GA4 conversions as three side-by-side columns,
                    never summed, until definitions reconcile
                    [critical, high, restores a readable signal for every later decision, a few hours, analyst]
                 2) hold Meta out of any month-over-month read until a full window exists entirely under 1-day
                    click on both sides of the comparison
                    [critical, high, removes the mid-window splice, near-zero - just wait, analyst]
                 3) reconcile each platform's conversions against the order table (revenue, not count) before
                    trusting any platform number
                    [high, medium, catches whether Meta/Google/GA4 are even close to shipped orders, a day, analyst]
findings deleted: none - nothing here is a confirmed root cause of a real decline yet; the "22% drop" itself
                 is deleted as a finding, since it is an artifact of the measurement break, not a performance fact
prediction     : once Meta is reported under a stable 1-day-click window for a full comparable month, the
                 blended total will likely show a materially smaller decline than 22% - because part of the
                 apparent drop is the window shrink itself, not lost conversions
handoff        : mbfinotti/advertising-skills@ad-attribution-gap (quantify how much of the 22% is the window
                 change vs real); mbfinotti/advertising-skills@ad-conversion-tracking (fix the report structure)
re-check       : first full calendar month entirely after the 12th, once Meta, Google, and GA4 are reported
                 unsummed and Meta is measured on a stable window both sides
```

**What this means for "cut the bottom 20% this week":** that ranking cannot be trusted this week, full stop. Any campaign that looks like a loser right now may just be the campaign with the most Meta 7→1-day click conversions in last month's baseline. Killing on this data risks cutting campaigns that are actually fine and keeping ones that aren't, based on which attribution mix each one happened to carry.

**What to do instead this week, in order:**

1. **Split the report into three columns** (Meta / Google Ads / GA4), never summed. Takes an analyst a few hours, and it's the only thing that makes any ranking below trustworthy again.
2. **Re-run the month-over-month comparison per platform separately**, not blended. For Meta specifically, don't compare this month to last month at all yet — compare Meta's post-12th days only, against an equivalent stretch from before, if you can pull a 1-day-click view historically; otherwise wait for a full month under the new setting.
3. **Reconcile against your own order table** (revenue and order count, not platform-reported conversions) — for a B2C ecommerce account this is the actual source of truth, not any ad platform's count. If a campaign's associated revenue in your own backend is genuinely down, that survives the attribution mess; if it's not, the platform number was lying to you.
4. **Only after that**, rank campaigns by their own platform-native metric against their own history (CPA or ROAS trend within Meta, within Google, within GA4-sourced channels) — never mixed, never against industry benchmarks — and then cut the bottom 20% of _that_ clean ranking, if a real decline survives.

If there's commercial pressure to cut something this week regardless: the only defensible move is to pause campaigns with a real, backend-confirmed revenue decline that predates the 12th and shows up consistently in a single platform's own history — not campaigns identified only by their position in the current blended "total conversions" column.
