# Budget Scaling Schedule: $500 → $2,000/day

## First, a correction on the premise

What you read isn't quite an "official Meta rule." Meta has never published a formal policy stating "raise budget 20% every 72 hours, guaranteed no learning-phase reset." What actually exists:

- Meta's Business Help Center says **learning phase can reset on "significant edits,"** and budget changes are one trigger — but Meta doesn't commit to a public numeric threshold.
- **"~20% is safe, 72h is the reset window"** is a heuristic repeated by Meta account reps and performance marketers so widely it's become industry folklore — useful, but not contractual. Actual algorithm behavior varies by account, audience size, and how volatile your signal already is.
- Even when learning phase *doesn't* technically reset, **CPA can still drift** from bidding into a thinner part of the auction — that's a delivery/auction effect, separate from the learning-phase mechanic entirely.

So treat 20%/72h as a **starting cadence**, not a guarantee — your own January/April/June data is a better predictor than the rule of thumb.

## The gap I can't fill without your data

You mentioned three prior bumps (+30% Jan, +15% Apr, +25% Jun) and that you can pull how CPA responded. I don't have those numbers. Before you execute past step 3 or 4 below, pull:

- Peak CPA reached after each bump, and days-to-recovery to baseline $38.
- Whether June's +25% (your largest single jump) caused worse degradation than April's +15% — that tells you if degradation scales linearly with jump size or if there's a cliff above ~20-25%.

If June's +25% already caused a rough patch, compounding eight 20% jumps back-to-back is materially more aggressive than anything this campaign has seen — the schedule below should be treated as a draft to stress-test against that history, not a final plan.

## The schedule

$500 → $2,000 is a 4x increase. At +20% per 72h, that's 8 steps (~24 days). Last step is capped to land exactly on $2,000 rather than overshoot to ~$2,150.

| Step | Date (starting today, adjust to your actual start) | Budget | Increase | Cumulative vs. $500 |
|---|---|---|---|---|
| 0 | Fri Sep 12 | $500 | — baseline | — |
| 1 | Mon Sep 15 | $600 | +20% | +20% |
| 2 | Thu Sep 18 | $720 | +20% | +44% |
| 3 | Sun Sep 21 | $864 | +20% | +73% |
| 4 | Wed Sep 24 | $1,037 | +20% | +107% |
| 5 | Sat Sep 27 | $1,244 | +20% | +149% |
| 6 | Tue Sep 30 | $1,493 | +20% | +199% |
| 7 | Fri Oct 3 | $1,792 | +20% | +258% |
| 8 | Mon Oct 6 | $2,000 | +11.6% (capped) | +300% |

Full ramp finishes **Oct 6**, ~7 weeks before Black Friday (Nov 27). That's intentional slack, not padding — see the timing note below.

## Decision gate at every step — don't advance on autopilot

Before each 72h bump, check trailing CPA:

- **CPA ≤ $44 (80% of max):** proceed to next step on schedule.
- **CPA $44–$55:** hold current budget for one extra 72h cycle before advancing. Don't increase and don't pull back yet.
- **CPA > $55 for 2+ consecutive days:** roll back one step (not to baseline), then hold 72h before trying again. Repeated failure at the same step means that's your real ceiling for now — stop climbing and report back with what broke (frequency spike, audience overlap, one placement dying, etc.).

Never cut budget and re-raise it within the same 72h window — that's the classic way to actually trigger a learning-phase reset, regardless of which single move you blame it on.

## Why the timing matters more than the rule

Two things your Jan/Apr/Jun history *can't* tell you: those bumps happened against normal-season CPMs. Nov–Dec CPMs typically run 20–40% higher industry-wide as every advertiser competes for the same holiday inventory — independent of anything you do with budget pacing. That means:

- Reaching $2,000/day by Oct 6 and holding there through October gives you a **clean read on how this campaign handles 4x spend before the holiday CPM inflation hits**, rather than conflating "budget scaling shock" with "holiday competition shock."
- Budget it now for a possibility: **$55 max CPA may not hold in peak BFCM week** even with zero scaling mistakes, purely from market-wide CPM pressure. Decide in advance whether you'll flex the ceiling temporarily during Nov 20–Dec 2 if AOV/margin supports it, rather than fighting the algorithm on CPA during the highest-value week of the year.

## What I'd do next

Send me the CPA trajectories from the Jan/Apr/June bumps (peak CPA and days-to-recover for each). If June's +25% single jump degraded CPA more than proportionally to April's +15%, I'd stretch this schedule to 96h or 120h steps instead of 72h for the back half — the steps above $1,000/day are where an account with limited scaling history is most likely to actually feel it.