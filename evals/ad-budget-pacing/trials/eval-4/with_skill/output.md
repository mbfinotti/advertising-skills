# Pacing check: Meridian Outdoors × Alpine Media Group IO

## The numbers

```
period          : Oct 5 - Nov 15, fixed flight | day 28 of 42, 14 remaining (week 4 just closed)
committed       : 8,000,000 impressions (hard commitment, guaranteed IO)
buy type        : guaranteed / IO-based

metric                          flat curve
expected to date                5,333,333   (elapsed_share = 28/42 = 0.667)
delivered to date               4,900,000
pacing ratio                    0.92        (4.9M / 5.333M)
projected end-of-flight         7,350,000   (4.9M / 28 days × 42 days)
projected shortfall             -650,000    (-8.1% of commitment)
remaining commitment            3,100,000
required daily (14 days left)   221,429 impr/day
trailing daily (last 4 weeks)   175,000 impr/day
adjust delivery by              +46,429 impr/day (+26.5% over trailing rate)
```

No weighted (day-of-week/seasonal) curve was run — there's no 2-3-cycle delivery history for this account, so the flat curve is the right tool here, not a shortcut (per the skill: default to flat alone when history is thin).

**Gate check — does this deviation survive, or is it noise?**

- Not a single-day overdelivery artifact — this is a 4-week cumulative trend.
- Not a first/last partial day — you're at day 28 of 42.
- Denominator isn't trivial — 28 elapsed days is a solid read.
- Not too early to judge — you're two-thirds through the flight.
- No budget edit / relearning window in play.
- These are finalized week-4 numbers, not an intra-day snapshot.

It survives. This is a real gap, not something the delivery mechanics explain away.

**One wrinkle on severity**: 0.92 sits just inside the generic 0.90-1.10 "on-pace" convention, so by that band alone this wouldn't even fire an alert. But that convention is built for auction pacing, where 90-110% is genuinely fine. On a **guaranteed IO**, the standing practice is to hold delivery slightly _ahead_ of prorated, not just inside a tolerance band, because there's no "good enough" on a fixed impression commitment — either 8M lands by Nov 15 or it doesn't. Judge this one against the commitment, not the convention.

## Diagnosis

The diagnostic checklist (budget-capped, bid-capped, audience size, disapprovals, billing, tracking, auction cost, schedule, frequency caps, learning phase) is built for auction-bought delivery you can inspect account-side. You don't operate this account — it's Alpine's guaranteed inventory — so the cause sits with them, not with a setting you can check. What you _can_ diagnose is the process failure: Alpine let four weeks of a hard-commitment flight run 8% behind without flagging it. Under the IAB Direct Buy Addendum (effective Feb 2026), the seller carries a duty to promptly notify the buyer of material under-delivery. Silence until your analyst caught it, followed by an unprompted credit offer, reads as Alpine already knowing the number and choosing the cheapest remedy for them rather than the one that fulfills the buy.

## Should you take the credit?

**Not yet, and not as offered.** Walk through why using the remedy hierarchy for a running guaranteed IO:

```
efficiency (= value): accelerate > make-good flight > credit
effort:                make-good flight > credit > accelerate
compliance cost:       make-good flight == credit > accelerate
```

- **Accelerate** is the default while runway remains, and you have 14 days left — real runway, not the flight's final stretch. It buys back the _actual inventory you contracted for_ (audience reach in front of camping-gear buyers ahead of the season you bought this flight for), at zero renegotiation cost, reversible if it doesn't work.
- **Credit** is the fallback the terms guarantee _when a make-good negotiation fails_ — not the first move, and not something you accept before acceleration has even been tried. Taking it now means:
  - You get cash back on undelivered inventory instead of the impressions you actually wanted delivered — the reason "clean and easy" is doing a lot of work in the framing. A DTC brand running a flight for seasonal reach doesn't want a rebate line item, it wants the eyeballs.
  - It closes the flight instead of fixing it, foreclosing the 650K-impression recovery that's still achievable with 14 days left.
  - You have no visibility yet into whether Alpine's offered credit is even priced at full contracted value per impression, or discounted.

The credit isn't "wrong" as an eventual fallback — it's premature as a first response to an offer that conveniently skips the two remedies that would actually cost Alpine more effort.

## What to do with the remaining two weeks

**1. Push acceleration first, today.**

- current → proposed: 175,000/day trailing → 221,429/day required
- affected: all placements/line items under this IO
- rationale: closes the full 650K shortfall inside the existing flight without a contract amendment
- expected effect: +26.5% daily delivery closes the gap by Nov 15; uncertainty is Alpine's available inventory headroom at that rate — ask them directly whether they can sustain it
- owner: your analyst monitors Alpine's daily delivery against the 221,429/day bar; Alpine's account rep executes the acceleration
- verification date: end of week 5 (~Nov 8) — by then you should see delivery tracking to the new rate; recompute `adjust_spend_by` daily rather than waiting, so any residual gap stays small instead of piling into a final-week dump (a last-days surge to hit the number is a failure mode in itself — it buys worse inventory and reads as a rescued number, not a healthy pace)
- rollback trigger: if week 5 delivery doesn't move off the ~175K/day trailing rate, acceleration isn't happening — stop waiting and move to step 2

**2. If acceleration stalls, escalate to a make-good flight**, not straight to credit — a short extension past Nov 15 delivering the residual impressions. This is the remedy that still gets you the audience, just later. Negotiate it now, in parallel with monitoring acceleration, so you're not starting a negotiation cold with three days left.

**3. Only fall back to the credit if a make-good is operationally impossible** (e.g., Nov 15 is a hard campaign-end date you can't move for seasonal reasons). If you get there, don't just accept "whatever ends up undelivered" — get it quantified against the negotiated CPM for the exact shortfall, in writing, referencing the IO's under-delivery clause, before the flight closes.

**4. Separately, put the disclosure lapse on record with Alpine**, independent of which remedy you land on. They had a duty to flag this at 8% behind and didn't; that's a partner-reliability data point for your next IO negotiation (renewal terms, audit cadence, whatever leverage you want), not something a credit offer should quietly absorb.

**Bottom line: don't take the money yet.** You have runway to get the impressions you actually bought — use it, hold Alpine to acceleration first, keep the credit as the last-resort fallback it's supposed to be, and log the notification failure regardless of how this flight resolves.
