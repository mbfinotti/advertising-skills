## Short answer: yes — the plan has five separate problems, and they compound

"Simple and wide" collapses every lever this skill exists to control: recency, behavioral depth, message ladder, exclusion, and cap. Here's what breaks, then the fix.

### What's wrong

**1. The 365-day Meta window doesn't do what you think it does.**
Meta's retention ceiling for standard website custom audiences is **180 days**, not 365 (365 is only for Page/IG _engagement_ audiences). Ask for 365 and Meta silently truncates to 180. Not fatal by itself, but it means your "one 365-day audience" claim is already false on one of your two platforms.

**2. Safari/iOS at 55% makes the pixel windows mostly fiction anyway.**
Safari caps first-party JS cookies at **7 days** (24 hours if there's a click-tracking parameter). With 55% of your traffic on Safari/iOS, over half your visitors functionally disappear from a pixel-based audience after about a week — regardless of what window you configure. A "365-day" (or even 180-day) pixel-based Meta audience on this traffic mix is quietly built on the 45% of visitors who aren't Safari, while claiming to represent everyone. Given your cycle (95-day median, 150-day p80), this is the core mismatch: **your long-tail retargeting needs to be CRM-list-based, not pixel-based.** Google's remarketing list ceiling (540 days) survives this better technically, but suffers the same Safari undercounting on the pixel side.

**3. One audience, one message, to everyone, for a year — no depth stratification.**
This is the skill's textbook negative pattern: identical treatment regardless of recency or behavior, no ladder. A day-2 blog visitor and a day-300 pricing-page-and-trial visitor get the same "book a demo" ad. Day-2 visitor hasn't built any belief yet; hitting them with your highest-friction ask (a sales-assisted demo) before proof/objection content wastes the impression. B2B ladder order is **proof → objection → ROI → ask** — you're running only the last rung, on everyone, immediately.

**4. No converter exclusion.**
Nothing in your plan suppresses people who already booked a demo or became a customer. They keep seeing "book a demo" ads — wasted spend, and it reads as inattentive to a data-quality buyer evaluating whether you're rigorous.

**5. No frequency cap.**
Meta has no cap field on conversion-type objectives (only Reach/Awareness), and Google Display's cap controls are partial. Without a cap-proxy, a broad 180-365 day pool with one ad creative is an uncapped frequency machine — you won't notice fatigue until CTR is already down.

Net effect: platform-reported ROAS on this setup will likely look fine, because it's mostly re-showing "book a demo" to people who were either never going to convert from that visit (too cold, too early) or were going to convert anyway (already deep in a CRM deal stage) — the classic cannibalization signature this skill's measurement step exists to catch.

---

### Redesigned sequence

Your CRM percentiles (median 95d, p80 150d) are real converter data — good, that's the strongest input this skill uses. I'm using **150 days as the active-evaluation horizon** (the point past which a visit is stale, not the "hot" edge — B2B cycles this long need the horizon set at the tail, not the front). Everything below 150d needs internal stratification by depth; everything beyond is win-back, not conversion retargeting.

I don't have your traffic volume, which events are tracked (pricing page? trial/assessment start? CRM sync to ad platforms?), or your content assets (case studies, comparison pages) — so stage sizes and some rung choices below are provisional. Flagged where that matters.

**Stage table**

| Stage                  | Inclusion                                                  | Window / source                                   | Message intent                                                        | Concepts |
| ---------------------- | ---------------------------------------------------------- | ------------------------------------------------- | --------------------------------------------------------------------- | -------- |
| S1 High-intent         | Pricing-page view _(confirm this is tracked)_              | 0-14d, pixel                                      | Proof — case study or named-customer result                           | 3        |
| S2 Evaluators          | Any product/feature page view, no pricing view             | 0-30d, pixel (accept Safari undercount)           | Objection handling — security, integrations, data-accuracy comparison | 3        |
| S3 Open-deal air cover | CRM deals in evaluation/proposal                           | List, weekly refresh, runs to ~150d               | ROI content — aimed at the buying committee, not one visitor          | 3        |
| S4 Direct ask          | S1/S2 aged 15-150d, no open deal                           | CRM-matched list + pixel remainder                | The "book a demo" ask — this is where it belongs, not everywhere      | 3        |
| S5 Win-back            | Any past visitor/lead, 150-365d, no purchase, no open deal | List-based only (pixel is useless here on Safari) | Fresh proof/new-feature angle, not a repeat of the same ad            | 2-3      |

Note what this fixes: "book a demo" now runs only on S4, aimed at people who've shown depth _and_ aged past their hot window without an open deal — exactly the segment a direct ask converts, per the skill's rung logic. S1-S3 build belief first.

**Exclusion map**

- `RTG_PRICING_0-14` excludes `EXCL_CUSTOMERS`, `EXCL_OPENDEAL`.
- `RTG_FEATURE_0-30` excludes `RTG_PRICING_0-14`, `EXCL_CUSTOMERS`, `EXCL_OPENDEAL`.
- `RTG_DEAL_LIST` (S3) excludes `EXCL_CUSTOMERS`.
- `RTG_ASK_15-150` excludes all fresher stages, `EXCL_CUSTOMERS`, `EXCL_OPENDEAL`, `EXCL_CLOSEDLOST_90` (give sales a cooling-off window on recent losses).
- `RTG_WINBACK_150-365` excludes everything above.
- Converter/customer exclusion: no expiry (list-based, tied to CRM customer status — not a rolling pixel window, since this is B2B not repeat-purchase).

**Cap sheet**

- Meta: no cap field on conversion objectives. Cap-proxy: act when frequency exceeds ~5-7/week per person, or CTR falls 15-20%+ / CPM rises 10%+ against a 7-day rolling baseline (S1-S3 review every 2-3 days given small pools; S4-S5 weekly).
- Google Display: check for viewable-frequency controls on the campaign type in use; if absent, same proxy as above.
- Given likely-thin B2B volume, expect pools near the practical floor (~1,000 for both platforms) — **run the size check after exclusions before building**, and if any stage is under, collapse in this order: widen window → broaden trigger → merge adjacent stages → single warm pool. Given your numbers, S1 is the one most at risk of falling under floor; merging S1+S2 into one 0-30d intent stage is the likely fallback.

**Measurement plan**

- Per stage: spend, reach, frequency, CTR, CPM, platform CPA, new-vs-returning share.
- Committee-level for S3: cost per engaged account, account penetration.
- Blended: quarterly pipeline ÷ total paid spend (drops attribution entirely).
- Incrementality: **10-20% audience holdout on S4** (the direct-ask stage — highest "would have booked anyway" risk under your current single-audience design) for one full sales cycle (~150 days, so a real read takes time — plan for it). Decision rule: if holdout-measured lift on S4 is indistinguishable from zero, the demo ask isn't earning its stage; fold budget back into S1-S3 belief-building or prospecting.

---

### Design-gate scorecard for your original plan

- [ ] Tracking verified per stage — unknown, needs confirming
- [x] Boundaries from real lag data — you have this (95d/150d), just wasn't applied to stage design
- [ ] Every stage clears floor after exclusions — no exclusions exist, so untested
- [ ] Mutual exclusion — fails (one undifferentiated pool)
- [ ] Converter exclusion — fails (none)
- [x] No discount misuse — N/A, no discount rung exists (fine for B2B)
- [ ] Frequency cap / proxy — fails (none defined)
- [ ] 3+ creative concepts per stage — unknown, but a single audience implies a single ad
- [ ] Incrementality test scheduled — fails (none)

Your plan clears 1 of 9. The redesign above clears the structural ones; three things I still need from you to finish it for real: **(1)** is pricing-page/feature-page view tracked separately from generic pageviews, **(2)** is your CRM already synced to Meta/Google for list-based audiences, **(3)** rough monthly traffic and lead volume, so I can run the actual floor check instead of flagging it as a risk.
