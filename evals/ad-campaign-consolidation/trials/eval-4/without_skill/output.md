No web access granted, so this is based on established Meta Ads platform mechanics rather than a live doc check — flagging that up front since the numbers below (50 events/week, 20-30% daily budget delta) are Meta's long-standing published guidance but I couldn't re-verify they're unchanged today.

---

## Sanity check: this plan is risky for the exact week it's trying to protect

🔴 **Overall verdict: don't run it as written.** Every risky move is stacked into one 48-hour window, right before your highest-stakes week, with the fallback deleted before you know if it worked.

### The core problem: you're stacking three learning-phase resets into one weekend

Meta's algorithm re-enters "Learning Phase" on an ad set whenever you make a **significant edit** — and your plan does three of them at once:

1. **New targeting** on the 3 keepers
2. **Optimization event change** (add-to-cart → purchase) — this alone is a full reset, always
3. **A large budget jump** (100% of account budget landing on Sunday)

Any one of these resets learning. All three together means the algorithm is relearning delivery from a cold start, using a new signal (purchase, which is sparser than add-to-cart) — during the week traffic and competition both spike for Black Friday. That's the worst possible time to ask the algorithm to relearn anything.

### Switching to purchase optimization now, this way, is the biggest red flag

- Purchase-optimized ad sets need real volume — Meta's own guidance is roughly **50 purchase events per ad set per week** to reliably exit learning phase. If the account was optimizing on add-to-cart, that's usually a signal purchase volume wasn't dense enough to optimize on directly.
- Flip the event 12 days before Black Friday, on ad sets that haven't proven they can hit that purchase threshold, and you risk ad sets stuck in **"Learning Limited"** — inconsistent delivery, high CPA, right through your biggest week.
- This is a change you want **weeks** of runway on, not days, and definitely not bundled with two other changes.

### Moving 100% of budget in one day compounds it

Meta's pacing guidance is to cap daily budget changes at roughly **20–30%**, not jump straight to 100%, precisely because large jumps also disturb the auction/delivery that's re-stabilizing after an edit. Doing this on the same day the ad sets are already relearning from the targeting + optimization event change means you're asking a freshly-reset system to also absorb a 4x+ spend shock.

### Deleting the 5 losers on Monday removes your only safety net

- You'll have had **one day** (Sunday → Monday) of data before deleting the fallback campaigns — nowhere near enough to know if the new setup is working.
- Deletion also destroys the historical learning data on those campaigns, so if the 3 keepers underperform during BFCM week, there's no quick revert.
- "Keep the account tidy" is a January job. Nothing is gained by deleting on Monday vs. pausing and deleting in December — except losing the fallback exactly when you need it most.

### You won't be able to diagnose anything if it goes wrong

Targeting + optimization event + budget are three independent variables, all changed at once, then judged during a period (Black Friday) with its own seasonality distortion on top. If CPA spikes that week, you'll have no way to tell whether it's the new audience, the new optimization event, the budget shock, or just BFCM auction pressure. You'll be debugging blind during the one week you can't afford to.

---

## What I'd do instead

1. **Move the whole consolidation earlier, not later.** Make the targeting + optimization event changes to the 3 keepers now (or as soon as possible this week) — not "next weekend." You want the ad sets to have already exited learning phase, on the final structure, _before_ BFCM traffic hits, not during it.
2. **Split the two edits.** Change optimization event first, let it stabilize (watch for learning-phase exit, ~50 purchases/week/ad set), _then_ change targeting — or vice versa. Don't do both simultaneously.
3. **Ramp the budget, don't jump it.** Move budget over in steps of ~20–30%/day into the 3 keepers instead of 100% in one day. Gives the algorithm room to hold delivery stable while it absorbs more spend.
4. **Pause, don't delete, the 5 non-keepers.** Zero cost to keep them paused through BFCM as a revert path. Delete in December once the new 3-campaign structure has a full sales cycle of proof behind it.
5. **Give yourself a real observation window.** Aim for the new structure to be fully live and out of learning phase by ~Nov 18–20, so you have a genuine stability check before Black Friday week starts, not a same-weekend leap of faith.

Bottom line: the _direction_ of the plan (consolidate to 3 strong campaigns, optimize for purchase) is right. The _sequencing_ — bundle three resets into one weekend, judge it during Black Friday, delete the fallback the next day — is what turns a good idea into unnecessary risk during the account's most important two weeks of the year. Pull the timeline forward and add a real buffer instead.
