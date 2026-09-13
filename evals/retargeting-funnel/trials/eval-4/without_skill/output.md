## Verdict

🟠 Solid structure, three real risks before you spend a euro on it.

## 1. Audience sizing — two tiers are thin

- **Pricing 30d (~700/mo):** near LinkedIn's ~300-member floor, well under the 1,000–5,000 you want for stable delivery under manual bidding. Expect weekly reach of ~150–250 and fast frequency saturation.
- **Feature-page 30d:** likely thinner than pricing. Your ~11k sessions minus 65% blog minus pricing leaves ~3,150 sessions/mo spread across product, features, resources, demo-request, etc. Combine **all** feature pages into one audience — don't split per feature — and check the actual count in Campaign Manager before allocating budget.
- **Webinar 180d:** list upload (email match), independent of pixel volume, but LinkedIn typically only matches ~40–65% of uploaded emails to a profile. Pool multiple webinars if any single session is under ~150 registrants.

## 2. Blog readers 90d is a mismatch for a $40k ACV sale

- 65% of 11k = ~7,150 sessions/mo, ~90-day pool likely 10–15k uniques. That's a top-of-funnel, low-intent crowd for sales-assisted procurement software.
- ❌ Don't retarget all blog readers with a demo-request CTA — you'll burn spend on students, competitors, and casual readers.
- ✅ Fix: either scope the audience to BOFU blog categories only (buying-stage, procurement-pain content), or layer LinkedIn firmographic targeting on top (job function = Procurement/Finance, seniority = Director+). Treat this as your lowest-budget, nurture-content tier, not a conversion tier.

## 3. Five campaigns, all manual bid, is more overhead than the data supports

Manual bid on sub-1,000-person audiences usually just underspends — not enough auction volume to pace against.

- Merge pricing + feature-page visitors into one "high-intent" campaign (vary the ad creative per segment, don't split the campaign) until each clears ~1,000.
- Keep webinar attendees as its own campaign — highest intent, distinct message ("you were in the room, here's the next step").
- Keep blog as its own campaign but smallest budget, awareness/nurture creative only.
- Clarify "video viewers" before building a line for it: native LinkedIn video-ad engagement (LinkedIn tracks this itself, no size risk) vs. YouTube/website-embedded video (needs an Insight Tag event, likely very thin for a niche B2B product). Different setup, different risk profile.

## 4. Lookalike → it's called Predictive Audiences now

LinkedIn sunset classic Lookalike Audiences in 2023; the current feature is **Predictive Audiences**, seeded from a conversion signal, not raw traffic. Two problems with seeding it off pricing-page visits:

- 700 pageviews is a weak, noisy signal — includes competitors, researchers, job-seekers.
- ✅ Better seed: closed-won customers if you have enough (ideal), or demo-requesters as a fallback (~1.5% conversion rate gives you a larger, higher-quality pool over 90–180 days than raw pricing hits). Verify current minimum seed-size requirements in Campaign Manager — this feature has moved fast and I can't guarantee today's exact threshold.

## 5. Launch-day audience creation will leave you empty for weeks

Pixel-based audiences (pricing, feature, blog, video) only count forward from when the Insight Tag/URL rule goes live — **no backfill**.

- If you create them "the day we go live," pricing/feature audiences won't reach usable size for ~2–4 weeks, and blog for ~90 days.
- ✅ Install/verify the Insight Tag now and create the audience _definitions_ now (free to sit unused in Campaign Manager) so they're pre-populated at launch.
- Webinar list audience is unaffected — upload-based, fine to build same-day.

## Revised shape

| Tier                                                | Window | Status                                                         |
| --------------------------------------------------- | ------ | -------------------------------------------------------------- |
| Pricing + feature visitors (merged)                 | 30d    | ✅ build now, launch when clearing ~1,000                      |
| Webinar attendees                                   | 180d   | ✅ own campaign, build day-of is fine                          |
| Blog readers (BOFU subset or firmographic-filtered) | 90d    | ⚠️ own campaign, lowest budget, nurture creative               |
| Video viewers                                       | 30d    | ⚠️ clarify source first                                        |
| Predictive audience                                 | —      | seed from demo-requesters or customers, not raw pricing visits |
