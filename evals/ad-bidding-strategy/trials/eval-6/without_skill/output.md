## The framing is wrong — this isn't a manual-vs-automated fight

Both camps are debating the bidding *mechanism*. The actual problem is the *optimization signal*. Automated bidding does exactly what you told it: get cheap form fills. It has no idea a form fill from a job seeker is worthless and one from a facilities director is worth $80K ARR. Manual bidding wouldn't fix that either — a human bidding manually on the same "form fill" goal, across the same broad keywords/placements, would drift toward the same junk traffic over time, just slower and more expensively. Reverting throws away a real 30% CPA gain to solve a problem manual bidding doesn't actually solve.

## What's really happening

Smart/automated bidding (Target CPA, Maximize Conversions, PMax) hill-climbs toward whatever conversion event you feed it, using whatever signals correlate with that event — device, time of day, broad-match query expansion, Display/Discovery/YouTube inventory, PMax asset-group expansion. None of those signals know "facilities director at a university." So it found cheaper, higher-volume ways to trigger "form submitted" — likely broad-match queries about "facilities management" (a course topic, a career path) or expanded placements, not necessarily worse targeting everywhere.

## Diagnose before deciding anything

1. Pull 6 months of form-fill leads, join with SDR disposition (MQL/SQL/junk) by campaign, ad group, keyword, and placement/asset group.
2. Check whether junk concentrates in specific segments (broad match, Display/YouTube, PMax expansion) or is spread evenly.
   - **Concentrated → targeting problem.** Fix with negative keywords, audience/placement exclusions, tighter PMax inputs. Keep automated bidding.
   - **Even spread → signal problem.** The algorithm is optimizing the wrong goal, full stop, regardless of mechanism.

Most likely answer is "both, but mostly signal" — that's the pattern in almost every case like this.

## The actual fix: change what the algorithm optimizes for, not how it bids

- Stop optimizing to raw form fill. Feed the platform a downstream qualification signal via **offline conversion import** (Google Ads Enhanced Conversions for Leads, LinkedIn CRM sync, etc.): SDR marks a lead "SQL-qualified" or "disqualified" in CRM within 24–72h, that status gets imported back as the primary conversion action.
- You don't need to wait for the 4-month sales cycle to close deals. SQL qualification happens in days. That's fast enough to retrain the algorithm without losing volume for months.
- Keep raw form fill as a secondary/observation action only, not the bid target.
- Add a self-qualifying gate on the form itself (job title, institution type, seniority, or a "are you evaluating this for your institution" screen) — cheap, immediate, filters students/job seekers before the SDR ever touches the lead, and doubles as an extra signal for the algorithm.

## How to settle the internal argument

Don't debate it — test it, on the metric that matters:

1. Run a **holdout, not a full reversion**: carve off 10–20% of spend into a manual-bidding control cell, keep 80%+ on automated but switched to the SQL-import signal.
2. Measure **cost-per-SQL** and **SQL rate**, not cost-per-form-fill, for 4–6 weeks minimum.
3. Whichever cell wins on cost-per-SQL (and ideally pipeline $ created) wins the argument — not "trust the algorithm" ideology, not "black box" distrust.
4. Full pipeline/revenue read will take the full 4-month cycle, so treat SQL rate as the interim decision metric and revisit CAC-to-LTV once enough cohorts close.

## Bottom line

Don't go back to manual bidding. Fix the conversion signal you're feeding the algorithm (SQL-qualified import, not raw form fill), add a self-qualification gate on the form, and run a small holdout test measured on cost-per-SQL to settle the internal debate with data instead of vibes.