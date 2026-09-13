# Kindra Systems — Buyer Committee Map for ABM Launch

## Correcting one assumption before anything else

Your intent feed will not tell you who is on the buying committee. Intent data resolves to **accounts**, not people — roughly 81% account-level accuracy, and narrower topics only 60-70%. It tells you _which_ mid-market healthcare accounts are actively researching workforce analytics right now. It cannot tell you _who inside those accounts_ is involved, and licensing it doesn't change that. Its job in this plan is account selection, not role identification — see "How the intent feed actually gets used" below.

## Evidence plan for a 6-week window

You have three sources in play. Ranked by roles confirmed per hour of effort, given what you already have in hand:

1. **Closed-won/lost diff (42 won vs. 30 lost)** — same segment throughout, clean stage history. This is roughly a day of work and it is your primary source. Diff which roles/titles appear in won-deal stage history against lost-deal stage history; a role present in wins and absent or blocking in losses is your strongest signal.
2. **Call recordings on most deals** — an hour or two to pull notes once you know which roles the diff leaves ambiguous. Use these to fill gaps, not to start from scratch.
3. **Buyer interviews (15, next quarter)** — demoted, not deleted. They land _after_ your 6-week deadline, so they can't inform launch. Repurpose them as your post-launch confirmation pass: run them against whichever roles the diff and call notes leave as unresolved hypotheses.

Delete nothing else — you have no stated blocker on interview consent or intent-feed licensing (already signed), so both stay on the menu, just resequenced.

**Why this order, not intent data first:** intent data is a standing job to configure and re-tune, and it never confirms a role. Against a 6-week clock, that effort has to go to the diff and the recordings first.

## How the intent feed actually gets used

Build a **mini account list**: mid-market healthcare accounts (500-2,000 employees) the feed flags as actively surging on workforce-analytics or staffing-adjacent topics. Gate your committee-wide, multi-role targeting on that warm list at launch. Do not run full per-role targeting cold against your entire healthcare TAM — every person on a cold list is still cold from a messaging standpoint, intent or not. Expand to the full TAM only once the warm list is producing engagement.

## Committee size — working hypothesis, pending your diff

$90K ACV mid-market (500-2,000 employees) sits in TrustRadius's mid-market band (4-5 roles), not Gartner's "6-10," which is scoped to complex solutions only — don't carry that figure into a mid-market deal without evidence it applies. Healthcare's compliance layer (HIPAA, PHI-adjacent workforce data, BAA requirements) is the one thing that could push you a role higher than a same-ACV deal in a less-regulated vertical. Treat 5 roles below as the hypothesis to run the diff against, not the answer.

## Role map

Every row is a **hypothesis** until your diff and call notes confirm it — none of this is evidenced yet, because the diff hasn't run.

| Role                                                              | Evidence status                                                                                                                                         | Measured on                                                                    | Personal risk                                                                                        | Likely objection                                                | Messaging angle                                                                                                                            | Proof / offer                                                                                                                                                                                     | Targeting proxy                                                                                                                                               |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Champion** — VP HR / Chief Nursing Officer / Dir. Workforce Ops | Hypothesis — disproof: cut if absent from >80% of the 42 won-deal stage histories                                                                       | Turnover, overtime cost, staffing-ratio compliance                             | Sponsoring a tool that doesn't move the numbers, or understaffing that surfaces as a safety incident | "We already track this in [BI tool] / spreadsheets"             | Tie the offer to one workforce KPI they're already measured on — overtime cost or staffing-ratio variance, not a generic "analytics" pitch | Ungated guide or checklist (default rung); ROI calculator once the offer proves engagement                                                                                                        | Account list (mini, intent-warmed) + function: Human Resources OR Nursing/Clinical Operations, seniority: Director+                                           |
| **End user** — HR analyst / staffing coordinator / nurse manager  | Hypothesis — often collapses into champion at this deal size; confirm via call notes, not CRM stage (end users rarely show up in stage history)         | Daily scheduling/reporting workload                                            | Forced onto a tool that adds work before it removes any                                              | "Another dashboard to learn"                                    | Show the workflow it replaces, not the workflow it adds                                                                                    | Demo or hands-on trial, no gate                                                                                                                                                                   | Same function cell as champion, seniority: Manager and below — likely merges with champion's audience at this account size                                    |
| **Economic buyer** — CFO / COO                                    | Hypothesis — disproof: cut if finance sign-off appears in <50% of the 42 wins                                                                           | Labor cost as % of operating budget (the dominant line item in healthcare P&L) | Approving five figures that duplicates a capability finance already thinks it has                    | "What does this replace, and what's the payback?"               | Labor-cost efficiency framed as budget-line impact, not feature list                                                                       | ROI/savings calculator built on labor-cost data                                                                                                                                                   | Account list + function: Finance, seniority: VP+                                                                                                              |
| **Technical evaluator** — IT / Data lead                          | Hypothesis — disproof: cut if absent from next 10 wins once tracked                                                                                     | Integration load against HRIS/payroll/EHR/scheduling systems                   | Owning a broken integration, or a PHI-adjacent data flow nobody vetted                               | "Another vendor touching sensitive data"                        | Read-only, standard connectors; explicit statement of what data the platform does and doesn't touch                                        | Architecture doc; sandbox only if you have the engineering quarter to spend on it                                                                                                                 | Account list + functions: Information Technology AND Data/Analytics (cross-functional, expect to target both), seniority: Manager+                            |
| **Gatekeeper** — Compliance/Privacy officer, Procurement          | Hypothesis — check specifically against the 30 lost deals: a security/compliance objection appearing there and absent from wins is the clearest confirm | Vendor risk accepted on their signature; HIPAA exposure                        | Being the name on a BAA that turns out wrong                                                         | "Will you sign a BAA — where is the data hosted and processed?" | Compliance documentation pack — leads if certifications already exist, otherwise defer this rung until they do                             | Confirm before committing: if SOC 2/HIPAA compliance docs exist today, this is near-free and the highest-leverage offer in the map; if not, this is a quarter of work and should not block launch | Same account list + function: Legal & Compliance OR Information Technology, seniority: Manager+, reached at supplier-selection — before validation, not after |

**Structural check still open:** proxy-audience sizing against platform floors (20,000-50,000 practical floor for stacked function+seniority targeting) can't be confirmed without knowing your platform and your TAM's actual headcount — see open items below. A narrow ICP like this one is exactly where stacked cells (function + seniority + account list) risk falling under floor; be ready to merge the champion and end-user rows into one audience if the split doesn't clear it.

## Precision vs. reach: the one decision I can't make for you

$90K ACV alone doesn't clear the ~$100K threshold where full per-role campaigns are defensible regardless of account count. The swing variable is your named-account count in the 500-2,000-employee healthcare band, which you haven't given me:

- **Under ~500 named accounts:** per-role campaigns are defensible — reach is bounded either way, so precision is close to free.
- **At or above ~500:** default to the merged map — one primary angle (labor-cost/staffing-KPI framing) plus role-aware proof points (the compliance pack for gatekeepers, the ROI calculator for the CFO), rather than five parallel campaigns.

Given a 6-week clock and a role map that's still hypothesis-stage, I'd start with the merged map regardless of which side you land on, and split into full per-role campaigns once week 6 engagement data confirms which roles are actually worth splitting. That's the cheaper failure mode if the split turns out wrong.

## Sequencing

- **Champion + end user:** reach at problem identification — this is where your ungated, low-friction content should already be running.
- **Economic buyer:** business-case stage — ROI calculator engagement is your signal to advance.
- **Technical evaluator + gatekeeper:** reach _before_ validation, not at it. A security reviewer who arrives late in a healthcare deal reopens requirements and resets work already agreed — the compliance pack is the cheapest insurance in this whole map, which is exactly why confirming whether you have the certifications to build it now matters.
- Weight the CFO and compliance angles toward risk reduction, not urgency: no-decision, not a competitor, is what you're most likely fighting in healthcare procurement cycles.

## 6-week build sequence

| Week         | Action                                                                                                                                                                                                                                  |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Run the closed-won/lost diff on all 72 deals. Pull call-recording notes for any role the diff leaves ambiguous.                                                                                                                         |
| 1-2          | Configure the intent feed to produce the mini warm-account list for mid-market healthcare. Confirm compliance sign-off on the feed's re-use terms if not already cleared at licensing.                                                  |
| 2            | Lock the role map: mark each row evidenced or hypothesis-with-disproof-test, cut anything that fails the swap test (two roles with the same angle merge). Decide the precision-vs-reach posture once account count is in hand.          |
| 3            | Build offer assets, cheapest rung first: ungated guide/checklist for champion and end user, ROI calculator for economic buyer. Confirm compliance-pack feasibility (certifications in hand or not) before committing gatekeeper assets. |
| 4            | Build targeting proxies against your platform's floors; merge cells that undershoot.                                                                                                                                                    |
| 5            | Build creative variants per surviving angle; run the swap test again on finished copy, not just the plan.                                                                                                                               |
| 6            | Launch against the intent-warmed mini account list first. Track role engagement spread and account penetration as your live signal for whether to expand cold or hold the merged map.                                                   |
| Next quarter | Run the 15 buyer interviews against whichever roles are still hypothesis-status after 6 weeks of engagement data — that's a far more targeted interview list than 15 generic buyer conversations would have produced going in cold.     |

## What I need from you to finish this

- **Named-account count** in your 500-2,000-employee healthcare TAM — the swing variable for the precision-vs-reach call above.
- **Platform(s) and monthly budget** — determines whether your function+seniority cells clear the practitioner floor.
- **Purchase type** — net-new category, replacing an incumbent, or expanding from a smaller existing footprint. Changes who shows up and when.
- **Do SOC 2 / HIPAA compliance documentation already exist?** Determines whether the gatekeeper offer is a same-week asset or a quarter of work — don't let it block launch either way, but the answer changes what week 3 looks like.
- **Creative production capacity** — how many role-differentiated variants you can actually staff, independent of the strategic call above.

## Handoffs

- Audience construction, floor sizing, and budget allocation once the role map is locked: `mbfinotti/advertising-skills@ad-audience-targeting`.
- Ad copy per angle: `mbfinotti/advertising-skills@ad-copy-variants`.
