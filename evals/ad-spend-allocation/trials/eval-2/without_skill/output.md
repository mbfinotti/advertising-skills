# Loam & Ember — Paid Media Plan (5-Channel, $12K/mo)

## Before this goes to the freelancer: three things need attention

**🔴 Meta pixel is unverified — do not turn on Purchase-optimized spend until this is fixed.**
An unverified pixel two weeks old commonly means: Purchase event not firing, wrong/missing value parameter, or duplicate events with no dedup. If Meta starts optimizing toward a broken signal, it will spend $2,400/mo learning the wrong thing and the CPA number coming back will be meaningless. Fix path (1-2 days of freelancer work, do it first):
1. Meta Events Manager → Test Events → place a real test order, confirm `Purchase` fires with correct `value` and `currency`.
2. Check Event Match Quality score (aim for "Good"/"Great," not "Low").
3. Install Conversions API (server-side) alongside the browser pixel if the freelancer can — iOS/ad-blocker loss otherwise costs you 15-30% of trackable conversions and inflates reported CPA.
4. Only after this: switch Meta campaigns to Purchase-optimized.

**🟠 A $35 target CPA hasn't been checked against actual margin.**
AOV $120 with unknown margin means the freelancer can't tell if $35 CPA is comfortable or break-even-and-hoping-for-repeat-purchase. Cookware typically runs 55-70% gross margin before shipping (cookware ships heavy, so freight eats into this more than most DTC categories) and 3% payment processing. Rough math: if gross margin is ~60% ($72) minus $8-15 shipping/fulfillment minus ~3% processing (~$3.60), contribution margin before ad spend lands around $50-60. A $35 CPA target is workable on that basis but leaves thin room — worth confirming actual numbers before holding the freelancer to $35 as gospel. **Action: get a real contribution-margin-per-order number this week; until then, treat $35 as directional, not a hard kill switch.**

**🟠 Splitting $12K five ways gives each channel $2,400/mo (~$554/week) — thin for learning phases.**
At a $35 CPA target, $554/week buys ~16 conversions/week per channel. Meta's ad-set learning phase wants ~50 conversions/week to exit properly; TikTok and YouTube have similar appetites. Below that, algorithms stay in a perpetual "learning limited" state and CPA stays volatile and high. This doesn't mean don't do 5 channels — it means each channel's freelancer setup below is built to concentrate signal (fewer ad sets/campaigns, not more) so the thin budget isn't fragmented further.

If it were my call, I'd run Google Search + Meta at full strength for the first 2-3 weeks while the pixel gets fixed and TikTok/Pinterest/YouTube creative gets built, then bring the other three online — rather than all five cold on day one. But the request was for the five-way split, so here it is, built to survive being thin.

---

## The split

| Channel | Monthly budget | % of budget | Role |
|---|---|---|---|
| Google Search (non-brand) | $2,400 | 20% | Highest intent, direct response |
| Meta (FB + IG) | $2,400 | 20% | Direct response + retargeting once pixel verified |
| TikTok | $2,400 | 20% | Native video, younger/discovery-driven buyer |
| Pinterest | $2,400 | 20% | Planning/inspiration, longer purchase window |
| YouTube | $2,400 | 20% | Upper-funnel + direct via Video Action campaigns |
| **Total** | **$12,000** | **100%** | Blended target CPA: **$35** (directional pending margin confirmation) |

---

## Channel-by-channel brief for the freelancer

### 1. Google Search — Non-Brand — $2,400/mo
- **Campaign type:** Search, "Maximize Conversions" with a target CPA cap once ~15-20 conversions have landed (Smart Bidding needs a data floor). Start on manual/enhanced CPC for the first 1-2 weeks if conversion volume is uncertain.
- **Keyword themes:** category + material ("stainless steel cookware set," "cast iron skillet," "ceramic nonstick pan"), use-case ("cookware for gas stove," "non-toxic cookware set"), gift/occasion terms if relevant.
- **Match types:** Phrase + Exact only at this budget level. Avoid Broad match until there's enough negative-keyword history — Broad will burn a $2,400/mo budget fast on irrelevant queries.
- **Negatives:** recipe/how-to/DIY terms ("how to season cast iron," "cookware recipes"), job/wholesale terms, "cheap"/"free" unless that's genuinely the audience.
- **Extensions:** sitelinks, callouts (free shipping / warranty / non-toxic materials if true), price extensions.
- **Expected volume:** cookware CPCs commonly run $1.50-$4. At $2,400/mo that's roughly 600-1,600 clicks; at a 2-3% site conversion rate, ~15-45 conversions/mo. This is the channel most likely to land near the $35 CPA target since intent is highest — weight it up first if reallocating later.

### 2. Meta (Facebook + Instagram) — $2,400/mo
- **Gate:** do not launch Purchase-optimized campaigns until pixel verification above is done. Until then, run a small Traffic or Engagement campaign to build creative/audience data without wasting spend on a broken optimization signal.
- **Structure once verified:** 1 campaign, 1-2 ad sets max — do not split into 4-5 ad sets at this budget, it starves each of data. Use Advantage+ audience (broad) rather than narrow interest stacking; let the algorithm find buyers once the signal is trustworthy.
- **Creative:** UGC-style video (unboxing, demo, "cooking with it" clips), testimonials, before/after. Cookware is tactile — show the product in use, not just product shots.
- **Math check for the freelancer:** $2,400/mo ÷ $35 CPA ≈ 68 conversions/month ≈ 16/week — below Meta's ~50/week ideal for exiting learning phase per ad set. Keeping it to one consolidated ad set is the mitigation.

### 3. TikTok — $2,400/mo
- **Verify the TikTok pixel/events the same way as Meta before optimizing to Purchase.**
- **Campaign type:** Conversion objective, optimize to Complete Payment.
- **Creative:** native-feeling, not polished ads — fast cuts, creator-style, "what's in my kitchen," satisfying cooking B-roll. Spark Ads (boosting organic-style posts) tend to outperform standard in-feed ads here.
- **Expectation-setting:** likely the noisiest channel at this budget — plan for a longer learning period and don't judge CPA before ~3-4 weeks of data.

### 4. Pinterest — $2,400/mo
- **Campaign type:** Conversions objective, standard Pins + Idea Pins, plus catalog/Shopping ads if the product feed is set up.
- **Attribution window:** set to 30-day click / 1-day view (Pinterest default is often shorter) — Pinterest users plan and pin weeks before buying, so a short window will understate performance and make the freelancer cut a channel that's actually working.
- **Creative:** styled kitchen/recipe imagery, "kitchen must-haves" boards, gift-guide angles.
- **Expectation-setting:** don't compare Pinterest's CPA to Meta/Google at the 30-day mark — give it closer to 60 days before judging.

### 5. YouTube — $2,400/mo
- **Campaign type:** Video Action Campaigns or Demand Gen, optimized to purchase via Google Ads conversion tracking (separate tag from the Meta pixel — confirm this is wired to GA4/Google Ads, not assumed to piggyback on Meta's).
- **Creative needs:** at minimum a 15s and 6s bumper cut; ideally one 30s+ story-driven ad. If no video assets exist yet, this is the one channel that can't launch without creative production time — flag that dependency now.
- **Expectation-setting:** YouTube often looks weak on last-click CPA while actually assisting conversions on other channels. Don't kill it purely on standalone CPA before ~60 days; watch view-through conversions too.

---

## Tracking setup checklist (hand to freelancer as a gate before scaling any channel)
- [ ] Meta Pixel: Purchase event verified via Test Events, correct value/currency, Event Match Quality "Good"+
- [ ] Meta Conversions API (server-side) installed
- [ ] TikTok Pixel: same verification pass
- [ ] Google Ads conversion tag installed independently (not relying on Meta pixel data)
- [ ] Pinterest tag installed and Purchase event verified
- [ ] GA4 (or equivalent) as the source-of-truth cross-channel view, since each platform will self-report favorably

## 30-day review
- Pull CPA per channel against the $35 target (Pinterest and YouTube graded on a longer clock, per above).
- Reallocate from underperforming channels toward Google Search / Meta first — they're the two proven direct-response channels and most likely to be data-ready fastest.
- Revisit the $35 target once real contribution-margin-per-order is in hand — this plan should not stay fixed on an unverified number past month one.