# Brightgale — sponsored-card copy (in-assistant beta)

**One thing up front:** the search line wasn't trimmed — it was rewritten. Per the skill this is built from ("Adapt this winning search headline for a one-shot assistant slot" is expected to fail the register and get rewritten, not trimmed"), `The #1 Project Management Tool | 30% Off - Ends Tonight | Try Brightgale Free Today` fails on three separate grounds, not just length:

- **"#1"** — unsupported superlative, no source on hand. Sits directly next to whatever qualified answer the assistant gives in the same turn; it loses that comparison. Held as `UNSOURCED`.
- **"Ends Tonight"** — manufactured urgency, which breaks the conversational register on its own. It's also **factually wrong for this placement**: the real discount runs through March 31, 2026, not tonight. Shipping "Ends Tonight" here isn't a style miss, it's a false claim.
- **Category-winner announcement + discount + CTA in one line** — three moves bundled into one slot; the one-idea rule kills two of them.

Below is the rewritten package, built from the situation up.

## Placement + control axis

In-assistant sponsored card, beta. **Verbatim** — the platform renders your string exactly as written, no model rewrite. Advertiser-written, owned by whoever runs your paid-media/ads-manager account. Fields: Title ≤50 chars, Copy ≤100 chars, no CTA field (ask folds into the copy line), targeting description ≤280 chars — as pasted from your ads manager.

_Assumption made in place of a full interview: treating this as B2B (project-management tooling is usually a team decision, and the reader is often building a case, not just buying for themselves). Flag if Brightgale is actually sold B2C/solo — the situation description below would need to shift to name a single user's pain, not a team-lead's case._

## Situation description

"A team lead choosing project management software after past tools took weeks to configure, needing the team executing on a real plan within a day." (146 chars)

Alternate, for delivery diagnosis: "A manager comparing project management tools after one buried a simple plan under setup screens instead of getting the team moving." (131 chars)

## Slot copy

- **Title:** `First project plan in under 20 minutes` (38/50 chars)
- **Copy:** `Brightgale: 210 customers shipped their first project plan in under 20 minutes (2026 survey).` (93/100 chars)
- **Ask folded in:** none needed — the claim itself is the pitch; no CTA field exists, and forcing "Try free" into the remaining 7 characters would bundle a second move into one slot.

Why this angle over the discount: the onboarding-speed number is the one piece of evidence that's both quantified and durable — it doesn't expire, and it gives a B2B reader something to repeat in a meeting ("teams like ours got a working plan in 20 minutes"). The discount is real but time-bound and better suited to its own tested variant (see below) than to bundling with the speed claim.

## Grounding table

| Claim                                                  | Source                                                  | Status                                                               |
| ------------------------------------------------------ | ------------------------------------------------------- | -------------------------------------------------------------------- |
| "210 customers" / "2026 survey"                        | 2026 onboarding survey, 210 customers, supplied by user | Sourced                                                              |
| "first project plan in under 20 minutes"               | Same 2026 onboarding survey                             | Sourced                                                              |
| "#1 Project Management Tool" (from original search ad) | None supplied                                           | `UNSOURCED` — dropped, not carried into the card                     |
| "30% off — Ends Tonight" (from original search ad)     | Discount is real but ends March 31, 2026, per user      | Inaccurate as originally worded — dropped, not carried into the card |

## Compliance note

- Not a regulated category (health/medical/financial) — no pre-existing legal-review gate under this skill's rules.
- Platform's own "Sponsored" label covers disclosure; FTC/ASA obligations still sit on Brightgale independently.
- One flag worth routing to legal/marketing regardless: the original search ad's "Ends Tonight" against a real March 31, 2026 deadline is a live accuracy problem on whatever surface it's still running, not just this new card — worth checking outside this task's scope.

## Quotability gate — 10/10

1. Full sense with zero context — pass.
2. Product named explicitly, no pronoun — pass ("Brightgale" in the copy line).
3. Exactly one idea — pass (onboarding speed only).
4. Claim first, support after — pass (title states the outcome, copy sources it).
5. Specific detail over adjectives — pass ("under 20 minutes," "210 customers").
6. Every claim traced to a source — pass (2026 onboarding survey).
7. Time-bound claims dated, review date set — pass; not itself time-bound, but date the survey and set a review for when a newer cohort survey exists (recommend: re-verify by Q1 2027 or on next onboarding survey).
8. Recommendation register, no manufactured urgency — pass.
9. Survives sitting beside the model's own assessment, no unsubstantiated superlative — pass (no "#1," no "best").
10. Inside today's pasted limits — pass (38/50 title, 93/100 copy, 146/280 situation description).

## On the discount

A genuine, dated offer is allowed on this surface ("a genuine, dated offer still qualifies; a countdown does not"). If you want to test the discount as a second angle, it needs to ship as its own variant, not bundled into the line above — that's a variant-matrix exercise, out of this skill's scope (hand it to the ad-copy-variants skill). For reference, a compliant version of that angle, correctly dated and with no fake urgency: `Brightgale: project management software, 30% off through March 31, 2026.` (78/100 chars) — untested, unscored, offered only as a corrected illustration, not a second shipped line.

## Measurement plan

No account baseline on this surface yet — the first 30 days set it. Attribution window: 14 days minimum (majority of conversions land outside the immediate click window on this surface). Read order: delivery across the two situation descriptions first (confirms the "team lead, slow setup" framing is finding real conversations) — only then read click-through against the 30-day baseline once it exists. Given B2B, expect lead-quality to be the read that actually matters, but on a quarterly cadence, not 30 days — conversion volume this early won't support copy-level significance sooner.
