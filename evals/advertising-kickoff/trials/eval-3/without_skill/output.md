## Where this lives in the repo — and why I can't point you to a skill

I checked `skills-affiliation` end to end (everything except `skill-wip/`, which I was told to leave untouched). Two things worth flagging before the actual answer:

- **This repo doesn't contain skills at all.** Per its own README: *"This repository does not contain the skills themselves"* — it only tracks affiliate programs and which skill uses which. The actual skill content (including any advertising/paid-media skill) would live under `skill-wip/<owner>/<repo>/`.
- **I did not open `skill-wip/`**, as instructed, so I can't tell you whether a matching skill already exists there or is still a stub. If one does exist, it may already handle part of what you're asking.
- Everything else I *can* see is unrelated: `memory/naomakers/` is event-ops knowledge (hackathons, sponsors, run-of-show) — nothing on CAC, pacing, or bid strategy. `research/2026-08-24-priority-skills-advertising-crm-sales.md` is just a list of third-party skills.sh listings (`ads-budget`, `paid-ads`, `google-ads-manager`, etc.) kept as a reference for *building* a future skill, not something usable today.

So: no skill in the accessible part of this repo handles any of your three asks. Ask the repo owner whether an advertising skill already exists in `skill-wip/`; if not, here's the framework directly, in the order I'd actually run it.

---

## Order of operations

1. **Kill switch first.** Fix the Dec $18k weekend before anything else — it's the only item with real tail risk.
2. **Weekly pacing cadence** — the mechanism you'll use every Friday from here on.
3. **tCPA calibration** — check the dial before deciding to turn it up.
4. **Scale-up case for next quarter** — last, because it depends on 1–3 actually holding.

---

## 1. CAC rule and kill switch (the VP's #2 ask, do this first)

Write this down and get finance + VP sign-off — it's a policy, not a suggestion:

- **Max allowable CAC** = target payback period × monthly gross margin per customer. Example: if a customer nets $400/mo margin and you require payback in ≤6 months, max CAC = $2,400. Plug in Loomhaven's real ACV and margin — don't reuse a generic SaaS benchmark.
- **Soft threshold (review, don't pause):** blended CAC > 1.2× target, trailing 7-day window.
- **Hard threshold (auto-pause):** blended CAC > 1.5× target, trailing 7-day window, **or** any single day's spend > 15% of the monthly budget ($6,750 on a $45k month) with zero attributed conversions by end of day.
- **The Dec $18k weekend was almost certainly a pacing/automation gap, not a targeting gap** — holiday weekends have thin staffing, lower conversion propensity, and campaigns left on standard/maximize-conversions bidding with no daily cap. The rule that would have stopped it:
  - Every campaign gets a **hard daily budget cap**, not just a monthly one — never rely on Google's monthly pacing alone.
  - **No unattended automated bid-strategy changes** (e.g., Target CPA auto-adjustments, Performance Max budget reallocation) run over Fri evening–Mon morning without a human checking Friday's pacing snapshot first (see #2).
  - A **standing calendar block** the Friday before any 3+ day weekend to explicitly set weekend caps low, or pause non-core campaigns, rather than trusting defaults.
- **Who can override the pause, and how fast:** name a single owner (you, presumably) with pause/unpause authority, and require a second person's sign-off to *raise* the CAC ceiling — never to lower it.

## 2. Weekly Friday pacing check (the VP's #3 ask)

- **Daily budget target** = $45,000 ÷ days in the month (not ÷ 4 weeks — months aren't 28 days). For a 30-day month: $1,500/day.
- **Every Friday, compute:**
  - `expected spend to date = daily target × calendar days elapsed`
  - `actual spend to date` (pull from platform, blended across channels)
  - `variance % = (actual − expected) / expected`
- **Decision bands:**
  - within ±10% → on pace, no action
  - +10% to +25% → **burning too fast**: tighten daily caps for the remaining days so you land at $45k, don't just let it ride
  - beyond +25% → treat as a kill-switch-adjacent event, escalate same day, don't wait for next Friday
  - −10% to −25% → **burning too slow**: check for a delivery blocker (disapproved ads, exhausted audience, bid too low) before assuming you're "saving" money — underspend against a fixed monthly budget is not a win, it's wasted headroom you can't get back once the month closes
  - beyond −25% under → same, escalate
- Log this weekly in one running sheet (date, expected, actual, variance, action taken) — that log is also your evidence base for the Q1 scale-up ask.

## 3. Is tCPA set right? (calibration, do before touching budget)

tCPA targets drift wrong for one of three reasons — check in this order:

1. **Not enough conversion volume.** Google's Target CPA bidding needs ~30 conversions/campaign in a rolling 30-day window to have a stable signal. Below that, the algorithm is guessing, and any CAC swing you see is noise, not signal — don't retarget off it.
2. **Conversion lag mismatch.** If your sales cycle (demo → close) runs longer than your attribution/conversion window, tCPA is optimizing on a leading proxy (e.g., demo booked) that may not track close rate. Check: has your lead-to-close rate been stable, or has "cheap CAC" recently come with worse lead quality?
3. **Target stale vs. reality.** Compare *actual trailing-30-day CAC* to the *tCPA you've set* — if actual has been running consistently 15%+ below target for 3+ weeks (which is what triggered the VP's question), the target is set too loose, and Google will spend up to meet it, not below it. Tighten the target down toward actual, in single-digit-percent steps, and watch volume — don't jump straight to the new number.

**Do not use "beat target 2 months straight" alone as justification to loosen tCPA further** — that's exactly the instinct that leads to point 3 above. Beating target consistently means either the target's stale (fix it) or there's real headroom (test it deliberately, see #4) — not "raise the target and hope."

## 4. Should you put more money into ads next quarter? (the VP's #1 ask, answer last)

- **This quarter's $45k is fixed — don't treat "beat target 2 months" as license to overspend now.** The case you're building is for Q1 budget, not for bending the current cap.
- Before recommending an increase, get three numbers from the pacing log and tCPA calibration above:
  - Is the Google campaign's CAC stable *and* below your max-allowable CAC (from #1) with sufficient volume (from #3) — not just "under target," which could mean the target's loose?
  - What's the marginal CAC if you push 20% more budget into it — not the current blended CAC. Test this in-quarter with a small controlled budget bump (e.g., +$2-3k for one week, isolated from the rest of the $45k) before proposing a permanent increase; flat or rising marginal CAC as spend increases means you're near channel saturation, not "add more."
  - Is the win concentrated in one segment/keyword set that could hit a ceiling, or genuinely broad?
- **Recommendation structure for the VP:** "Google is beating target with [X] margin of safety on CAC, marginal CAC at +20% spend held at [Y], so we're not yet saturated — propose +$Z/month for Q1, contingent on the CAC kill-switch rule above being in place first." That last clause matters — she won't (and shouldn't) fund more spend without the guardrail that stops another $18k weekend.