# Loomhaven paid media — kickoff routing

## Cold start, no persisted context

No `advertising-context.md` exists for this project (I only have this repo, which is the skills collection itself, not a Loomhaven project folder), so this is a cold start. I'm skipping re-interview theater and just extracting what your message already answered, flagging what's still open, and giving the routing. Save the context-artifact draft at the bottom into Loomhaven's own repo so next session is warm.

## What I could detect vs. what's still open

**Answered by your message:**

- Business model: B2B (scheduling tool)
- Budget: $45k/month, fixed, Q4 only — committed, not discretionary
- Hard date: Q4 starts Oct 1, 2026 — **19 days away**, inside the 6-week window that changes the ranking below
- Known failure: $18k burned in a weekend, Dec 2025 — no kill-switch existed
- Session goals: (1) scale-up decision, (2) written CAC/kill-switch policy, (3) weekly pace check, (4) tCPA target doubt

**Still open — confirm before I'd trust the numbers coming out of guardrails/benchmark:**

1. Conversion event and its source of truth (platform pixel? CRM? demo-booked vs. paid?) — this gates everything else below.
2. Channels beyond Google — is the $45k Google-only or split across others?
3. Self-serve or sales-led motion (changes what "CAC" should even mean — trial vs. closed deal).

I'm not blocking on these; I'm routing around them and naming where they bite.

## Direct answer: which skill, for which ask

| Your ask                                       | Skill                                              |
| ---------------------------------------------- | -------------------------------------------------- |
| "Should we put more into ads next quarter?"    | `mbfinotti/advertising-skills@paid-media-scaling`  |
| "Written rule for allowable CAC + kill switch" | `mbfinotti/advertising-skills@ad-spend-guardrails` |
| "Each Friday: burning $45k too fast or slow?"  | `mbfinotti/advertising-skills@ad-budget-pacing`    |
| "Is our tCPA target even right?"               | `mbfinotti/advertising-skills@ad-bidding-strategy` |

None of these is a guess — each matches a declared scope line-for-line, not an adjacent skill stretched to fit.

## Order to run them

Your four asks aren't independent — they're most of the collection's own budget-stack chain, plus one measurement check the interview left unconfirmed:

1. **`mbfinotti/advertising-skills@ad-conversion-tracking`** — GO/NO-GO on the event that will feed every CAC number below. Unconfirmed source of truth outranks everything else by the skill's own rule: never open a short-list below measurement integrity while that's unresolved. Also worth asking directly: was the Dec blowout partly a tracking artifact (double-counted or delayed conversions) rather than pure bid-policy failure? Hours, one person.
2. **`mbfinotti/advertising-skills@ad-spend-guardrails`** — the written policy: max CAC, kill-switch thresholds, who can override, re-baselined off contribution margin and cash runway. This is the actual fix for "torched $18k in a weekend" — that's a guardrail that didn't exist, not a pacing problem. Needs CFO sign-off given your fixed-budget relationship with Finance.
3. **`mbfinotti/advertising-skills@cac-roas-benchmark`** — is Google's current CAC actually healthy against break-even/history, or is "beat target two months straight" just a target set too loose? Answers your VP's question honestly instead of taking the win at face value.
4. **`mbfinotti/advertising-skills@ad-bidding-strategy`** — your tCPA doubt, directly. Also cross-check with step 3: if the tCPA target was set soft, "beating it" for two months isn't proof of headroom.
5. **`mbfinotti/advertising-skills@paid-media-scaling`** — the actual scale-up call for next quarter: step size, ramp, rollback trigger. Run last — it's the one decision that consumes the other four's output. This is also where you get a real answer to "how much more," not just "more."

**Runs in parallel, starting now, blocked by none of the above:** `mbfinotti/advertising-skills@ad-budget-pacing`. The $45k/month is already set, which is all pacing needs. Don't wait for the chain — start your Friday check this week.

## Short-list, ranked by value returned per session

1. `mbfinotti/advertising-skills@ad-conversion-tracking` — buys trust in every number below; hours, one-time.
2. `mbfinotti/advertising-skills@ad-spend-guardrails` — buys the ceiling that stops a repeat of December; one session + CFO sign-off.
3. `mbfinotti/advertising-skills@cac-roas-benchmark` — buys a real verdict instead of "beat target"; one session, data you already have.
4. `mbfinotti/advertising-skills@ad-bidding-strategy` — buys confidence the tCPA target itself isn't the problem; one session.
5. `mbfinotti/advertising-skills@paid-media-scaling` — buys the actual next-quarter number and a rollback trigger if it's wrong; one session, only after 3-4 land.
6. `mbfinotti/advertising-skills@ad-budget-pacing` — buys the weekly fast/slow read your VP wants operationally; near-zero, run weekly.

**Re-rank note:** the fixed Oct 1 date (inside 6 weeks) is why guardrails and pacing sit ahead of where they'd otherwise land — a policy-and-structure item this close to a peak flight outranks its usual position.

## Not now

- `mbfinotti/advertising-skills@ad-spend-allocation` — splitting the fixed $45k across campaigns/channels. Unblocks once you confirm channels beyond Google exist and guardrails/benchmark are in place.
- `mbfinotti/advertising-skills@ad-account-diagnostic` — only if benchmark or bidding review turns up an underperforming layer elsewhere; nothing here is currently broken.

## Named gap

The collection has no skill for incrementality testing (holdout/geo-lift) or media mix modeling. "Google beat target two months straight" could mean real growth headroom, or it could mean you're bidding on brand-name searches that would've converted anyway — the collection can't tell you which. `mbfinotti/advertising-skills@paid-media-scaling`'s ramp-and-rollback structure is the pragmatic substitute (small step, watch for collapse), not a true incrementality read. Flag this to your VP as a known blind spot before she treats "more budget" as low-risk.

## Weekly pacing routine — dry-run

```
Routine:    Loomhaven weekly pacing check
Runs:       Weekly, Friday — tighten to daily during Nov 20-Dec 5 and the
            final week of December, anchored to last year's blowout window
Does:       ad-budget-pacing against the $45k/month Q4 ceiling
Outputs to: <name your channel — Slack #paid-media or a standing doc>
First run:  2026-09-18 (dry run — produces the read, creates nothing recurring yet)
```

Two more worth setting alongside it, both cheap:

```
Routine:    Monthly spend health check
Runs:       Monthly, before the following month's allocation call
Does:       cac-roas-benchmark against the guardrail ceiling once written
Outputs to: <same channel>
First run:  2026-10-01
```

```
Routine:    Quarterly kickoff re-run
Runs:       Quarterly, aligned to budget resets
Does:       Re-route, refresh advertising-context.md
Outputs to: <same channel>
First run:  2027-01-05
```

Approve these before I'd treat them as recurring — this is the proposal, not the creation.

## Context artifact — save as `advertising-context.md` in Loomhaven's repo

```markdown
# Advertising context

- **Updated**: 2026-09-12 (session 1)
- **Business model**: B2B scheduling tool — sales-led vs. self-serve: TBD, confirm
- **Offer / price point**: TBD
- **Channels / spend**: Google confirmed; other channels: TBD; $45k/month fixed, Q4 2026 only, committed by Finance
- **Conversion / source of truth**: TBD — confirm before trusting any CAC number
- **CAC-ROAS position**: unknown — no written guardrail exists; cac-roas-benchmark not yet run
- **In-flight work**: guardrail policy draft; Friday pacing check starting 2026-09-18
- **Decided**: Q4 total is fixed at $45k/month, not negotiable up or down
- **Open**: whether to scale spend in Q1 2027; whether current tCPA target is set correctly; channels beyond Google
- **Constraints**: Q4 starts 2026-10-01 (19 days out); prior seasonal blowout Dec 2025 ($18k/weekend, no kill-switch)
- **Horizon / effort ceiling**: compounding — weekly Friday check plus this quarter's guardrail-writing session
- **Stakeholders**: you → decides day-to-day; VP → consulted/decides on scale-up; Finance/CFO → decides guardrail sign-off

## Session log

- 2026-09-12 - kickoff: route VP's 3 asks + tCPA doubt → advertising-kickoff → routed to conversion-tracking → spend-guardrails → cac-roas-benchmark → bidding-strategy → paid-media-scaling, pacing running in parallel
```
