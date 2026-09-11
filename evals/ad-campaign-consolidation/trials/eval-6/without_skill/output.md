# Brightpath paid media consolidation — plan

## 1. Reframe the problem

Two different mechanisms are being conflated. Untangle them first:

- **Meta (social):** the problem is targeting fragmentation — 9 ad sets each with a dozen stacked interest/job-title filters, all shown the identical creative. Splitting a thin budget 9 ways starves every ad set of the ~50 weekly conversions Meta's algorithm needs to exit learning phase, and overlapping interest stacks make you bid against yourself, inflating CPMs.
- **Google (search):** the "10x CPA before merging" rule is a **Target CPA bidding readiness rule**, not a consolidation rule. It doesn't apply to merging ad sets on Meta at all. Don't let that advice bleed across channels.

Also sanity-check the arithmetic before acting on it: if $15K/month is split across both channels and 9 ad sets, raising every ad set's daily budget to 10x CPA will blow past $15K. That mismatch is itself evidence you're over-segmented — fix segmentation first, budget math second.

## 2. Meta: consolidate delivery, not message

Root cause: message differentiation is being forced through **audience targeting** (fragile, post-iOS14.5 signal-poor) instead of **creative** (which Meta's algorithm actually reads well).

- Cluster the 9 personas into 3–4 campaigns by buying-committee role or deal-stage proximity (e.g., Economic Buyer: CFO/CEO; Technical Buyer: IT admin/Security; Champion: HR director/HR ops), not 9.
- Within each campaign, use Advantage+ audience (broad, algorithm-driven) instead of stacked interest/job-title filters. Interest stacking is a pre-ATT relic; the algorithm now out-performs manual stacking once given enough conversion signal.
- Serve **persona-specific creative** (headline/copy naming their pain point) as multiple ads inside each ad set. Let Meta's creative-level delivery optimization route each creative toward the people who engage with it — this is where your "who sees which message" control now lives, not in the targeting filters.
- Use Campaign Budget Optimization (CBO) across the ad sets in each campaign so budget flows to what's converting, instead of 9 fixed, undersized pools.

Net effect: fewer, better-fed ad sets; message control moved from targeting (which was already leaking) to creative (which the CMO can actually audit).

## 3. Medlow's $2,000/month guarantee — carve it out, don't fold it in

A CBO campaign will happily reallocate spend away from an underperforming ad set — which breaks a contractual guarantee. Two ways to protect it, pick one:

- **Preferred:** keep the Medlow line as its own standalone campaign with Ad Set Budget Optimization (ABO), fixed at ≥$2,000/month, entirely outside the consolidated CBO campaigns. Simplest to prove compliance to the CMO or to Medlow if audited.
- **If it must live inside a CBO campaign:** set a per-ad-set **minimum spend limit** of ~$65–70/day on that ad set (Meta supports min/max spend limits per ad set within CBO). More fragile — verify weekly it's actually hitting the floor, since CBO can still throttle a limit-protected ad set on efficiency grounds in edge cases.

Do not let "consolidate the 9 ad sets" implicitly include Medlow. Treat it as a compliance line item, not a growth line item.

## 4. Keep persona-level reporting alive after consolidation

Consolidating delivery structure doesn't have to consolidate reporting structure — decouple them:

- Tag every ad with a `persona` parameter via UTM (`utm_content=persona-cfo`) and/or Meta ad naming convention, independent of which ad set/campaign it lives in.
- Build the CMO's weekly view as a **breakdown by ad/creative**, not by campaign — Ads Manager and your CRM/analytics can both slice by that persona tag regardless of consolidation.
- This gives the CMO the same "spend and leads per persona" view they have today, even once the underlying ad set count drops from 9 to 3–4.

## 5. Google Search: get to Target CPA readiness correctly

- The 15-conversions/30-days threshold gates **Smart Bidding**, not manual budget levels — don't wait passively.
- Interim step: switch to **Maximize Conversions** now (no historical conversion minimum required). It still automates bidding and, unlike your current manual CPC, actively helps you accumulate the conversion volume needed to graduate to Target CPA faster.
- Once you're near 15 conversions/30 days, *then* apply the 10x rule: set the campaign's daily budget to at least 10x your intended target CPA before switching to Target CPA, so the algorithm has room to spend and isn't budget-throttled during its own learning phase.
- This is a **search-only** step. Do not apply it to the Meta consolidation — different mechanism, different guarantee threshold, different platform.

## 6. Sequencing

1. Week 1: Set up UTM/persona tagging on all social ads (reporting decoupling), before touching structure.
2. Week 1: Spin off Medlow into its own protected campaign/ad set with the spend floor.
3. Week 2: Cluster remaining personas into 3–4 campaigns, switch to Advantage+ audience + CBO, load persona-specific creatives per ad set.
4. Week 2 onward, in parallel: switch Search to Maximize Conversions; track conversion count weekly toward the 15 threshold.
5. Once search hits 15+ conversions/30 days: raise budget to ≥10x target CPA, then switch to Target CPA.
6. Give the consolidated Meta structure 1–2 weeks in learning phase before judging performance — don't re-fragment early on a noisy first week.