# Budget Pacing Report — Juniper Financial (Meta), 2026-11-11

**Bottom line first: don't send an over-pacing alert today, and don't make a third budget edit today either.** The $3,850 reading fails two of the skill's false-alarm gate checks before it ever gets to a diagnosis. Below is the full report, why it's suppressed, what to tell the client instead, and exactly how to size the cut once it's actually safe to make one.

## Pacing report

```
BUDGET PACING REPORT - Juniper Financial, Meta, 2026-11-11
period : calendar month 2026-11-01 -> 2026-11-30 | day 11 of 30, 19 remaining
budget : $9,000 (commitment type not confirmed - assumed target, not hard commitment)
buy    : auction (assumed - no IO mentioned) | model: not confirmed (B2B/B2C)

metric                        flat curve (provisional, intra-day)
expected to date              $3,300
spend to date                 $3,850  <- this morning's live dashboard figure
pacing ratio                  1.17  (matches your own 17% figure)
projected period spend        $10,500
budget utilization            42.8%
remaining budget              $5,150
required daily spend          $271/day
trailing 7-day avg daily      not computable - no daily-level breakdown provided
adjust spend by                not computable - see below

status     : SUPPRESSED - does not clear the false-alarm gate (see below)
suppression: gate check 5 (edit landed inside the relearning window) AND
             gate check 6 (figure is intra-day / unrestated)
diagnosis  : learning-phase / edit-reset volatility, not a genuine spend problem
recommend  : no budget change today; re-pull and re-check per the plan below
owner      : you | next check: after pulling yesterday's finalized spend (see below)
```

No weighted curve is shown - that needs 2-3 cycles of this account's own delivery history to build an index, and this isn't the moment to build one with a client deadline today. Flat curve alone is the correct default here (skill: "flat alone when history is thin or the answer is due today").

## Why this doesn't clear the gate

Two of the six false-alarm checks fail, and either alone is enough to suppress the alert:

**Gate check 5 - budget edit inside the relearning window.** You cut the daily budget 15% two days ago (Nov 9). That is almost certainly still inside Meta's relearning/settle window - Meta's own pages document that budget edits trigger relearning, though they don't publish an exact day count; the practitioner convention is roughly 3-7 days before delivery restabilizes. Two days post-edit, what you're seeing is very likely the _edit_ talking, not the _pacing_. On top of that, this Nov 9 cut landed only six days after the Nov 3 increase - the account may not have even finished settling from the first edit before the second one landed.

**Gate check 6 - the figure is intra-day.** "This morning's" $3,850 is a live, unrestated number. Dashboards lag and get restated; the skill's daily check is built to read _yesterday's finalized_ spend, never today's running total. Comparing a partial Nov 11 to a full elapsed-day denominator is exactly the mechanical trap that produces false alarms.

**One correction to flag, since it's load-bearing for what you do next:** the "20% budget change resets Meta's learning" threshold you cited is folklore, not a documented Meta rule - it appears in no Meta documentation, which ties reset risk to unquantified "magnitude of the change" instead. Your own account just demonstrated this directly: you deliberately stayed under 20% on the Nov 3 increase and delivery still got choppy. That's evidence against the 20% line, not for it. Treating any large edit cautiously is still the right instinct; the specific number just isn't a platform guarantee you can rely on to rule out relearning.

## Diagnosis

Reading the evidence you have (a full status/constraint-pair sweep isn't available from a chat conversation - that's on you to pull from Ads Manager):

- Two edits in eight days (+18% Nov 3, -15% Nov 9), the first followed immediately by "choppy" delivery - textbook learning-phase / edit-reset signature, not a budget-capped, bid-capped, or auction-shift signature.
- You're now two days past the second edit, looking at a hot number, and about to make a third edit. This is precisely the failure mode the skill calls out: _"Correcting through a relearning window - the correction's own volatility then reads as a new anomaly, inviting a second correction."_ A third edit inside eight days would compound the instability you're trying to fix, not resolve it.

## What to send the client today (instead of an over-pacing alert)

An "over-pacing alert" implies a confirmed problem with a sized correction. You don't have either yet - what you have is a live number two days into a relearning window. Send a status note instead:

---

**Subject: November Meta pacing — status check, no action needed yet**

Hi [Client],

Quick pacing update for November. Spend is running slightly ahead of the flat monthly pace as of this morning, but I'm not treating that as a signal yet — we made a budget adjustment two days ago (Nov 9) to smooth out some delivery volatility, and Meta's delivery system is still settling from that change. Reading pacing off live numbers during a settle window produces false alarms more often than real ones.

I'll re-check against yesterday's finalized spend once the account has had a few more days to stabilize, and will follow up by [target date, see below] with either an all-clear or a sized correction. No action needed on your end in the meantime.

Best,
[You]

---

## The plan to actually size a cut

Don't guess at a cut size off today's numbers. Do this instead:

1. **Wait for the settle window.** Hold off on any further budget edit until roughly **Nov 13-14** (4-5 days after the Nov 9 cut) - practitioner convention, not a platform-guaranteed date, but the shortest reasonable wait given you're compounding two recent edits.
2. **Re-pull on yesterday's finalized number**, not today's live one. On the day you check, use `spend to date` = Ads Manager's restated total through the prior full day, and `days elapsed` = full days only.
3. **Pull daily-level spend for the trailing 7 days** before computing anything - I don't have that breakdown from what you gave me, and `adjust_spend_by` (the number that actually matters) needs it:
   ```
   required_daily   = (period budget - spend to date) / days remaining
   adjust_spend_by  = required_daily - trailing 7-day average daily spend
   ```
   That signed delta is the deliverable - not the pacing ratio, and not a round number pulled from the deviation size.
4. **Run the status sweep first** (budget-limited / learning-limited flags, impression share lost to budget vs. rank) before touching the budget again. If the account is still shown as learning-limited or the loss is to _rank_ rather than _budget_, a budget cut won't be the right lever regardless of pacing.
5. **If it's still hot after the settle window and the sweep points to budget as the real constraint**, make one small, reversible cut - not a round "let's take off 15% again" - sized off the formula above, and then hold your hands off it through the next settle window.

The pattern to break here: three edits in ten days is a scale-down spiral, and every edit resets the clock on the next reading. One clean read after the window closes, with a properly sized number, ends the spiral instead of extending it.
