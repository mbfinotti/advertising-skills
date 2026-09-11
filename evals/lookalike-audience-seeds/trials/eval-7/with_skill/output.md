# Recommendation: Keep the new seed running. Don't swap tomorrow.

## Why "72% match rate = solid seed" is the wrong read

⚠️ Match rate is a data-hygiene signal, not a quality signal — in either direction. Meta's own guidance: a high match rate means the data was clean, not that the audience will perform. It can't be used to defend the seed any more than a bad CPA can be used to convict it.

## Why "CPA 40% over target, day 5 = bad seed" is also the wrong read

🔴 **You're reading inside the learning phase.** Meta's own benchmark is ~50 optimization events/ad set/week, or 2–4 weeks at low volume, before a CPA read means anything. Five days is noise. Swapping tomorrow grades the seed before the account has accumulated enough signal to grade it — this is the skill's named trap ("judging a seed inside the learning phase"), and it's exactly what you're about to do.

## The real problem: you don't have a baseline

⏳ Cohort LTV has never been measured on this account. Per the pass rule this skill runs on — *90-day acquired-customer cohort LTV must meet or beat account-average LTV, at equal-or-better CPA* — an unknown baseline means **neither seed can be graded yet**. Treat the current run as the baseline-building run, not a verdict.

## The old seed is not a safe fallback — it already failed

This is the named "Churney" pattern, verbatim: good CPA, but the seed scaled low-margin/discount-only converters, and 90-day LTV was weak. The skill's own fix for that symptom is explicit: **re-seed on margin or predicted LTV, retire the seed version.** That seed was already disqualified by finance's finding, independent of anything the new seed does. Reinstating it tomorrow reintroduces a known-bad seed to chase a 5-day CPA number that hasn't cleared the learning phase.

## Your head-to-head plan needs a fix before it runs

❌ Two ad sets, naive comparison, will not give you a clean read — audience overlap between two lookalikes drawn from the same customer base contaminates it. Use Meta's actual user-level A/B test (Experiments), not two co-running ad sets.

🎯 And this decision — retiring vs. reinstating a seed version — is exactly the case the skill flags for escalating past even a proper split test toward a **geo holdout**: expensive to reverse, and the CPA read itself is what's in dispute. If the split test's result gets challenged again in 3 months, you'll wish you'd held a market out from the start.

## What to actually do

1. **Leave the new seed live.** No swap tomorrow.
2. Confirm the negative-selection pass (refunders, discount-only buyers, employees, wholesale) was applied when this seed was built — if it wasn't, that's a real, fixable issue, independent of the CPA number. 40%-off-code buyers polluting the *old* seed is documented; nobody has checked whether they're in the *new* one.
3. Let it clear the learning phase (~2–4 weeks from launch, ~Sept 7) before reading CPA as signal — earliest honest read: **~Sept 21–Oct 5**.
4. Don't build a two-ad-set test against the old seed. It's already retired per the Churney rule. Testing against it just re-risks the thing finance already caught.
5. If you want a real comparison, test the current seed against a **new, value-based re-seed** (margin or predicted LTV, never cumulative revenue) — a legitimate second candidate, not the disqualified one.
6. Set the first real checkpoint at **90-day cohort LTV**, launch + 90 days → **~Dec 6, 2026**. That's the date this seed gets graded against account-average acquired-customer LTV, at equal-or-better CPA.
7. Until then, judge only on: match quality (already fine, don't re-check it), delivery/serving health, and directional engagement — not CPA, not LTV.

## Bottom line

🎯 Keep the new seed. It hasn't failed anything — it just hasn't been measured yet, because nothing on this account ever has. The 40%-off seed already failed the metric that matters and should stay retired regardless of what the new one does this week.