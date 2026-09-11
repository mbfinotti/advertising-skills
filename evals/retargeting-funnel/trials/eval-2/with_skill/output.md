Here's the plan. Two things up front, both required by the skill I'm following (`retargeting-funnel`) before I hand you any windows:

**I'm not going to hand you generic "what everyone uses" numbers.** That skill explicitly bans it — platform default windows are arbitrary relative to any specific business, and a default-length window on a 4-6 month cycle silently drops most of your pipeline. What I *can* do without a lag report: use the one piece of client-specific data you already gave me — **your stated deal cycle (4-6 months) with the security review sitting at the midpoint (~2-3 months in)**. That's a real proxy, ranked below a CRM export or analytics lag report in evidentiary weight, so **every window below is flagged provisional**. When you get 20 minutes, a CRM export of first-touch-to-close dates (even just closed-won deals, no dashboard needed) would let me replace "provisional" with "derived."

**Second, a scope note:** you asked for windows for 3 audiences. The skill's output is a full stage design (mutually exclusive stages, exclusions, caps, measurement) because ungated windows without exclusion logic is the #1 documented failure mode (self-competing ad sets, buyers still seeing acquisition ads). I've kept it as tight as 3-tracked-events allows — this is a 4-stage plan, not more.

Assumptions I'm making because Friday doesn't leave room to interview you — **confirm or correct these**:
- No discount/incentive exists in your funnel (standard for compliance sales to banks — procurement-driven, not price-driven). If wrong, tell me, it changes the final rung.
- You track: site visits, feature-page views, demo requests. Nothing about pricing pages, trial starts, or CRM deal stages was mentioned — if your CRM has deal stages, sequencing by those beats web recency for a sale this long (noted below).
- Channels aren't specified, so caps below are platform-agnostic proxies, not tuned to one platform.
- Traffic/lead volume wasn't given — mid-market-bank compliance software is a narrow ICP, so I'm flagging a real risk that these pools run thin. See the collapse note at the bottom before you build all four in-platform.

---

## Stage table

| Stage | Inclusion rule | Window (provisional) | Source | Message intent | Concepts |
|---|---|---|---|---|---|
| **S1 — Engaged, pre-review** | Submitted a demo request, deal not closed | 0–90 days | Pixel + CRM-list (list preferred — see note) | Proof: compliance credibility, named-bank case study if you have consent — arms your champion *before* the security review, which is your stated mid-cycle chokepoint | 3 |
| **S2 — Engaged, post-review** | Same demo-request pool, aged 90–180 days, deal still open | 90–180 days | CRM-list only (pixel won't survive this long — see caveat) | Objection handling on the specific security/compliance blockers that came up in review, then ROI content for the committee; ends on the hardest direct ask since there's no discount rung in this business (a tailored security-readiness assessment or a scoped pilot works as the B2B "incentive equivalent") | 3 |
| **S3 — Feature-page viewer, no demo request** | Viewed a feature/product page, never requested a demo | 0–60 days | Pixel | Objection handling (security/compliance angle) with a direct pull toward requesting a demo — the goal is promoting people into S1 | 3 |
| **S4 — Site visitor, no deeper engagement** | Any visit, no feature-page view, no demo request | 0–180 days | Pixel (degrades hard past ~7 days on Safari/iOS — this is a reach layer, not a hard-sell layer) | Category/authority awareness, low frequency, no hard ask | 3 |

Deepest action (demo request) gets the tightest *near-term* window (S1) per the depth rule, but because your cycle runs long, S2 exists specifically to keep air cover on that same person through the review and into close — that's the B2B departure from the B2C "deep = short and done" pattern.

## Exclusion map

- `RTG_DEMOASK_0-90` excludes `EXCL_CUSTOMERS`, `EXCL_CLOSEDLOST_90`.
- `RTG_DEMOASK_90-180` excludes `RTG_DEMOASK_0-90`, `EXCL_CUSTOMERS`, `EXCL_CLOSEDLOST_90`.
- `RTG_FEATURE_0-60` excludes `RTG_DEMOASK_0-90`, `RTG_DEMOASK_90-180`, `EXCL_CUSTOMERS`.
- `RTG_VISITOR_0-180` excludes `RTG_FEATURE_0-60`, `RTG_DEMOASK_0-90`, `RTG_DEMOASK_90-180`, `EXCL_CUSTOMERS`.
- `EXCL_CUSTOMERS`: closed-won accounts, list-based, **no expiry** — bank compliance contracts are multi-year, not a repurchase cycle, so a time-boxed exclusion (like the 180-day one that fits e-commerce) would let you re-target a live customer.
- `EXCL_CLOSEDLOST_90`: closed-lost accounts, 90-day cooling-off before they re-enter any stage — confirm this window with sales; I'm defaulting to the pattern used in comparable B2B sequences.

## Cap sheet

| Stage | Cap or proxy | Detection signal | Review cadence |
|---|---|---|---|
| S1 | ~3/week/person if account-based (LinkedIn-style); 4-5/week proxy elsewhere | CTR down 15-20%+, CPM up 10%+, negative feedback rising vs. 7-day baseline | Weekly |
| S2 | Same proxy — small list, refresh creative every 2-3 weeks so a thin pool doesn't burn out on one concept | Same | Weekly |
| S3 | 4-5/week proxy | Same | Weekly |
| S4 | 2-3/week proxy — this is reach, not conversion, so cap conservatively | Same | Bi-weekly |

Whatever platform(s) you actually run this on, check whether it exposes a real impression-cap field before trusting a "hard cap" — most only expose it on awareness objectives, not conversion ones. That changes whether the number above is a setting or a manual trigger.

## Measurement plan

- Per stage: spend, reach, frequency, CTR, CPM, platform CPA, new-vs-returning share, plus pipeline-specific: influenced opportunities, cost per engaged account.
- Blended sanity metric: quarterly pipeline ÷ total paid spend.
- Incrementality: given a likely-thin pool (narrow ICP, no volume numbers yet), run a **15-20% audience holdout** across S1/S2 for one full sales cycle (~6 months) — that's the cheapest design that still works on a small B2B pool; ghost ads and geo holdouts need scale or coordination you probably don't have here. Decision rule: if held-out accounts open opportunities at the same rate as targeted ones, cut S1/S2 spend regardless of platform-reported ROAS.

## Before you build these in-platform

1. **Pool size is unverified.** I don't have your traffic or demo-request volume. Check each stage against your platform's floor *after* exclusions — if S1, S2, or S3 don't clear it, the fix order is: widen the window → broaden the trigger → merge stages → fall back to one combined warm pool (the Ben Heath position — legitimate default for a niche ICP like mid-market banks, not a failure state).
2. **Pixel reliability past ~7 days is unreliable on Safari/iOS.** S2's 90-180 day window and most of S4's 180-day window should be CRM-list based wherever you have an identified contact (S1/S2 definitely do, since a demo request is a named lead); S3/S4 anonymous traffic has no such fallback, so treat their long tail as undercounted, not absent.
3. **Confirm the no-discount assumption** and whether your CRM tracks deal stages — sequencing S2 by actual deal stage (post-review, in-negotiation) beats a flat 90-180 day calendar window and is a small edit once you have it.