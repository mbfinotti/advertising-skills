# Karvela Systems — LinkedIn Audience Targeting Plan

## Assumptions and open items (flag before you launch)

Three inputs the skill needs weren't in your message. I scored them neutral and proceeded rather than blocking — confirm before launch:

- **Customer list size / current-customer count within the 600 health systems** — changes the net size of the account list and the exclusion list. Needed before upload.
- **Site traffic / LinkedIn Insight Tag volume** — determines whether the retargeting pool clears LinkedIn's 300-member floor on its own, or needs an engagement-audience fallback.
- **Buying-signal data** (RFP/tender postings, GPO contract timing, new VP Supply Chain hire at a target account) — none was named, so no signal-triggered tier is in this plan. This is a real gap, not a rejected option: see the tier table below.

ICP evidence for now rests on your own sales-defined titles and the account's live conversion history (3 demos/week), not a closed-won CRM analysis. That's usable but thin — validate against closed-won data within the next review cycle.

## 1. ICP summary

- **Attributes:** employer = one of ~600 named US hospital networks/health systems; function = supply chain / procurement; seniority = Director and above (VP of Supply Chain, Director of Procurement, and equivalents). Evidence: sales-team-defined, drawn from the current draft and live account — not yet CRM-validated.
- **Signals:** none currently evidenced. Candidates worth building toward: RFP/tender activity, GPO contract renewal timing, a new VP Supply Chain/CPO hire at a target account. Until one is evidenced, no behavioral/signal-triggered tier is funded (see deleted tiers).
- **Broad-vs-layered verdict: explicit layers.** Every condition on that side of the ledger is met at once — a 24,000-person universe, a narrow two-title ICP, a $9k/month budget, and 3 demos/week (nowhere near a learning threshold). This is not a close call.

## 2. The core finding: your universe is a closed list, not an open market

600 health systems is not "a market with an addressable slice" — it's an enumerable list you can upload directly. That collapses several of your six campaigns into duplicates of the same population:

- "Exact job titles," "interest-based," and "broad prospecting" all draw from the same ~24,000 people. Running three separate definitions of one closed population guarantees overlap well past the skill's 50% merge threshold — you don't need the platform's overlap tool to know this; the math is structural (three inclusion definitions over one closed pool of ~24k people).
- LinkedIn recognizes only ~30% of freeform job titles, so "exact titles" alone quietly excludes most of your real audience. Function + seniority targeting typically triples the matched audience at similar engagement — use that instead of exact titles.
- A 600-account list is precisely what a matched company list is for. There's no daylight between "prospecting" and "your customer-list/ABM tier" here — they're the same 600 accounts, one used as an inclusion list, the other (implicitly) as an exclusion list.

**Net: consolidate six campaigns into two funded tiers**, plus the customer list running as suppression (and, later, a seed — not a funded campaign today).

## 3. Tier table

| Tier                                                     | Defining signal (evidence)                                                                                                                       | Est. size                                                                                 | Exclusions applied | Budget                     | Success criterion                                                                                      |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- | ------------------ | -------------------------- | ------------------------------------------------------------------------------------------------------ |
| **Target-account list** (cold/prospecting, consolidated) | Matched company list of the 600 health systems + function (supply chain/procurement) + seniority (Director+) overlay, Audience Expansion **off** | ~24,000 minus exclusions (net TBD pending customer count)                                 | E1, E2, E3, E4     | $240/day (~$7,200/mo, 80%) | Proxy-event CPA ≤ ~$34 (floor math below); demo CPA tracked as true KPI, not optimized to directly yet |
| **Retargeting pool**                                     | Site visitors + LinkedIn page/content engagers, warm                                                                                             | Unknown — verify against Insight Tag data; likely thin for a niche B2B audience this size | E1, E2, E3         | $60/day (~$1,800/mo, 20%)  | Cost/demo watched directly, not forced through the 50/week learning floor                              |

Rows sit in efficiency order (retargeting > cold prospecting), with budget weighted the opposite way — prospecting gets the larger share because it's the slower, less efficient signal that needs the volume to say anything. This is the same pattern as any B2B plan in this posture, not a re-rank.

**Tiers deleted, with reasons:**

- **Exact-job-titles as its own campaign** — folded into the consolidated prospecting tier as function+seniority targeting. Standalone title-only targeting misses ~70% of the real audience and duplicates the population below.
- **Interest-based set** — deleted. Interest targeting on LinkedIn is a weak, largely deprecated precision tool, and on a 24k closed universe it draws from the same pool as prospecting — pure overlap with no new reach.
- **Broad prospecting with Audience Expansion on** — deleted, not demoted. For a defined ICP this small, Audience Expansion pushes spend toward people outside the 600 target accounts entirely. This is the platform's own stated failure mode for exactly this situation, and it's the most expensive of the six drafted tiers to run wrong.
- **Lookalike** — deleted for now. LinkedIn replaced lookalike with Predictive Audiences in 2024, which needs an engagement/conversion seed to build from. At 3 demos/week you don't have one yet. Revisit once the two funded tiers produce enough volume to seed it (seed selection itself is out of scope here — see references).
- **Customer-list tier as a funded campaign** — reclassified, not deleted. It runs as a suppression list against every funded tier (mandatory) and, later, as the seed for Predictive Audiences once it has enough engagement behind it. Running it as its own paid campaign today would either duplicate the account list or need its own 300+-matched-account floor check you haven't done yet.

## 4. The budget math you need to see before launching

Demo-request CPA target is $310. The standard learning-threshold floor (~50 optimization events/ad set/week — this figure comes from Meta's documented threshold; LinkedIn doesn't publish an equivalent number, so verify with your rep, but it's the standard cross-platform default) requires:

> daily budget ≈ (target CPA × 50) ÷ 7 = (310 × 50) ÷ 7 ≈ **$2,214/day per ad set** (~$66,400/month)

Your total budget is $9,000/month (~$300/day) — **across every tier combined**, not per ad set. No structure, however consolidated, clears that floor while optimizing directly to "demo request." This isn't a targeting problem your six campaigns could have fixed; it's a budget-vs-objective mismatch that exists regardless of how the audiences are sliced.

Fix order per the skill (merge upward → cheaper proxy event → cut) — merging is already done above. Apply the second step:

- **Optimize both tiers to a cheaper higher-funnel proxy event** (e.g., a lead-gen form open or a gated-content download) instead of the raw demo request. At the prospecting tier's $240/day, the floor math inverts to a workable number: 240 × 7 ÷ 50 ≈ **$34** proxy-event CPA needed to clear learning — a realistic number for a mid-funnel B2B event, unlike $310.
- Track **demo requests as the true KPI offline**, via CRM/offline conversion import, not as what the campaign optimizes toward yet. Re-evaluate switching to demo-CPA optimization once volume and budget both grow.
- Retargeting's pool is inherently small by design (bottom-funnel, lowest volume/highest intent) — don't force it through the same learning-floor logic. Watch cost/demo on it directly instead.

For context: your current $9,000/month against 3 demos/week (~13/month) works out to roughly **$692 effective cost/demo** — more than double the $310 target. Under this skill's own kill rule (2× target CPA with results meaningfully worse than the best tier), the status quo six-campaign structure would already be a kill. That's the actual case for restructuring now, not a hypothetical one.

## 5. Exclusion matrix

| List                               | Source                                  | Applied to                                                                      |
| ---------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------- |
| E1 Current customers               | Customer list upload, refreshed monthly | All funded tiers                                                                |
| E2 Employees + known competitors   | Company exclusion list                  | All funded tiers                                                                |
| E3 Recent demo requesters, 90 days | CRM upload, weekly                      | All funded tiers (don't re-solicit a warm lead as cold)                         |
| E4 Retargeting pool                | First-party audience                    | Prospecting tier only (higher-intent tier suppressed from the lower-intent one) |

Re-check both tiers' post-exclusion size against LinkedIn's 300-member floor once the customer count and site-traffic volume are known — this is the first thing to verify before spend goes live, not after.

## 6. Test sequence

1. **Week 1 — structural cleanup, no new spend yet:** collapse the six drafted campaigns into the two above; upload E1–E4; turn Audience Expansion off permanently; switch title targeting to function+seniority.
2. **Weeks 2–3:** launch both tiers at the stated budgets, optimized to the proxy event; demos tracked offline via CRM. If the retargeting pool doesn't clear 300 matched members, fall back to engagement audiences in fill-speed order: video viewers → page/content engagers → lead-form openers.
3. **Weeks 4–6:** evaluate cost/proxy-event against the ~$34 floor-adjusted target, and cost/demo informally (volume will still be low — don't over-read it yet). Apply promote (beats target, scale ≤20%/week) / hold (within ±20% or still learning) / kill (2× target with 50%+ worse results) per tier.
4. **Week 6+:** revisit funding the customer list as a Predictive Audiences seed once tiers 1–2 have produced enough conversions to build one. Revisit splitting the account-list tier from a broader prospecting tier only if it saturates — not before, per the default B2B rung for a universe this size.

## 7. Compliance notes

Not a regulated category. The product targets professional attributes (job function, seniority, employer industry) of people who work in healthcare organizations — it does not target or infer individual health conditions, which is the actual trigger for the regulated-category rules. No restricted-mode targeting applies. Standard exclusions (customers, employees, competitors) still apply regardless.

## 8. Review cadence

- Overlap audit before adding any tier back (especially before ever re-introducing a title-only or interest layer).
- Weekly floor check during the weeks 2–6 test window.
- Customer/demo exclusion uploads: monthly and weekly per the matrix above.
- Full plan review at quarter-close or on ICP change — sooner if the customer-list and traffic-volume unknowns get resolved, since both materially change tier sizing.

## References

- mbfinotti/advertising-skills@lookalike-audience-seeds — seed selection once the account has enough engagement to build a Predictive Audiences seed.
- mbfinotti/advertising-skills@retargeting-funnel — per-stage messaging/windows for the retargeting tier sized above.
- mbfinotti/advertising-skills@ad-buyer-group-mapper — VP Supply Chain and Director of Procurement are two seats on a larger buying committee (likely also finance/CFO sign-off and IT/security vendor risk); worth mapping before your next creative pass.
