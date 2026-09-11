# BrightHarbor — Meta vs. Google Channel Plan (personal loans, Austin)

## Flag before anything else: the Meta plan as described won't run

Personal loans are a **credit** product. In the US, Meta requires **Special Ad Category** declaration for credit ads (mandatory since it's a financial product/service, required in the US since Jan 21, 2025). Once declared, Meta strips exactly the capabilities your plan depends on:

| You planned | What Special Ad Category does to it |
|---|---|
| 1% lookalike from best-customer list | Lookalike audiences are disabled — replaced by a weaker, broader "Special Ad Audience" (seed-list based, no precise % match) |
| 25–45 age targeting | Age locked to 18-65+ — no narrowing |
| Specific high-income ZIP codes | ZIP-level precision removed — locked to a 15-mile minimum radius |
| Exclude renters | Detailed-targeting exclusions removed entirely — can't exclude anyone by housing status |
| (implicit) gender narrowing | Also removed |

So Meta isn't disqualified as a channel — but the audience-surgery plan is. If you build it as described, Meta will reject it at ad-set creation. Budget accordingly: Meta becomes a **broad-audience, creative-led** channel here, not a precision-targeting one. (Verified against Meta's advertising policies as of this reporting period — reconfirm on the current policy page before campaign build, since these rules shift.)

Google has a parallel gate but it's operational, not a targeting strip: personal loan advertisers must complete **Google's Personal Loans certification** (product must carry APR ≤ 36% and a minimum 61-day term; state eligibility varies) before any ad serves. If any BrightHarbor product tier falls outside that (e.g., a short-term/high-APR SKU), that SKU cannot run on Google Ads at all — check this per-product before building the account. Certification can take days to a few weeks; start it now regardless of which channel you fund first.

---

## 1. Economics (assumptions flagged — confirm before locking budget)

Lending economics don't map cleanly onto the skill's default AOV×margin math (retail contribution logic vs. risk-adjusted net interest margin). Absent your real numbers, I'm using directional placeholders, clearly marked unverified:

- Average funded loan: **$12,000** (assumption)
- Contribution per funded loan (net of cost of capital, servicing, expected credit loss): **~$500** (assumption — this is the number that actually matters and only you have it)
- Payback target: 3–12 months (default band) → **allowable CAC ≈ $500** at a 1-month "payback," or scale up if you're comfortable amortizing CAC over the loan's revenue life rather than month one.

**What I need from you to firm this up**: allowable CAC per funded loan (you likely already track this internally), lead→funded conversion rate, and whether any repeat/refinance revenue extends LTV beyond the first loan. Until then, every CPA/CAC comparison below is directional.

## 2. Deleted channels

| Family | Gate failed | Reason, dated 2026-09-12 |
|---|---|---|
| Retail media | Disqualifier | Not applicable — no marketplace shelf presence for a lending product |
| B2B professional networks | Disqualifier | Consumer product, not B2B |
| Connected TV | Affordability / effort | $50K+ direct or $5K+ DSP entry, $1,500–$15K production, a full quarter before a readable result — doesn't fit a $40K/month budget that also needs to fund search, or a first-campaign timeline |
| Podcast/audio | Funding floor | ~$15K+ across 3+ shows to be measurable; would eat ~40% of total budget alone, starving search |
| Short-form video | Capacity | No stated in-house video production capacity for a first campaign — revisit once search + social are validated and a creative pipeline exists |

Personal-finance podcasts are a genuinely strong topical fit for this buyer (worth naming) — but they fail the funding-floor gate at this budget and don't meet the "concentrate, don't spread" rule for a first campaign. Reconsider as a second- or third-quarter add once search is proven and budget scales toward the ~$50K/month breakpoint.

## 3. Candidates ranked by value ÷ effort — survivors only

| Rank | Family | Value (presence / reachability / reach / measurability) | Effort (creative burn / skill+coordination / reversibility) | Value ÷ Effort |
|---|---|---|---|---|
| 1 | Paid search | 17 (5/4/4/4) — huge existing search demand for "personal loan," "debt consolidation," etc.; Google's geo-targeting still works down to postal code, unlike Meta's stripped ZIP precision | 5 (1/3/1) — text + landing page, but finance-vertical compliance review (APR disclosures) adds setup weight | **3.4** |
| 2 | Paid social (Meta), run broad | 13 (4/2/4/3) — reachability drops hard because the ICP (homeowner, 25-45, specific ZIPs, renter-excluded) is *not* expressible once Special Ad Category strips those tools | 9.5 (4/4/1.5) — first Meta campaign for the team, special-ad-category setup, and creative now has to do the audience-qualifying work targeting can't | **1.4** |

Both survive affordability and funding-floor checks at $40K/month (see Section 5). No departure from the default B2C ordering (search > social) — the regulated category reinforces it rather than changing it, because it specifically weakens social's reachability score, not search's.

Native/discovery, programmatic display, paid review listings: left in the unranked price-discovery bucket. Not worth testing on a first-campaign budget this concentrated — revisit as a second-channel candidate once search + social are validated.

## 4. Primary recommendation: Paid search

The category has real, high-intent search volume ("personal loan," "$10,000 loan," "debt consolidation loan"), your targeting isn't gutted the way Meta's is, and it returns the most per hour of setup. This is a capture-first case, not a creation-first one — Google's own benchmark data puts finance among the most expensive verticals (legal-tier CPCs, $20-60+ common in lending), but that's a cost problem, not a reachability problem.

## 5. Funding plan

$40,000/month, split ~80/20 for the first 90 days, per the skill's default concentration pattern:

- **Paid search: ~$30,000–$32,000/month.** Comfortably clears the "≥10 clicks/day, 3-5x target CPA" floor even at aggressive finance-vertical CPCs.
- **Paid social: ~$8,000–$10,000/month, one consolidated broad ad set** — not segmented by lookalike/ZIP/homeowner as originally planned. That segmentation would have split volume across multiple ad sets, each falling below Meta's ~50-optimization-events/7-day learning floor — the exact "$10K split five ways" anti-pattern the framework warns about, independent of the special-ad-category issue.
  - **Optimize to a cheap upstream event** (e.g., "application started," not "loan funded"). At an assumed $30-80 CPL, 50 events/week costs roughly $1,500-4,000/week — that clears within the $8-10K remaining budget. Optimizing straight to "funded loan" (a rarer, more expensive event) would very likely blow past what's left after funding search and never exit learning.

## 6. Test design

- **Price discovery**: ~$100-$300 each on search (exact-match core loan terms, Austin-metro geo) and social (one broad prospecting concept) — real CPC/CPL numbers before committing full budget; published benchmarks are unreliable in this vertical (search CPC alone spans $1.50-$50+).
- **Real test — search**: 3-5x target CPA per concept, 2-4 weeks, same weekday start/end.
- **Real test — social**: 3-5x target CPA per concept, 3-6 weeks (covers Meta's fatigue/learning cycle).
- **Pass**: CPA/CPL ≤ allowable CAC at 90-95% confidence — plug in your real number once confirmed (Section 1).
- **Kill**: 2-3x target CPA spent with zero qualifying leads after a readable sample, then diagnose before rerunning.

## 7. Second-channel trigger

Add a third channel only when search CPA rises on saturation signals (impression-share ceiling in the Austin metro) **or** budget crosses roughly $50K/month with payback still inside target — you're just under that breakpoint at $40K, which is itself a reason to hold at two channels for now rather than three. Next candidate in line: short-form video, once an in-house or agency creative pipeline exists, or podcast/audio, once budget clears its ~$15K measurability floor without starving search.

## 8. Measurement approach

- Start at UTM discipline + last-non-direct (default rung for a capture-heavy plan at this budget).
- Add self-reported attribution immediately ("How did you hear about us?" on the application form) — social enters the mix from day one, and platform dashboards structurally over-credit search/under-credit social by last-click.
- Use cost-per-funded-loan (ad spend ÷ funded loans from CRM/loan-origination system) as your MER-equivalent — platform-reported conversions won't match funded-loan reality, especially with the lead→funded lag and iOS tracking loss (30-45% of iOS conversions go dark).
- Verify application→funded tracking end-to-end before any spend moves — a regulated-category test on broken tracking measures nothing and voids the pass/fail criteria above.
- Add a geo-lift test on the Austin metro once search is scaled and stable — genuinely feasible here since you're already running a single, bounded geography.

---

**Before you spend anything**: confirm allowable CAC per funded loan (Section 1), start Google's Personal Loans certification now (it gates the primary channel), and rebuild the Meta plan around one broad, compliant ad set rather than the segmented lookalike/ZIP/renter-exclusion structure — that structure cannot be built on the platform as regulation stands today.