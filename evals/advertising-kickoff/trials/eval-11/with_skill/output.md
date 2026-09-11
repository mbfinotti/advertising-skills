## Warm start — Marrowgate Fitness

**State summary** (from `advertising-context.md`, session 9, updated 2026-09-04):
- B2C subscription fitness, self-serve — $29/month, AOV $41 — paid social only, $30k/month, frozen for Q4
- Conversion source of truth: first paid membership, order system authoritative — **tracking verified GO in June**
- CAC $44 vs $58 break-even, guardrail policy already written
- In-flight work: none
- Active constraint: none blocking — two in-house creators hired last month, compounding investment with exec sign-off

Session goal (given): decide what to do next.

## Push back on the assumption

No — don't re-audit tracking this month. The "measurement → diagnose → creative" order is the **default for a cold or newly-symptomatic account**, not a ritual to repeat every session. Your artifact shows you've already walked it:

- Measurement: `mbfinotti/advertising-skills@ad-conversion-tracking` verified GO in June, and nothing since then touched the pixel, consent flow, or event setup. Re-running it without a trigger (a tag change, a new discrepancy, a consent-mode update) buys zero new information — that's the "cheapest option" failure mode in reverse: repeating a cheap step because it feels safe, not because it's owed.
- Diagnosis: `mbfinotti/advertising-skills@ad-account-diagnostic` already ran (2026-07-10) and named **creative decay** as the failing layer. `mbfinotti/advertising-skills@ad-creative-fatigue` then confirmed it (2026-07-24): **fatigued**. Diagnosis is done and it has a verdict — re-running it isn't diagnosis, it's stalling.

What's actually sitting open since May: creative hasn't been refreshed since the May flight, the fatigue verdict from July has never been acted on, and two in-house creators you hired last month have nothing to shoot.

## Route

**`mbfinotti/advertising-skills@ad-creative-brief`** — turn the July fatigue verdict + your audience insight into a brief your two in-house creators can execute.

## Short-list

Creative & audience is explicitly promoted above its normal efficiency ranking. All three promotion conditions in the kickoff skill are met at once:
1. Compounding + headcount available (Q6-equivalent: "compounding investment... exec sign-off," creators hired)
2. Diagnosis already named creative as the failing layer (twice: diagnostic, then fatigue)
3. No refresh in a full flight (last refresh: May; it's now September)

| # | Skill | Bottleneck it attacks | Session cost |
|---|---|---|---|
| 1 | `mbfinotti/advertising-skills@ad-creative-brief` | Fatigued creative, unbriefed, idle in-house capacity for 7 weeks | One session, no production yet |
| 2 | `mbfinotti/advertising-skills@ugc-ad-scripts` | No shootable scripts once the brief lands | One session per concept, feeds creators directly |
| 3 | `mbfinotti/advertising-skills@ad-creative-test-plan` | New batch has no pre-registered kill/scale rule, so a relaunch can't be read cleanly | One session, plans only — no spend moved |
| 4 | `mbfinotti/advertising-skills@ad-copy-variants` | No fresh text/headline variants to pair with new video | One session, ML asset-pool refresh |
| 5 | `mbfinotti/advertising-skills@cac-roas-benchmark` | CAC/ROAS position last computed before this flight; confirms the guardrail still holds while creative turns over | About an hour, measurement only |

## Chain

`mbfinotti/advertising-skills@ad-creative-fatigue` *(done, 07-24)* → `mbfinotti/advertising-skills@ad-creative-brief` → `mbfinotti/advertising-skills@ugc-ad-scripts` / `mbfinotti/advertising-skills@ad-copy-variants` → `mbfinotti/advertising-skills@ad-hook-analyzer` → `mbfinotti/advertising-skills@ad-creative-test-plan`

Each link hands the next one its input: fatigue verdict justifies the brief; the brief directs the scripts and copy; hook-analyzer ranks the resulting video openings before spend touches them; the test plan sets the cells, budget, and kill/scale rule the ranked shortlist launches under.

## Not now

- `mbfinotti/advertising-skills@ad-hook-analyzer` — after `mbfinotti/advertising-skills@ugc-ad-scripts` produces candidate scripts/storyboards to score.
- `mbfinotti/advertising-skills@ad-conversion-tracking` — only if a tracking/pixel/consent change ships, or a new discrepancy shows up. Nothing in the artifact triggers it today.
- `mbfinotti/advertising-skills@ad-account-diagnostic` — only if a new symptom appears post-refresh that creative alone doesn't explain (e.g., CPA drift persisting after new creative launches).
- `mbfinotti/advertising-skills@ad-swipe-file` — only if the first brief round underperforms and you need outside angles; the internal verdict (wear-out, not a strategy gap) doesn't call for it yet.

**Deleted, not ranked:**
- `mbfinotti/advertising-skills@paid-media-scaling` and `mbfinotti/advertising-skills@ad-spend-allocation` — Q4 budget is decided, frozen at $30k/month; no total-spend or split decision is live.
- `mbfinotti/advertising-skills@ad-platform-selection` — channel isn't open; paid social only is the standing decision.
- `mbfinotti/advertising-skills@ad-spend-guardrails` — policy already written and in force.
- `mbfinotti/advertising-skills@ad-negative-keywords` — no search spend on this account; not applicable.

## Gap

None for this task — everything needed (brief → scripts → test plan) is covered by the collection.

## Artifact patch

```
- **Updated**: 2026-09-12 (session 10)
- **In-flight work**: Q4 creative refresh — brief for two in-house creators (starting)

## Session log
- 2026-09-12 - decide what to do next -> mbfinotti/advertising-skills@advertising-kickoff -> routed to ad-creative-brief; creative class promoted (compounding+headcount, diagnosis already named creative twice, no refresh since May flight); declined re-audit of tracking/diagnosis — no trigger since June GO
```