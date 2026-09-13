## Hollowbeam — routing (cold start, no `advertising-context.md` found in this repo)

This repo has no `advertising-context.md`, so this is a cold start for Hollowbeam. The prompt itself answers most of the interview, so I'm not blocking on questions — routing below, with the two still-open items flagged at the end instead of asked one-by-one.

**Detected**: B2B (dev-tools), $18k/month = $5k–50k spend band, conversion source of truth currently _disputed_ (that's item a itself).

### Route

| #   | Task                                                         | Route                                                 | Why (per `skill-routing.md`)                                                                                                                                                                                                                                                                                                                                               |
| --- | ------------------------------------------------------------ | ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| a   | Meta 210 / GA4 150 / CRM 96                                  | `mbfinotti/advertising-skills@ad-attribution-gap`     | Exact match: "quantify and explain the discrepancy between ad platform reporting, an analytics tool, and the source of truth... 'the numbers don't match'." Not `cac-roas-benchmark` (that judges health once one number is trusted, doesn't reconcile three) or `ad-conversion-tracking` (that's pre-launch GO/NO-GO; here events are already live and just disagreeing). |
| b   | Pick the video opener from 3 cuts (differ only in first 4s)  | `mbfinotti/advertising-skills@ad-hook-analyzer`       | Exact match: "score and force-rank the openings of candidate video ads before launch... first 3 seconds, thumbstop." Not `ad-creative-test-plan` (that sizes budget/duration for a test, doesn't pick the winner) or `ugc-ad-scripts` (that writes scripts, doesn't score existing cuts).                                                                                  |
| c   | One newsletter + one podcast, no doomscrolling               | `mbfinotti/advertising-skills@advertising-radar`      | Exact match: "newsletter", "podcast", "stay current" is the named trigger list for this skill verbatim.                                                                                                                                                                                                                                                                    |
| d   | Copy for a sponsored answer slot in an AI shopping assistant | `mbfinotti/advertising-skills@conversational-ad-copy` | Exact match: "the one-shot ad occupying a single response slot inside an assistant reply or answer-engine result." Not `ad-copy-variants` (that's feed/search/social copy, explicitly excludes this surface).                                                                                                                                                              |

None of the four hit a named coverage gap — all four route cleanly, no stretching.

### Short-list (this project, right now — value/effort, highest first)

1. **`ad-attribution-gap`** (= task a) — buys back which of the three numbers Hollowbeam can act on; every other number this month is unreadable until this runs. Costs a session on data already in hand, ~1 day.
2. **`ad-hook-analyzer`** (= task b) — decides the opener before spend goes behind any of the three cuts; skip it and you're guessing which 4 seconds to bet media on. Costs one scoring pass, no new production.
3. **`conversational-ad-copy`** (= task d) — a bought placement sitting idle costs money every day it's live without copy; near-zero effort, single slot. Costs an hour.
4. **`advertising-radar`** (= task c) — pure currency, not an outcome; do it last of the four. Costs ~20 minutes to assemble the list.
5. **Not routed today, but next once (1) lands** — `mbfinotti/advertising-skills@cac-roas-benchmark`: $18k/month with no stated CAC/ROAS verdict is exactly the class-2 diagnosis question this account hasn't answered yet. Held below the four above because it depends on (1) naming which number is authoritative first.

### Chain

Only one real dependency exists among today's four items — the rest are independent asks, not a sequence:

`ad-attribution-gap` (task a) → **if** it finds a genuine unexplained residual rather than a timing/definitional gap → `mbfinotti/advertising-skills@ad-conversion-tracking` (re-verify events aren't double-firing/dropping) → then `cac-roas-benchmark` becomes trustworthy. Conditional, not fabricated — only follow it if (a)'s verdict calls for it.

### Not now

- `mbfinotti/advertising-skills@ad-spend-allocation` / `paid-media-scaling` / `ad-spend-guardrails` — pointless to touch while the source of truth is contested; unblocked once `ad-attribution-gap` (task a) returns a verdict.
- `mbfinotti/advertising-skills@ad-creative-test-plan` — natural next step _after_ the hook-analyzer ranking (task b) picks a winner, if Hollowbeam wants a powered test rather than just shipping the top cut.
- `mbfinotti/advertising-skills@ad-account-diagnostic` — only worth running if (1) surfaces a deeper structural problem than a reporting gap.

### Gap

None for these four — all routed. (For reference, this collection still has no skill for incrementality testing, positive keyword research, or in-platform execution, none of which today's grab bag touched.)

### Open items (would ask next turn, not blocking this answer)

1. Is Hollowbeam's dev-tools motion sales-led or self-serve? (changes nothing about today's four routes, but re-ranks the short-list going forward.)
2. Is this a one-off pass or should I stand up `advertising-context.md` + routines (monthly `cac-roas-benchmark`, weekly `ad-budget-pacing`, quarterly kickoff re-run) for Hollowbeam as a recurring engagement? If yes, point me at the actual Hollowbeam project path — this repo is the skill collection itself, not a client project, so I can't write the artifact here.

Draft artifact, ready to drop in once you give me the path:

```markdown
# Advertising context

- **Updated**: 2026-09-12 (session 1)
- **Business model**: B2B dev-tools, motion unconfirmed (sales-led vs self-serve)
- **Offer / price point**: unconfirmed
- **Channels / spend**: Meta + (implied) Google/GA4-tracked channels, ~$18k/month
- **Conversion / source of truth**: DISPUTED — Meta 210, GA4 150, CRM 96 for the same period; CRM is the provisional source of truth pending `ad-attribution-gap`
- **CAC-ROAS position**: not yet benchmarked, blocked on source-of-truth resolution
- **In-flight work**: reconciling Meta/GA4/CRM conversion counts; ranking 3 demo-video openers; writing conversational-ad-copy for a bought AI-assistant sponsored slot; building a radar (1 newsletter + 1 podcast)
- **Decided**: —
- **Open**: which number is authoritative; sales-led vs self-serve motion
- **Constraints**: none stated yet
- **Horizon / effort ceiling**: unconfirmed
- **Stakeholders**: unconfirmed

## Session log

- 2026-09-12 - grab-bag routing (attribution gap, hook pick, radar, conversational copy) → `ad-attribution-gap`, `ad-hook-analyzer`, `advertising-radar`, `conversational-ad-copy` → routed, none executed yet
```
