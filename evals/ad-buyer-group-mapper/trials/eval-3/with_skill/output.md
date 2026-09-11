# LinkedIn Ads Sanity Check + Messaging — Loopwell

## 1. Sanity check: four problems in the current plan

**Title + seniority can't stack.** On LinkedIn, Job Title and Seniority are mutually exclusive facets — the platform will not let you AND them together. The plan as described ("exact job titles... stacked with seniority filters") isn't buildable as specified; you'll be forced to pick one. Titles also only resolve 30-50% of the real population (stale/inflated self-reported titles, unlisted variants), so title-only targeting misses more people than it catches. Function + seniority instead of exact title roughly triples reach at similar engagement, and is the correct default proxy here.

**2,500-3,500 members is too narrow to spend against, not "nicely focused."** The technical floor for a matched/saved audience is ~300, but the floor where results actually reach significance is ~5,000, and the practical floor for delivery at typical budgets is 20,000-50,000. At $9K/month split five ways ($1,800/campaign), five audiences this size will hit frequency fatigue in days and burn spend on repeat impressions rather than new reach.

**Five full per-role campaigns aren't earning their cost yet.** The skill's own threshold: per-role campaigns are defensible below ~500 named accounts or above ~$100K ACV. Loopwell is $45K ACV (under the bar) and the addressable list is 900 accounts (over the bar). Neither condition clears. Default should be a merged campaign structure — one or two audiences, role-aware creative variants rotating inside them — not five standalone campaigns each needing its own budget and delivery volume. Five campaigns become defensible if you have in-house creative capacity to actually produce and coordinate five distinct creative sets; say so if that's the case and the recommendation flips.

**The 900-account ABM list is a targeting signal, not a warm audience — going straight to demo-request is the wrong offer for a cold list.** Uploading the list tells the platform who to show ads to; it does not mean those people have engaged with Loopwell. Cold demo/trial requests convert around 1.5-4%; cold gatekeeper-type roles essentially never book one from a cold ad. Low-friction offers (calculator, guide) convert 10-15% cold. Gate the demo ask on a second touch — someone who already clicked or engaged once — rather than opening with it.

One thing the plan gets right: for the 900-account list specifically, **account list + function + seniority** (not exact title) is the strongest proxy available — the list is small enough to enumerate, which is exactly the condition where that combination outperforms everything else, including intent data.

## 2. Committee, corrected

"Head of Revenue Operations" and "VP Revenue Operations" are the same functional slot at two seniority labels, not two committee roles — most orgs use one or the other depending on company size, not both simultaneously. Targeting them as separate campaigns duplicates spend against the same person-type. Collapse to one role: **RevOps Leader**, targeted by function (not title) across a Director-through-VP seniority band.

That leaves three named-role slots unaccounted for out of your five. I don't have your committee evidence (closed-won diff, call notes), so the two below are title-inference hypotheses only — the weakest rung on the evidence ladder — flagged with a disproof test each. Confirm or cut them against your own data before spending against them.

| # | Role | Evidence |
|---|------|----------|
| 1 | RevOps Leader (Head/VP/Director Revenue Operations) | User-provided (title inference) |
| 2 | Director of Sales Enablement | User-provided (title inference) |
| 3 | CRO / VP Sales — Initiator | Hypothesis. Disproof: cut if this title never appears in the next 10 closed-won threads as the one who opened the deal. |
| 4 | Sales Ops Manager — Technical evaluator | Hypothesis. Disproof: cut if no CRM/data-integration question ever surfaces before contract. |
| 5 | IT/Security or Procurement — Gatekeeper-blocker | Hypothesis. At $45K ACV this may not survive contact — cut if absent from the next 10 closed-won notes. |

## 3. Role map

| Role | Measured on | Personal risk | Likely objection | Messaging angle | Proof/offer (default rung) | Targeting proxy |
|---|---|---|---|---|---|---|
| RevOps Leader | Forecast accuracy, pipeline conversion, CRM data quality reported up to CRO/CFO | A forecast miss or messy pipeline traced back to them in front of the board | "We already have a CRM and dashboards, why add another tool" | Stop defending the forecast with guesswork — see deal risk before the board asks | ROI/savings calculator (hours saved on pipeline review, forecast variance reduction) | Function: Operations (test Sales too) + Seniority: Director-VP. Not exact title. |
| Director of Sales Enablement | Rep ramp time, quota attainment %, playbook adoption | Enablement spend gets cut when it can't be tied to quota attainment | "Reps already have too many tools, they won't use one more" | Prove which coaching and playbooks actually move win rate, instead of guessing | Ungated checklist ("signals that predict a rep misses quota") | Function: Sales AND Training/Sales Enablement (test both — cross-functional role straddles cells) + Seniority: Director |
| CRO/VP Sales (Initiator) — hypothesis | Bookings, pipeline coverage ratio | Missed number traced to blind spots in pipeline visibility | "How is this different from what our BI/CRM already shows" | Surface the deals quietly slipping before they show up as a miss | Ungated guide | Function: Sales + Seniority: VP-C-suite |
| Sales Ops Manager (Technical evaluator) — hypothesis | Data integrity, integration uptime, admin overhead | Blamed if a new tool breaks the CRM data model or adds admin burden | "What does this touch in our stack, and who maintains it" | Fits your existing CRM without another manual sync to babysit | Ungated technical/integration one-pager | Function: Operations + Seniority: Manager-Senior |
| IT/Security or Procurement (Gatekeeper) — hypothesis | Vendor risk exposure, compliance posture | Owns the fallout if a vendor causes a breach or compliance gap | "What's your data handling and security posture" | Compliance/security pack removes the validation-stage veto before it stalls the deal | Compliance/security one-pager (near-zero effort if certifications already exist) | Function: IT or Legal/Compliance + Seniority: Manager+ |

Audience note: expect these to land well short of even 5,000 on function+seniority alone for a $45K mid-market ICP. If so, don't stack further AND conditions — that's the point past which delivery degrades. Widen the seniority band or merge adjacent functions before adding another filter.

## 4. Recommended structure (instead of 5 title campaigns)

**Campaign A — ABM (900-account list).** Targeting: account list + function + seniority, one campaign, role-aware creative rotating by the table above. Start everyone on the low-friction offer (calculator/guide/checklist per role). Move an individual to the demo-request creative only after one engagement (click, video view, form-adjacent action) — not on first exposure.

**Campaign B — Prospecting beyond the 900 accounts.** Function + seniority only, no title, merged creative set covering RevOps Leader and Sales Enablement angles (your two evidenced roles) as the primary pair, with the three hypothesis roles as proof-point variants inside the same campaign rather than standalone campaigns, until each is confirmed.

Rough budget split: weight toward Campaign A first — it's the list you already have permission-adjacent reach into, and the merge-to-fewer-audiences approach lets $9K/month actually build frequency instead of getting diluted across five thin buckets. Precise split, sequencing tests, and audience sizing math belong to your audience-targeting workflow next — this is a targeting sanity check and messaging pass, not a media plan.

## 5. Sequencing

- **Now:** CRO/Initiator and RevOps Leader — low-friction content, problem-identification stage.
- **Before validation, not during:** Sales Ops (technical evaluator) and IT/Security (gatekeeper) — reaching them before they're pulled into a late-stage review is the cheapest insurance in the plan; a security reviewer added late can reopen requirements and reset the deal.
- **Throughout, weighted toward risk reduction:** RevOps Leader and any gatekeeper-type role should see risk-reduction and proof messaging, not urgency — pressure tends to push these roles toward no-decision rather than toward yes.

**Open items before you spend:** confirm the three hypothesis roles against your own closed-won notes, and confirm whether you have creative capacity to actually run role-differentiated variants — that capacity is what would justify moving back toward more, smaller campaigns later.