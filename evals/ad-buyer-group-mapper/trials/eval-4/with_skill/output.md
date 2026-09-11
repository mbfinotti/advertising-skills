# Corvine Data — Buyer Committee Map & Campaign Plan

## 0. The six-campaign structure is deleted — here's why

Three independent gates in the buying-committee framework each rule out six simultaneous per-role campaigns, so this isn't a close call:

- **Effort ceiling.** One marketer producing ~1 ad concept/month cannot staff six creative sets plus six reviewer/optimization loops. This alone deletes the option regardless of the other two gates.
- **ACV threshold.** Per-role campaigns are defensible above ~$100K ACV. Corvine is $30K — roughly a third of that.
- **Market-size threshold.** Per-role campaigns are defensible below ~500 named accounts. The Corvine ICP is 40,000 companies — two orders of magnitude too large to enumerate as an account list, let alone six of them.

This is structurally the same shape as the SMB/no-committee-evidence negative case documented in this skill's reference material: solo-ish marketer, thin budget relative to headcount ambitions, no closed-won evidence yet, ICP too broad to list. The documented fix there is the one applied below: collapse to the roles the evidence actually supports, run **one consolidated campaign**, and use the second role as a **proof-point variant inside that campaign**, not a separate audience or budget line.

**What replaces "six campaigns, six audiences, six budgets":** one campaign, two live roles, one primary angle + one proof-point variant, phased in at the pace you can actually produce creative — which still gives you a real multi-month build-out, just not six parallel ones on day one.

## 1. Committee summary

- **Size:** No closed-won/lost data, call notes, or interviews were supplied, so this is title-inference only — the weakest evidence rung in this framework, used as a starting hypothesis, not an assertion. Published bands are a sanity check only, not a number to cite as fact: TrustRadius (2024) puts SMB committees at 2-3 people, rising with deal size; at $30K ACV and a 40,000-company ICP wide enough to suggest a partly self-serve/lower-mid-market motion, 2-3 is the plausible band, not Gartner's "6-10," which applies to complex enterprise solutions only.
- **Purchase type:** Not stated. Assumed net-new-category (data-quality monitoring is still an emerging buying category for most teams) — confirm or correct this.
- **Precision-vs-reach posture:** Merged map — one primary angle (champion/end-user) plus one role-aware proof-point variant (economic buyer), inside a single campaign. Not a single undifferentiated message, because the economic buyer's objection ("what does this replace / what's the ROI") is different enough from the champion's to need its own proof, and your production cadence can support one added variant without threatening the primary asset's cadence.
- **Named deletions from the menu (not demoted — deleted):**
  - Six separate per-role campaigns — effort ceiling + both thresholds, see §0.
  - Account list and intent-ranked account list as targeting proxies — 40,000 accounts is too large to enumerate or maintain a list against; falls back to function + seniority.
  - Exact job-title targeting — worst on every axis (setup effort, reach, platform title-parsing at ~30-50% coverage); function + seniority substitutes.
  - Benchmark report as an offer type — a quarter of data-collection effort a solo marketer doesn't have, and no proprietary data set was mentioned.
  - Demo/trial request and sandbox access as near-term offer types — parked, not confirmed deleted: state your sales capacity before adding either as a CTA. Without confirmation, an ungated asset is the safe default.

## 2. Role map

| Role | Evidence | Measured on | Personal risk | Likely objection | Messaging angle | Proof / offer type | Targeting proxy | Est. proxy audience vs. floor |
|---|---|---|---|---|---|---|---|---|
| **Champion / end user** (Data or Analytics Engineer, "data quality owner") | Hypothesis — title inference only. Disproof test: if this person doesn't show up as the primary contact in your first 10 closed-won deals, split champion and end user apart. | Pipeline/dashboard reliability, time spent firefighting bad data | Getting paged for an outage or bad-data-driven bad decision; blamed for dashboards nobody trusts | "We already have dbt tests / a few checks — why another tool?" | "Stop firefighting broken dashboards — catch data issues before your stakeholders do" (verify against your own support tickets or trial-signup free-text for the actual phrase they use) | Ungated checklist/guide (near-zero production cost — matches your 1-concept/month ceiling) | Function: Engineering / IT / Data (whichever discrete category your platform exposes), Seniority: Senior IC–Manager | Order-of-magnitude estimate only — function+seniority pools on a professional network typically clear the 20K-50K practical floor easily; confirm in-platform forecaster before spending against it |
| **Economic buyer** (Head of Data / VP Engineering / CTO — title unconfirmed) | Hypothesis — title inference only. Disproof test: cut this as a separate proof variant if the champion is reported as also holding budget authority in your first 10 deals (common at this ACV — may collapse into one role). | Engineering hours burned on incident response, ROI of tooling spend, trust in data feeding company decisions | Approving a $30K line that can't show payback; shipping a board-level decision off bad data | "What does this replace, and what's the payback?" | "Fewer data-fire drills means fewer engineering hours burned putting them out — the payback shows up in your team's roadmap, not just a dashboard" | ROI/savings calculator (light build — a week, still inside a solo marketer's reach once, not monthly) as a **second ad + landing page inside the same campaign**, not a new campaign | Same function pool, Seniority: Director-VP+ | Narrower than the champion pool by seniority filter alone — still likely clears the significance floor; verify in-platform before launch |
| **Data/security reviewer** (parked — not targeted) | Hypothesis, unconfirmed whether this stage exists at all at $30K self-serve-adjacent ACV. Disproof test: don't build anything for this role unless it appears as a blocker in your first 5 sales-cycle notes. | N/A — not yet evidenced | N/A | "What access does this tool need to our warehouse, and is it certified?" | Not written yet — held until evidence exists | If it appears: a one-pager assembled from certifications you already hold (near-zero effort *if* held; a quarter if not — confirm your cert status before promising this) | Not targeted with ad spend. Have the asset ready to hand to sales, not to run as a campaign. | N/A |

Two roles get ad budget. The third is a labelled hypothesis with a disproof test, parked as sales collateral, not a campaign — this is the mechanism that keeps the map honest without reinventing the six-campaign mistake under a different name.

## 3. Budget and cadence — one campaign, phased to your real production rate

- **$15K/month, one campaign, not six.** Splitting six ways would put ~$2,500/month behind each audience — below the level needed to reach the 5,000-signal floor reliably, let alone the 20K-50K practical floor for a real learning phase. Concentrating spend behind two roles instead of six is what makes the budget functional at all.
- **Cadence matched to 1 concept/month capacity:**
  - **Month 1:** Launch the campaign with the champion/end-user asset (ungated checklist). This is the always-on core creative.
  - **Month 2:** Add the economic-buyer ROI proof-point as a second ad + landing page in the *same* campaign (seniority-filtered ad set, not a new campaign). Start retargeting engaged champion-role viewers into economic-buyer content — that's a handoff to the retargeting-funnel skill, not new ad spend here.
  - **Month 3:** Second champion-role variant (e.g. a short proof/case-study cut of month 1's asset — cheaper to produce than a from-scratch concept).
  - **Month 4:** Check engagement split between the two live roles. If the economic-buyer ad set isn't engaging, that's evidence against the hypothesis — revisit its disproof test rather than assuming more creative will fix it.
  - **Month 5:** Only if sales has flagged a security/procurement blocker by now: build the reviewer one-pager. Otherwise, skip it this cycle.
  - **Month 6:** Re-run the committee-size sanity check against whatever closed-won or call-note evidence has accumulated in the first ~180 days. That's the point to decide whether a role has earned its own line item — not before.

## 4. Sequencing logic

- Champion/end-user content runs from day one (problem-identification stage, where this role naturally arrives).
- Economic-buyer content is introduced in month 2 and weighted toward risk-reduction/payback framing, not urgency — 40-60% of B2B deals end in no-decision, most of that from indecision, not preference for a competitor, and urgency messaging backfires on exactly the buyer role most prone to stalling.
- The reviewer asset, if it turns out to exist, needs to land before validation, not during it — the cheapest insurance in this whole map is having it ready before it's asked for, which is why it's prepped as a standing asset rather than something you build under deadline pressure mid-deal.

## 5. What's unconfirmed — answer these to tighten the map

- **Company size within the 40,000-account ICP** (SMB vs. lower-mid-market) — currently assumed from ACV + ICP breadth; changes the committee-size band.
- **Any existing evidence** — even a handful of closed-won/lost notes or sales call recordings would move roles off pure title-inference and let you name real objections instead of hypothesized ones. This is the single highest-leverage next step per the evidence-gate ranking (a diff of won vs. lost deals is the strongest source available for the least effort).
- **Ad platform** — assumed a professional network (function+seniority targeting depends on it); confirm before building audiences.
- **Purchase type** (net-new vs. replacing an existing data-quality process) — changes which objection leads.
- **Sales capacity** — determines whether a demo/trial CTA is affordable later, or stays off the menu.

## 6. Handoffs

- Audience construction, exact sizing, and budget pacing mechanics for the two live ad sets → `ad-audience-targeting`.
- Copy variants for the two approved angles → `ad-copy-variants`.
- The month-2 champion→economic-buyer retargeting sequence → `retargeting-funnel`.