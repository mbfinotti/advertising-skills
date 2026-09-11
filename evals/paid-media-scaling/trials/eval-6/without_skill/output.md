No — I'd push back hard on this plan. Three of its own assumptions work against each other.

**1. Seven conversions is noise, not a signal.**
With n=7, one unusually expensive lead can swing "CPA" by 30-50% on its own. You don't have a doubled CPA — you have a small sample that happens to look like one. Nothing about that number is actionable yet.

**2. You changed budget AND you're 5 days in — that combination is expected to look bad, independent of anything being wrong.**
Doubling daily budget is a >20% budget change, which resets Smart Bidding's learning phase (if you're on Target CPA/Maximize Conversions — worth confirming). Google's own guidance is 1-2 weeks and ~30 conversions before learning-phase volatility settles. You're 5 days and 7 conversions in. The CPA spike you're reacting to is very likely the learning-phase artifact itself, not evidence the account is broken.

**3. Click-to-booked-job is 3 weeks — so "CPA has doubled" isn't even measurable yet.**
Whatever conversion event you're counting today (lead vs. booked job matters — which is it?), clicks from the Sept 3 budget change won't fully mature into booked jobs until ~Sept 24. Any verdict before then is judging an unfinished funnel. This is the strongest argument for *not* making a big irreversible call today.

**4. "Kill it, then one fix per day" defeats its own stated goal.**
You said the point is to isolate what works — but:
- Killing (deleting, not pausing) throws away the Smart Bidding history the algorithm needs to warm-start again, so the relaunch re-enters a fresh learning phase too.
- Stacking a new change every 24 hours means each change gets judged before its own learning-phase volatility clears, and before it can accumulate anywhere near enough conversion volume. You'd be layering three sources of noise on top of each other and attributing whatever happens to whichever lever you pulled last. That's not isolation, it's guesswork with extra steps.
- Also worth a sanity check outside the account: roofing leads are storm/weather-driven. Did anything change in demand (weather events, competitor spend) around the 3rd that has nothing to do with your budget?

**What I'd do instead:**
- Don't delete. **Pause is reversible, delete is not** — if you do pause, pause, don't remove, so Smart Bidding data survives.
- Rather than pausing, consider just **rolling the budget back toward $800-1,000/day** rather than a full kill — a controlled step down is a smaller shock than kill-then-relaunch-from-zero, and keeps data flowing.
- Hold that one state for **1-2 weeks or ~30 conversions**, whichever comes later, before judging.
- Track **lead volume and lead quality**, not just CPA, during the hold — CPA is the least reliable metric at n=7.
- If you still want to test levers (location, headlines, bid target), change **one at a time, with a 1-2 week hold each**, not one per day. Three sequential 24-hour tests on ~1-2 conversions/day each will not produce a readable signal.
- Separately confirm what "conversion" means in your CPA number — lead form fill or actual booked job. If it's the former, your real CPA-per-booked-job won't be knowable for another ~3 weeks regardless of what you do to the campaign this week.

The instinct to isolate variables is right — the execution (kill + daily swaps) is set up to produce three confounded, underpowered mini-experiments instead of one clean one.