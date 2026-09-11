# Brightlark Go/No-Go Rules — 6-Ad Batch Test (launch Mon 2026-09-14 → decision Mon 2026-10-12)

## Read this first: the rule you proposed isn't Hott's, and mixing it with cost caps cancels itself out

The "spend 1× CPA before judging / 3× CPA before killing" rule is **untraceable folklore** — it circulates on agency blogs with no identifiable originator, and it's often *mis*-attributed to Barry Hott specifically. Hott's actual published position is the opposite: he explicitly rejects per-ad CPA kill rules ("ad-level CPA and ROAS is irrelevant") and instead judges new ads by comparative benchmarking against a maintained library of best-ever ads — a method that needs a weekly reviewer and a benchmark set you don't have time to run solo, checking twice a week.

Separately: "let the platform's cost caps kill losers automatically, no manual rule" is Andrew Faris's anchor — and a hard decision date (your Oct 12 feature deadline) is specifically named as one of the two conditions that rules Faris out, because it optimizes for a portfolio outcome with no per-ad element-level read and answers "never." You need a decisive list of winners by a fixed date, not a philosophy of never pausing.

So: not Hott, not Faris. What you actually described — a numeric kill at 2× CPA with no conversion, a numeric scale rule, checked periodically — **is Dara Denney's anchor**, word for word. It's also the one that needs nothing you don't already have (no benchmark library, no standing reviewer, no trusted split-test infrastructure), which matches solo + twice-a-week. I've built the plan on Denney, with a platform cost cap layered in as a *safety net between your check-ins*, not as the decision rule itself.

## Assumptions I made to ship this before Monday — confirm/correct these

| # | Assumption | Why it matters | Confirm by |
|---|---|---|---|
| 1 | The $30 CPA event is a subscription start or trial start, not a raw install | The $60 (2×) kill threshold must apply to the *same* event as your $30 CPA — if "install" in your message means literal app install (usually $1–5 for a meditation app), the numbers below are off by an order of magnitude | Mon |
| 2 | Platform is Meta (paid social) | Naming convention, "cost cap," and automated-creative-optimization toggle are Meta terms below — swap for TikTok/Google if wrong | Mon |
| 3 | $18k/month is the whole account, not a protected test budget | Determines how much of the $250/day-per-cell below is genuinely "new" spend vs. reallocated from what's already running | Mon |
| 4 | You have a current champion ad already running, to serve as control | A test with no concurrent control just compares the new batch to its own history — not valid (see caveats) | Mon |
| 5 | Advantage+ Creative / dynamic creative optimization is off (or can be turned off) for this batch | If it's on, the platform recombines/reallocates spend across your 6 assets itself and no cell-level read is possible | Mon |
| 6 | No specific creative rationale given, so the hypothesis below is a placeholder | Fill in the "because ___" — what's different about this batch vs. the champion, and by how much you expect it to move CPA | Before you write it down as final |

## The feasibility math — why this must be a screening test, not an A/B test

- $18k/month is under the $20k/month threshold where statistical significance becomes reachable at all. At this spend, the honest answer is: **proxy-gated screening, not a significance-tested winner.** Say that out loud to yourself before Oct 12, so a noisy ranking doesn't get reported as "the winner at 95% confidence."
- Stable-delivery floor per cell ≈ target CPA × 50 ÷ 7 = **$214/day**. Below that, a cell's numbers are unstable no matter what the sample math says.
- Recommended structure: **2 cells**, run concurrently, $250/day each (~17% above the floor):
  - **Control** — current champion ad(s), same budget, same structure.
  - **Challenger** — all 6 new ads in one ad set, automated creative optimization off.
- Projected over 28 days: ~233 conversions per cell (250/30 × 28). Checking the sizing table against a plausible ~5% baseline conversion rate, resolving even a large 50% relative lift needs ~1,500/cell — you're nowhere near that. **Verdict: Directional read**, both at the cell level (champion vs. new batch) and the asset level (~39 conversions/asset average, ranking only, not significance).
- Total dedicated test spend: ~$14,000 over the 4 weeks, inside your existing $18k/month — leave the remainder on whatever's already proven.

## The kill rules — the actual deliverable, checked at your fixed twice-weekly logins only

**Pick two fixed days now** (e.g. every Tue and Fri) and only ever apply these rules on those days. Checking off-schedule and reacting to a bad morning is exactly the peeking that inflates false kills — the whole point of writing this down is that you don't have to resist that temptation in real time.

**Never evaluate before Day 3** (launch Mon → earliest look Thu).

**KILL — asset level, any check-in from Day 3 on:**
- Spend ≥ **$60** (2× target CPA) with **zero conversions** on that specific event → kill the ad. *(This is your instinct, correctly sourced to Denney, not the folklore rule — keep it, it's a real anchor.)*
- CTR/hook rate sustained below 50% of your account's trailing median, by placement, across two consecutive check-ins → kill. This is a gate metric: it screens out obvious duds, it never crowns a winner on its own — a high CTR with a bad CPA usually means an offer or landing-page problem, not a creative one. Send that ad to iterate, not kill.

**SCALE — cell or asset level:**
- Any ad at or below $30 CPA at a check-in → raise its budget **+50–100%**, done a maximum of **2–3 times** across the 4 weeks, at least several days apart.
- Treat the first budget bump as its own read — don't stack a second increase on data collected mostly before the first one. A cheap early winner's numbers commonly regress once spend goes up; that's not the ad failing, it's the small sample from before catching up with reality.

**ITERATE — hold, don't judge yet:**
- Any ad that hasn't hit the kill trigger and hasn't hit the scale bar just sits until the next scheduled check-in.

**Automation backstop (this is your cost-cap ask, scoped correctly):**
- Set a cost cap / cost-per-result goal at **~$42/ad** (1.4× target CPA) at the ad or ad-set level. This throttles a runaway ad between your Tuesday and Friday logins — it does not make the kill/scale call for you. The manual 2×CPA rule above is still what actually kills something; the cap is just there so nothing burns badly out of control on the days you're not looking.

**Hard stop — pre-declared now, not decided at readout:**
- **Monday, Oct 12, 2026**, or ~40 conversions accumulated per surviving asset, whichever comes first.
- If nothing in the new batch beats the champion's baseline CPA by then: **keep the champion**, and feature only whichever new ad(s), if any, are at or below $30 CPA — don't push a loser into the feature window just because the calendar says to.
- "Winning batch" for the App Store push = whatever survives to Oct 12 without a kill and clears $30 CPA — could be 1 ad, could be all 6.

## Two things not in your original ask, worth 30 seconds

- **Wellness/health claims**: if any of the 6 creatives reference anxiety, sleep, or stress relief, check they're substantiation-safe under your ad platform's health-claims policy before Monday — this is the kind of thing that gets a whole batch disapproved mid-test, not just one ad.
- **Divergent delivery**: even a clean concurrent-control setup like this one is a relative, in-platform read — the algorithm can show your control and challenger to differently-optimized user mixes in ways you can't see. Treat the Oct 12 ranking as the best available screening signal, not causal proof. For a $30-CPA subscription app at this spend level, that's the correct level of confidence to act on — just don't oversell it to yourself later.