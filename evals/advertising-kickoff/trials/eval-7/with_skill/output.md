# Aldergate Health — Advertising Kickoff

**Cold start** — no `advertising-context.md` found in this repo (and this repo is the skills library itself, not an Aldergate Health project directory, so there's nowhere in-tree to commit one yet). Routing below runs against the collection's 31 skills.

## Before anything else: a flag outside this collection's scope

🆘 You're a telehealth clinic with an active state AG inquiry, running a Meta pixel and Google tag with **no independent source of truth** behind either. The single highest-risk item in your stack isn't marketing performance — it's what those two tags are actually capturing. Telehealth and hospital-system pixel deployments have triggered FTC actions and state AG suits industry-wide (GoodRx, BetterHelp, Cerebral, multiple hospital-system Meta Pixel suits) specifically for passing appointment types, form-field values, or page paths that amount to protected health information into Meta CAPI / Google Ads conversion events.

No skill in this collection audits legal exposure — that's a named gap (see below). Get legal/privacy counsel to pull the exact event parameters both tags send, **before** touching bidding, keywords, or anything else. This sits above the ranking that follows.

## Assumptions made to answer in one pass

This should normally be a capped interview (5-7 questions, one per message). Since you asked for the complete deliverable in one shot, I inferred what I could from your message and flagged what I couldn't:

| #   | Question                               | Answer used                                                                                                                                | Confidence                                                                                            |
| --- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| 1   | Selling to whom                        | B2C (patients)                                                                                                                             | assumed — confirm if there's a B2B2C/payer channel too                                                |
| 3   | Channels / spend band                  | Google + Meta, $35k/mo → **$5k-50k** band                                                                                                  | stated                                                                                                |
| 4   | Conversion source of truth             | Meta pixel + Google tag only, **no CRM/EHR/billing wired**                                                                                 | stated                                                                                                |
| 5   | Constraints                            | regulated vertical + legal review-everything (AG inquiry); no creative capacity for a quarter (designer left); no fixed landing date given | stated                                                                                                |
| 6   | One-off vs compounding, effort ceiling | **not stated**                                                                                                                             | unknown — assumed "compounding, a few hours/week" for ranking below; confirm, it reorders classes 3-4 |
| 7   | Decided vs open                        | nothing marked decided; your negative-keywords/bid-tweaks instinct is a _proposal_, not a decision                                         | inferred                                                                                              |

## Route

**`mbfinotti/advertising-skills@ad-conversion-tracking`** — start here, not with negative keywords or bids.

Q4's answer ("a platform pixel named as the only source of truth") pins measurement integrity to rung 1 regardless of what the session wanted — that's the kickoff's own override rule, and it happens to also be your compliance floor. This is a pre-launch-style GO/NO-GO check: are Meta pixel and Google tag firing once each, deduplicated between the two (double-firing on one conversion is common when both are live), consent-mode configured correctly, test/staff traffic excluded, values correct. It's the cheapest, fastest item on this list and it's the one everything else is currently built on sand without.

## Short-list — ordered by value returned per unit of effort

🟢 **1. `mbfinotti/advertising-skills@ad-conversion-tracking`** — Bottleneck: nobody knows if the pixel/tag numbers are even real. Cost: hours, one person, done once. _(promoted to rung 1 by Q4 — platform pixel is your only source of truth)_

🟢 **2. `mbfinotti/advertising-skills@ad-account-diagnostic`** — Bottleneck: you're guessing negative keywords/bids are the problem without having named the actual failing layer (could be creative decay, bidding, structure, offer — not search waste). Cost: one session, reads data you already have, implements nothing. Caveat: read its output knowing the underlying numbers weren't yet verified in step 1 — run these two close together.

🟢 **3. `mbfinotti/advertising-skills@cac-roas-benchmark`** — Bottleneck: you don't have a stated verdict on whether $35k/mo is healthy, over, or under break-even. Cost: one session against data in hand.

🟠 **4. `mbfinotti/advertising-skills@ad-spend-guardrails`** — Bottleneck: no written max-CAC/min-ROAS/kill-switch policy with named ownership. In a company where "legal reviews everything," a documented, sign-off-backed spend policy is also a defensibility asset, not just a marketing one. Cost: a session plus stakeholder sign-off.

🟠 **5. `mbfinotti/advertising-skills@ad-copy-variants`** — Bottleneck: no new visual creative for a quarter, but this is the one creative-class skill (along with `ad-swipe-file`) that needs no designer — text headlines, RSA assets, primary text your team or a freelance copywriter can produce. Cost: a session, no design capacity required.

🔴 **6. `mbfinotti/advertising-skills@ad-negative-keywords`** — Your original starting point. Near-zero effort, near-zero value until rungs 1-3 pass, and a bid/keyword edit spends a learning window you can't easily get back. Not deleted — still real work — just not where the dollar-per-hour is highest today.

🔴 **7. `mbfinotti/advertising-skills@ad-bidding-strategy`** — Same demotion, same reason. Bid changes on top of unverified conversion data risk optimizing toward a number that's wrong or, worse, non-compliant.

## Chain

`ad-conversion-tracking` → `ad-account-diagnostic` → _(the layer diagnostic names — could land on `ad-negative-keywords`, `ad-bidding-strategy`, `ad-campaign-consolidation`, or elsewhere)_

Verify the numbers are real and legal first; only then does "why is this account underperforming" mean anything, and only then does its answer tell you which of items 6-7 (or something else entirely) is actually the fix.

## Not now

- **`mbfinotti/advertising-skills@ad-attribution-gap`** — needs a CRM/order-system source of truth to reconcile against. You don't have one (EHR/billing never wired up). Unblocks when that integration exists — see Gap below.
- **`mbfinotti/advertising-skills@ad-spend-allocation`** / **`mbfinotti/advertising-skills@paid-media-scaling`** — unblocks after `cac-roas-benchmark` returns a verdict.
- **`mbfinotti/advertising-skills@ad-campaign-consolidation`** — unblocks if `ad-account-diagnostic` names fragmentation as the failing layer.
- **`mbfinotti/advertising-skills@ad-creative-brief`**, **`ugc-ad-scripts`**, **`ad-hook-analyzer`**, **`ad-creative-test-plan`**, **`ad-creative-fatigue`** — deleted from the short-list by your stated constraint (no creative production capacity this quarter), not merely ranked low. Unblocks when a designer is hired or contracted.
- **`mbfinotti/advertising-skills@ad-swipe-file`** — needs no designer either, but lower urgency than copy variants since you can't act on visual hypotheses yet. Worth running once someone's hired.
- **`mbfinotti/advertising-skills@retargeting-funnel`** — unblocks after `ad-conversion-tracking` clears GO (its funnel-stage data comes from the same pixel/tag).
- **`mbfinotti/advertising-skills@ad-platform-selection`**, **`ad-audience-targeting`**, **`lookalike-audience-seeds`**, **`ad-buyer-group-mapper`** — not in scope for this session (no new-channel decision on the table; lookalike/value-based seeding also blocked by the same missing CRM/EHR link as attribution-gap).

## Gap

The collection has no skill for:

- **Wiring the EHR/billing system to your ad platforms or analytics** — this is in-platform/data engineering execution, which no skill in this collection performs. It's also your actual root fix: until it exists, every CAC/ROAS number and every future attribution check is built on self-reported platform data.
- **Legal/compliance audit of what event data your pixel and tag actually transmit** — a legal question, not a marketing one. Given the AG inquiry, treat this as the real first task, ahead of anything above.

## Context artifact

No Aldergate Health project directory exists in this repo to commit `advertising-context.md` into. Here's the content — save it at the root of your actual project repo so the next session starts warm:

```markdown
# Advertising context

- **Updated**: 2026-09-12 (session 1)
- **Business model**: B2C telehealth clinic (confirm: any B2B2C/payer channel?)
- **Offer / price point**: not yet captured
- **Channels / spend**: Google + Meta, ~$35k/month
- **Conversion / source of truth**: Meta pixel + Google tag only; EHR/billing not wired — no independent source of truth
- **CAC-ROAS position**: unknown — not yet benchmarked; no written guardrail policy
- **In-flight work**: none yet
- **Decided**: nothing decided; negative-keywords/bid-tweaks is a proposal, not a decision
- **Open**: EHR/billing integration timeline; one-off vs compounding horizon and effort ceiling (Q6); whether a B2B2C channel exists
- **Constraints**: regulated vertical, legal reviews everything, active state AG inquiry; no creative production capacity this quarter (designer departed); no fixed landing date stated
- **Horizon / effort ceiling**: unconfirmed — assumed compounding, a few hours/week, pending your answer
- **Stakeholders**: growth lead → decides (assumed you); legal → consulted, likely required sign-off given AG inquiry; unnamed exec/board → unknown

## Session log

- 2026-09-12 - prioritize what to work on → advertising-kickoff → routed to ad-conversion-tracking; flagged PHI/pixel legal exposure as top priority outside the collection
```

## Routines — proposed, not created (dry-run only)

Per the skill's rule, a regulated vertical blocks search-term-mining until its channel clears compliance review, and no creative capacity removes the wear-out check entirely. That leaves the default three:

```
Routine:    Monthly spend health check
Runs:       monthly, before your allocation decision
Does:       cac-roas-benchmark against Google + Meta spend and pixel-reported conversions
Outputs to: <name a channel — Slack channel, doc, tracker>
First run:  dry run only, once channel is named
Caveat:     verdict is only as trustworthy as the pixel/tag audit above
```

```
Routine:    Weekly pacing check
Runs:       weekly, day of your team's spend review
Does:       ad-budget-pacing against the $35k/month total
Outputs to: <name a channel>
First run:  dry run only, once channel is named
```

```
Routine:    Quarterly kickoff re-invocation
Runs:       quarterly (no git history to infer pace from here — default cadence)
Does:       re-run advertising-kickoff to refresh routing and the artifact
Outputs to: <name a channel>
First run:  dry run only, once channel is named
```

**Held, not proposed:** monthly search-term mining (`ad-negative-keywords`) — blocked until the pixel/tag legal review clears this channel for that kind of monitoring. **Skipped:** creative wear-out check — no production capacity to act on its verdict this quarter.
