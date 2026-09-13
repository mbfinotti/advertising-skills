# Quillhaven LinkedIn Retargeting Build — Full Plan

Applied `retargeting-funnel` skill (v1.4.9). Short version first, full deliverable below: the five-tier structure is the right instinct, but three parts of the plan as stated won't work or won't hold up under LinkedIn's own constraints. Flagging those first because they change the build, then the four required artifacts.

## The three corrections that matter most

**1. "I'll create the audiences the day we go live" — this breaks the whole plan.**
LinkedIn Matched Audiences are **non-retroactive**: collection starts only at audience creation, nothing before that is recoverable. If you create the pricing-visitor audience on launch day, your "30-day pricing visitor" segment has zero members that morning and only reaches full size 30 days later. Your 90-day blog audience takes 90 days to fill; your 180-day webinar audience takes 180. **Create all five audiences now, this week** — they cost nothing to have sitting empty, and every day earlier is a day of backfilled pool by the time spend turns on.

**2. "Seed a LinkedIn lookalike" — LinkedIn discontinued lookalikes in February 2024.** Replaced by Predictive Audiences, which work differently: they model off an _outcome_ list, not a raw visitor list. Seeding from pricing-page visitors gives volume (~700/mo) but low quality — tire-kickers, competitors, students, no-budget browsers all view pricing pages. At $40k ACV, precision matters more than reach. Recommend seeding instead from demo-requesters + closed-won customers (a real converted-outcome list), accepting that this pool grows slowly (see sizing below) — and verify current seed-size guidance in Campaign Manager before building, since Predictive Audiences' minimums move.

**3. Manual bids across all five, on pools this size, will underdeliver.** LinkedIn's own guidance: small retargeting/ABM pools deliver better on automated bidding — manual bids on thin pools tend to starve. At 11k sessions/month, several of your five tiers are going to land near LinkedIn's practical floor (see below), which is exactly the condition where manual bidding hurts you. Recommend automated bidding (Maximum Delivery) at launch on every stage, revisit manual only for a pool that's clearing 1,000–5,000+ with room to spare.

## Data gaps — named, not guessed past

Per the skill's rule, I won't invent stage windows without lag data, so here's what's assumed and why:

- **No time-to-conversion data given.** Proxy used: sector-typical B2B SaaS sales cycle for $40k ACV, sales-assisted — commonly 60–120 days. This is the _weakest_ tier of proxy (cheapest, least specific to you). Pull an analytics lag report or a CRM sales-cycle export before locking these windows in — at this ACV, if your real cycle looks like the worked example in this skill (median 74 days, 80th percentile ~110 days), **30-day windows on pricing and feature-page visitors are cutting off before most of your pipeline has even converted.** That's the single highest-value fix available to you before launch.
- **"1.5% request demos"** — read as 1.5% of the ~700 pricing visitors (≈10–11 demo requests/month), not 1.5% of total traffic (which would be 165/month and implausibly high for this ACV). Confirm which you meant — it changes the seed-list math below materially.
- **Feature-page traffic isn't broken out.** Blog (7,150/mo) + pricing (700/mo) leaves ~3,150/mo across feature pages, homepage, and everything else. I can't split that without your analytics. Treat the feature-page pool size below as a placeholder, not a number to build a floor decision on.
- **Video-view and webinar-attendance tracking status unconfirmed.** Before either audience can be built, verify the events actually fire and land where LinkedIn's Insight Tag or a CRM sync can read them — this is a hard prerequisite (`ad-conversion-tracking`), not a nice-to-have.

## Stage table (revised)

Depth order used: pricing > feature-page > video-viewer (assumed — see note) > webinar attendee (treated as a parallel high-intent list, not ranked by page depth) > blog reader.

| Stage      | Inclusion rule                                                 | Window / source                                                           | Message intent                                                                                                                                     | Concepts | Projected pool (after exclusions)                                         | Floor risk                                                                                         |
| ---------- | -------------------------------------------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| S1 Pricing | Pricing-page view                                              | 0–30d, pixel — **provisional, likely too short; re-derive from lag data** | Proof — named-customer case study closest to their likely use case                                                                                 | 3        | ~650–700                                                                  | 🟡 Above LinkedIn's 300-member floor, below the 1,000–5,000 practical floor. Expect elevated CPMs. |
| S2 Feature | Feature/product-page view, no pricing view                     | 0–30d, pixel — same caveat as S1                                          | Objection handling — security, integrations, "how it fits your stack"                                                                              | 3        | ~1,200–1,800 (unverified)                                                 | 🟡 Same risk profile as S1, worse if real feature-page traffic is lower than the placeholder       |
| S3 Video   | Video-view event, not S1/S2                                    | 0–30d, pixel — **pending tracking verification**                          | Depends what's in the video: if product-demo, pair with proof/objection rotation; if top-funnel explainer, treat closer to blog                    | 3        | Unknown                                                                   | 🔴 Highest collapse risk — no volume data, tracking unconfirmed                                    |
| S4 Webinar | Webinar attendee (registration platform / CRM), not a customer | 180d, **list-based, not pixel**                                           | ROI/committee content — arm the attendee to bring this to their buying committee; coordinate with a parallel SDR follow-up outside the ad platform | 3        | Unknown — could sit at or below the 300-member floor depending on cadence | 🔴 Same risk class as S3                                                                           |
| S5 Blog    | Blog-page view, not in S1–S4                                   | 90d, pixel                                                                | Awareness reinforcement / thought leadership — nudge toward a pricing visit, not a hard ask (they're your shallowest, coldest signal)              | 3        | Comfortably tens of thousands, dedup notwithstanding                      | 🟢 No concern                                                                                      |

Two tiers (S3, S4) are unbuildable as sized today — you don't have volume numbers, and for S4 the arithmetic is genuinely worrying: one webinar a quarter at 50–100 live attendees puts your 180-day cumulative list right at LinkedIn's 300-member floor. Before launch, run the collapse rule (widen window → broaden trigger → merge adjacent stages → single pool) on whichever of S1–S4 comes back thin once real numbers land. Given 11k sessions/month is a genuinely small site (the worked B2B example in this skill needed merges at 38k/month), plan on merging at least one pair going in rather than treating five standalone campaigns as guaranteed.

## Exclusion map

Naming convention: `RTG_<depth>_<window>` / `EXCL_<what>_<window>`.

- `RTG_WEBINAR_180` (list, refreshed weekly) excludes `EXCL_CUSTOMERS` (no expiry) and `EXCL_DEMO_REQUESTED_90`.
- `RTG_PRICING_30` excludes `RTG_WEBINAR_180`, `EXCL_DEMO_REQUESTED_90`, `EXCL_CUSTOMERS` — a webinar attendee gets the sales-ready ROI creative, not a generic pricing nudge.
- `RTG_FEATURE_30` excludes `RTG_PRICING_30`, `RTG_WEBINAR_180`, `EXCL_DEMO_REQUESTED_90`, `EXCL_CUSTOMERS`.
- `RTG_VIDEO_30` excludes `RTG_PRICING_30`, `RTG_FEATURE_30`, `RTG_WEBINAR_180`, `EXCL_DEMO_REQUESTED_90`, `EXCL_CUSTOMERS`.
- `RTG_BLOG_90` excludes all four stages above plus `EXCL_DEMO_REQUESTED_90`, `EXCL_CUSTOMERS`.
- `EXCL_DEMO_REQUESTED_90` = 90 days: once someone's asked for a demo, sales owns them — pull them out of top-funnel retargeting rather than competing with your own SDR outreach.
- `EXCL_CUSTOMERS` = no expiry, list-based. Closed-won customers never re-enter this funnel; expansion/renewal is a separate campaign, not this one.

No discount rung — correctly absent from your ask; not applicable at this ACV. The ladder's final rung (S5→ ask) should be the hardest direct ask you have (demo/assessment), not a softer offer.

## Cap sheet

LinkedIn exposes no user-set frequency cap on non-awareness objectives — pacing is internal, so every row below is a cap-_proxy_: the reading at which you intervene, watched against a 7-day rolling baseline (CTR −15–20%+, CPM +10%+, rising negative feedback).

| Stage      | Cap-proxy      | Creative refresh                      | Review cadence                                                                                                  |
| ---------- | -------------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| S1 Pricing | ~3/week/person | Every 2 weeks (small pool burns fast) | Every 2–3 days                                                                                                  |
| S2 Feature | ~3–4/week      | Every 2 weeks                         | Weekly                                                                                                          |
| S3 Video   | ~3–4/week      | Every 2 weeks                         | Weekly                                                                                                          |
| S4 Webinar | ~2–3/week      | Every 3–4 weeks                       | Weekly — also coordinate cadence with any parallel sales email/SDR touches so the same contact isn't triple-hit |
| S5 Blog    | ~3–5/week      | Every 3–4 weeks (bigger pool)         | Weekly                                                                                                          |

## Measurement plan

Per stage: spend, reach, frequency, CTR, CPM, LinkedIn-reported conversions/CPA, and (in place of "new-vs-returning," which doesn't apply here) stage-to-demo-request rate and CRM-matched pipeline influenced.

Blended sanity metric: pipeline (or closed-won $) ÷ total marketing spend, tracked monthly.

Incrementality: with S1 at only ~700/month, a standard 15–20% holdout is ~100–140 people — thin, and at a multi-month sales cycle it needs a full quarter, not the 6-week window used in faster-cycle examples, to read cleanly. Run a 20% holdout on S1 (your highest "would've converted anyway" risk) for one full quarter, decision metric = CRM opportunity creation rate among holdout vs. targeted, not platform-reported conversions — per Gordon/Zettelmeyer, platform numbers overstate lift by roughly 7–9.5x, and retargeting is the worst-case scenario for that bias since it targets people already most likely to convert.

## Design gate

- [ ] Tracking verified for pricing/feature/blog (video and webinar **not yet verified** — blocking for S3/S4)
- [~] Stage boundaries — provisional, proxied from sector-typical cycle; **re-derive from a real lag report before spend scales**
- [ ] Delivery floor after exclusions — S1/S2 marginal, S3/S4 unknown pending real volume
- [x] Mutual exclusion map complete (above)
- [x] Converter exclusion defined and written (90d demo, no-expiry customer)
- [x] No discount rung — not applicable at this ACV
- [~] Frequency cap-proxies defined; will need recalibration once real frequency data exists
- [x] 3 creative concepts staged per tier
- [ ] Incrementality test scheduled — design named above, needs a start date once launch is confirmed

## Before you build anything

1. Create all five audiences (plus the predictive-audience seed list) **this week**, not at launch — non-retroactive collection means every day of delay is a day of backfill lost.
2. Pull a real time-to-conversion export (analytics or CRM) and re-check the 30-day windows on S1/S2 against it.
3. Confirm feature-page traffic volume, and whether video-view and webinar-attendance events are actually instrumented anywhere LinkedIn or your CRM can read them.
4. Decide the demo-request interpretation (1.5% of pricing visitors vs. of total traffic) — it changes whether a demo-requester seed list is viable at all.
5. Swap manual bids for automated at launch; revisit once a pool is proven to clear 1,000–5,000 with headroom.

Handoffs for the adjacent work this plan doesn't cover: tracking verification → `ad-conversion-tracking`; the actual ad copy per stage → `ad-copy-variants` / `ad-creative-brief`; ongoing frequency/decay monitoring after launch → `ad-creative-fatigue`; where this LinkedIn build sits against your total prospecting budget → `ad-spend-allocation`.
