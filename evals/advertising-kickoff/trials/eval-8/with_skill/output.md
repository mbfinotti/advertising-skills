## Detection

No `advertising-context.md` for this account anywhere in this repo, and no project repo for Torvald & Finch exists here — **cold start**. This session's scheduler reports zero jobs (`CronList` → none), so the "seven automations" live in whatever ops tool the last team actually used (Slack/Zapier/agency portal) — I can't see or audit them directly, only what you told me about one of them.

## Interview — answered from your message, rest flagged open

| # | Item | Status |
|---|---|---|
| Q1 business model | B2B legal-billing SaaS, sales-led assumed (LinkedIn spend) | **open — confirm** |
| Q2 session goal | Set up recurring reviews | given |
| Q3 channels/spend | $60k/mo — Search $24k (40%), Meta+LinkedIn $36k combined; split between the two not given | **partially open** |
| Q4 conversion source of truth | not stated | **open — blocking** |
| Q5 constraints | agency contract (Meridian West); flight ends 2026-10-10 (inside 6 weeks); creative capacity ample (in-house studio of 3, weekly); regulated-vertical status unknown | mostly given |
| Q6 effort ceiling | compounding, assumed "a few hours/week" | **open — confirm** |
| Q7 decided/open | flight date and agency relationship are decided; the other 6 legacy automations are undescribed | **open** |

Q4 is the one that gates everything else: per the skill's own rule, nothing ranks above measurement integrity while the conversion source of truth is unconfirmed — so it sits at the top of the short-list below, not as a footnote.

## Route

The immediate task — "set up recurring reviews" — is this skill's own §7 process (`advertising-kickoff`, self), which in turn schedules routines that each invoke a sibling skill.

## Short-list (value ÷ effort, highest first)

1. **`ad-conversion-tracking`** — bottleneck: no named source of truth means every number below is unverified; costs part of a day, one engineer.
2. **`cac-roas-benchmark`** — bottleneck: no monthly health verdict exists to judge the Oct 10 flight or the month after; costs ~1 hour/month once #1 is confirmed. Gated on #1.
3. **`ad-negative-keywords`** — bottleneck: $24k/month on Search with no stated query-mining cadence; costs a search-term export + review pass/month. Normally class-5 (near-zero value until rungs above pass), promoted into scope because Search is a meaningful spend share.
4. **`ad-creative-fatigue`** — bottleneck: weekly creative output with no wear-out check means stale ads can run past their life unnoticed; costs a weekly read of per-creative delivery. Same class-5 caveat, promoted because production capacity exists to act on the verdict.
5. **`ad-budget-pacing`** — bottleneck: Meridian West's Monday-only email leaves no coverage Tue–Sun; near-zero cost, but **only for the flight's final week** (see routines below) — the standing weekly version is a duplicate of the agency's report and is cut.

**Chain**: `ad-conversion-tracking` → `cac-roas-benchmark` — tracking has to be trusted before a health verdict means anything.

**Starved and not promoted**: class 4 (creative & audience — briefs, scripts, copy, hook analysis) is first on value and first on effort at once, so it ranks below measurement and diagnosis by the ratio every time. Not promoting it this session: nothing has named creative as a failing layer yet, and weekly studio output means no staleness signal either. It promotes when `ad-account-diagnostic` or `ad-creative-fatigue` names creative as the problem, or when a full flight passes with no refresh.

**Not now** (fixed date inside 6 weeks demotes anything that pays out past the flight):
- `ad-spend-guardrails` — unblocks 2026-10-10 (no written CAC/ROAS ceiling exists, but writing one now competes with flight-critical work)
- `ad-campaign-consolidation` — unblocks 2026-10-10, no fragmentation signal given anyway

**Deleted, not ranked last**: `ad-budget-pacing`'s standing weekly cadence is deleted outright, not parked at the bottom — Meridian West's Monday email already covers it. The constraint that killed it: an existing agency deliverable, not low value.

**Gap**: none new for this task. Standing gaps from the collection: no skill audits *existing* automations for relevance — that's this skill's own §7 cleanup step, done manually below.

## Cleanup — before adding anything

Only one of the seven legacy automations is named: the **daily "ad tips" digest**. It fails the routine test outright — no decision it feeds is still open daily, and "nobody reads it" is the direct symptom of a routine with no real output-channel value. **Recommend killing it.**

The other six are invisible to me — I don't have access to whatever system runs them. **Name them and I'll audit each against the same test** (named output channel? feeds a decision still open today? not a duplicate of Meridian West's email?) before you add anything new — installing four more routines on top of six unaudited ones just makes eleven, most of which nobody reads.

## Routines — dry run (nothing created yet)

Two structural notes before the routines:

- **Cap is 4 standing routines.** I'm proposing exactly 4, plus one temporary flight-bridge routine that self-deletes.
- **This session's scheduler can't host these.** `CronCreate` jobs live only in this Claude session, auto-expire after 7 days, and vanish when the session ends — useless for a monthly or quarterly cadence, and even the Oct 3 start of routine 5 is 3 weeks past that window. These need to live in whatever recurring-task tool already runs Meridian West's Monday email or the legacy automations. I'm handing you the spec; you (or I, once pointed at that tool) wire it in.

```
Routine:    Monthly spend health check
Runs:       monthly, first run 2026-10-13 (first Monday after flight close), then monthly before the next budget cycle
Does:       cac-roas-benchmark against real spend/conversion data — first run will likely return "insufficient evidence" until the conversion source of truth (Q4) is named
Outputs to: <name your team channel / doc — not yet known>
First run:  2026-10-13 (dry run only)
```

```
Routine:    Monthly negative-keyword mining
Runs:       monthly, after month-end budget reset — first run 2026-10-02 (covers September Search data)
Does:       ad-negative-keywords on the Search account's search-term report ($24k/mo, 40% of spend)
Outputs to: <name channel>
First run:  2026-10-02 (dry run only)
```

```
Routine:    Weekly creative wear-out check
Runs:       weekly, matched to the studio's weekly output cadence — day TBD
Does:       ad-creative-fatigue on the running creative set across Meta + LinkedIn
Outputs to: <name channel — studio needs to see this to act on it>
First run:  <TBD, pick a day>
```

```
Routine:    Quarterly kickoff re-invocation
Runs:       quarterly, anchored to Q4 planning — first run early November 2026
Does:       re-run advertising-kickoff to refresh advertising-context.md and re-route
Outputs to: this artifact + a short note to whoever owns the account
First run:  ~2026-11-03 (dry run only)
```

```
Routine (temporary, self-removes):  Daily pacing bridge for the flight's final week
Runs:       daily, 2026-10-03 through 2026-10-10 only
Does:       ad-budget-pacing, covering the gap Meridian West's Monday-only email leaves during the highest-risk week
Outputs to: <name channel>
First run:  2026-10-03 (dry run only) — deleted automatically after 2026-10-10
```

Compliance note: none of these five carry a compliance cost on their own (they read data that already exists) — but if the regulated-vertical question above turns out "yes," the negative-keyword routine's output channel needs to be one your data-handling policy already covers, since search-term reports can contain user-typed text.

## Context artifact

Sent as a file: `advertising-context.md`. It has no real project repo to live in yet, since Torvald & Finch isn't a repo I have access to — save it at that project's root and commit it; that presence is what makes the next session warm instead of cold. I did not write it into this repo (skills-affiliation), since it belongs to an unrelated project.

## Memory

Not written anywhere yet. Per your CLAUDE.md, I should ask first: does Torvald & Finch client context belong in that project's own memory/CLAUDE.md, or somewhere else? Regardless of where, I'd exclude the agency's negotiated rates, any ad account IDs, and unreleased campaign/pricing plans from whatever gets stored, per the skill's own exclusion list.

## Before anything goes live, I need from you

1. **Conversion source of truth** (blocks the spend-health routine from meaning anything).
2. The other **6 legacy automations** — name them so I can audit and prune alongside the ad-tips digest.
3. **Output channel names** for the 5 routines above (a Slack channel, a doc — "notify me" isn't a channel).
4. Confirm **business model** (sales-led vs self-serve) and the **Meta/LinkedIn split**.
5. Where the **real project repo/memory** lives, so the context artifact and memory entry land somewhere durable instead of my scratchpad.