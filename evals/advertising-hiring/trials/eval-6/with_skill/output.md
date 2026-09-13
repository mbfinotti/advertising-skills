# 30-60-90 Ramp — Quillwater Performance Marketer

_Assumptions (flag if wrong): this is the first dedicated paid-media hire, mandate is paid channels + measurement (not lifecycle/CRO), Quillwater runs 2+ paid channels at $120k/month. Milestone skeleton below is this skill's own synthesis, not a published standard — the two anchor rules (day-one access, no CAC target before attribution is validated) are sourced to eCommerce Placement's paid-media onboarding guidance._

## Two requests that need to change before Monday

**1. CAC target in week 2 — pull this.**
The sourced rule: _"Don't ask a new growth leader to commit to a CAC or LTV target before they've validated your attribution setup."_ Here it's worse than the general case — analytics access doesn't unlock until day 60, so in week 2 the hire has no login to the numbers a CAC target would even be measured against. A week-2 commitment would be a guess dressed as a target.

Replace it with: **by end of week 2, the hire delivers a written measurement-audit plan** — what will be reconciled (platform-reported vs. backend revenue, MMP vs. store data), against what data sources, on what timeline once analytics access opens day 60. That's a real, gradeable week-2 deliverable that doesn't require account access to produce.

**2. "Scale the best campcampaign 50%" as the month-1 win — pull this too.**
Two independent problems: (a) the skill's sourced pattern is explicit that _the first win is a tracking fix or a contained optimization, never a scaling bet_ — scaling before attribution is validated is how you scale a measurement error; (b) it's not physically possible under your own IT policy — ad account access opens day 30, right at the edge of "month 1," leaving zero verified days of account contact inside the window the COO is describing.

Replace it with: **the month-1 win is the account + creative audit, delivered as a prioritized, ranked backlog the day account access opens (day 30)**, with the highest-confidence item flagged and ready to co-sign in week 5. That's a real, visible, low-risk win the COO can point to — "found and queued $X/month of identified waste" reads better in a leadership update than an unvalidated scaling bet anyway, and it's the version of "big win" that won't need walking back in month 3.

Worth saying to the COO directly: asking for both of these together — a number to commit to and a scaling bet to execute — before the hire can see a single dashboard is the exact setup the skill's failure-mode table flags for early churn ("good hire pushed out at month 3 for no results... platform learning phases and attribution validation cannot resolve that fast"). Better to spend that credibility on the audit finding something real.

## Access vs. IT policy — flag this gap too

The sourced rule is access on day one; your policy gives ad accounts at day 30 and analytics at day 60. That gap is the actual root cause of why a week-2 CAC commitment and a month-1 scaling win aren't achievable — it's not a competence question, it's a sequencing one.

Recommended ask to IT/security: **request read-only access to ad accounts and analytics starting day 1**, with write/edit access staying gated at day 30/60 per policy. Read-only costs nothing on the security threat model probation is presumably protecting against (no changes possible), and it lets weeks 1-4 of "shadow" actually mean something — observing real data instead of screenshots someone else exports. If IT won't grant that, the ramp below assumes zero account visibility before day 30.

| Access                                                      | Granted                                   | Note                                                     |
| ----------------------------------------------------------- | ----------------------------------------- | -------------------------------------------------------- |
| Ad platform accounts                                        | Day 30 (policy) — ask for read-only day 1 | Security probation                                       |
| Web analytics                                               | Day 60 (policy) — ask for read-only day 1 | Security probation                                       |
| Mobile measurement partner (AppsFlyer/Adjust/etc.)          | Day 60, same as analytics                 | App advertiser — this is the attribution source of truth |
| Commerce/CRM backend                                        | Day 60, bundle with analytics             | Needed for backend-vs-platform reconciliation            |
| Tag manager                                                 | Day 30, bundle with ad accounts           |                                                          |
| BI/reporting layer                                          | Day 60                                    |                                                          |
| Docs, brand assets, historical reports (exported, not live) | Day 1                                     | No policy blocker — hand these over manually             |

## Spend-authority ladder (re-sequenced around the policy gap)

| Phase                    | Window          | Authority                                                                                                                                                                                                                                                                                                                                                |
| ------------------------ | --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Shadow                   | Weeks 1-4       | No account access (or read-only, if IT grants the exception). Onboarding, historical report review, stakeholder interviews, creative/account audit prep from exported data.                                                                                                                                                                              |
| Co-sign                  | Day 30 – day 59 | Ad account access live, analytics still dark. Changes require a second signature — no independent calls yet, since there's no reconciled number to judge them against.                                                                                                                                                                                   |
| Independent within a cap | Day 60 – day 89 | Analytics/MMP live. Cap is a written dollar figure, not a vibe — set it with the COO in week 8, once the audit is underway.                                                                                                                                                                                                                              |
| Full authority           | Day 90+         | **Contingent on a validated measurement audit.** Audit can only start day 60, so this is a ~30-day audit window — tight. If it's not done by day 90, authority stays capped, not full; that's expected, not a red flag (channel verdicts take 3-6 months per Wilcox — a 90-day full-authority date was already ambitious even without the access delay). |

## Day 30 / 60 / 90 milestones

|                        | Day 30                                                                                        | Day 60                                                                                                                                       | Day 90                                                                                                                             |
| ---------------------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Deliverable            | Account + creative audit complete; ranked optimization backlog; first co-signed change queued | Measurement audit complete — platform vs. backend reconciliation documented; MMP validated; first contained optimizations live independently | CAC/target commitment made **now**, against validated numbers; audit-flagged scaling candidate (if any) proposed, not yet executed |
| Replaces the COO's ask | —                                                                                             | This is where a real CAC number becomes honest                                                                                               | This is where a real scaling bet becomes honest — 60 days later than requested, but the first one that won't need retracting       |

## Watch areas (distinct from goals)

- Hire sits idle weeks 1-4 with no account access — mitigate with exported historical data, stakeholder interviews, and the audit-plan deliverable so week 2 still has a real output.
- Pressure to informally "peek" at live accounts before day 30 to satisfy the COO's timeline — access policy should hold regardless of leadership pressure.
- If the COO reintroduces a CAC number or scaling ask before day 60 informally (in a standup, a Slack DM), that's the same risk resurfacing outside the written plan — worth a one-line reminder at that moment, not a re-litigation.
- Early-tenure churn (documented industry range: 18-45% depending on source/cohort) concentrates in the first 45-90 days and, per the sourced pattern, traces to access delays and unclear spend thresholds — not the hire. If this ramp gets compressed under pressure, that's the mechanism to watch for.
