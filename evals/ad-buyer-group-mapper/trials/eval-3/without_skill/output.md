# Loopwell LinkedIn Ads — Targeting Sanity Check + Messaging

## ⚠️ Targeting sanity-check first

**1. Audience size is at the floor, not "nicely focused."**
LinkedIn Sponsored Content reliably needs 15K–50K+ for stable delivery and reasonable CPMs. At 2,500–3,500 with exact-title + seniority stacking, expect:

- CPMs in the $80–150+ range (small B2B audiences bid up fast).
- Frequency cap hit within days — same 5–8 people seeing the same ad 10x/week by week 2.
- Slow, lumpy spend pacing — Meta-style always-on delivery doesn't work here.

Fix: don't add more filters on top (no "years of experience," no groups/skills). Refresh creative every 10–14 days (2–3 variants per campaign) and set an explicit frequency cap (3–4x/week) so you're not burning budget re-serving the same 3,000 people.

**2. "Head of Revenue Operations" and "VP Revenue Operations" likely overlap.**
Same function, adjacent seniority. If both run as separate exact-title campaigns without mutual exclusion, you'll bid against yourself for anyone whose title straddles the two (common — title data on LinkedIn is self-reported and messy). Action: add each campaign as an **audience exclusion** on the other. Keep them separate only if the messaging genuinely differs by seniority (see below) — otherwise merge into one "RevOps leadership" campaign with OR-matched titles.

**3. The 4th/5th roles aren't specified — I've assumed CRO/VP Sales and CFO/VP Finance** (the two other seats that typically sit on a $45K ACV revenue-intelligence committee). Swap these for your actual roles 4–5 and the messaging framework still applies. Flag this back to me if wrong and I'll redo those two rows.

**4. CFO/Finance is a weak fit for cold LinkedIn prospecting.** Finance leaders click revenue-tool ads far less than RevOps/Sales/Enablement. Recommend: don't run this as a standalone cold-prospecting campaign — fold Finance into the ABM motion (sales-assisted, or retargeting) instead of paying CPMs to reach a title that won't engage top-of-funnel.

**5. Straight-to-demo for the whole ABM list skips a step.** These 900 accounts know the brand, but "known" ≠ "ready to book a call" for a $45K considered purchase. Run two creatives in rotation rather than one hard-CTA ad:

- Proof/relevance ad (peer case study, forecast-accuracy stat) →
- Demo-request ad (retarget same audience after 1+ impression).

**6. Your ABM "900 accounts" is a company list, not a people list.** Uploaded as a Matched Audience, LinkedIn will serve to _everyone_ at those 900 companies unless you also stack job-title/seniority filters on top. Without that, your demo-request CTA reaches SDRs, interns, and unrelated departments — wasted spend and a bad look ("Request a Demo" ad hitting someone who can't buy). Layer the same 5-role title/seniority filter onto the ABM list.

**7. Set up conversion tracking before launch, not after.** $45K ACV means a multi-week sales cycle past the click. Use Lead Gen Forms or Insight Tag conversions for demo requests, and push offline stage changes back via Conversions API — otherwise LinkedIn's optimization will chase the wrong signal (clicks, not pipeline).

**What's actually right about the plan:** exact-title + seniority stacking is the correct instinct for a 5-seat enterprise committee at this ACV — you're not trying to reach a mass audience, you're trying to reach 15–20 real people per company. Keep that; just fix the mechanics above so the small audience doesn't burn out in week one.

---

## Revised budget split ($9K/month)

| Campaign                                       | Monthly budget | Audience (post-fix)                              | CTA                                      |
| ---------------------------------------------- | -------------- | ------------------------------------------------ | ---------------------------------------- |
| VP/Head of Revenue Operations                  | $1,400         | ~2,800 (title-exclusion applied)                 | Soft → ROI calculator                    |
| Director of Sales Enablement                   | $1,400         | ~3,000                                           | Demo (product-in-action)                 |
| VP Sales / CRO _(assumed)_                     | $1,400         | ~2,500                                           | Exec-level soft ask                      |
| CFO / VP Finance _(assumed)_                   | $600           | ~1,000                                           | Benchmark report (no demo CTA)           |
| ABM — 900 accounts, role-filtered              | $2,700         | ~1,800–2,500 people (varies by contacts matched) | Proof ad → Demo ad (2-creative rotation) |
| **Reserve for reallocation after week 3 data** | $500           | —                                                | —                                        |

---

## Messaging per role

### VP / Head of Revenue Operations

- **Pain**: Forecast built on rep-entered CRM data nobody trusts; QBR prep takes days of manual pulls.
- **Angle**: Replace guesswork with signal-based forecasting — one source of truth across CRM, calls, and email.
- **Headline**: _"Your forecast is only as good as your CRM data. Fix the data, fix the forecast."_
- **Proof point to source/validate**: forecast-variance reduction %, hours saved per QBR cycle.
- **Seniority split, if kept as two campaigns**: Head = tactical ("automate the pipeline hygiene work you're doing by hand"); VP = strategic ("give your CRO a forecast the board believes").
- **Format**: Single-image ad or Document ad (carousel of the forecast dashboard).
- **CTA**: Soft — "See the RevOps Forecast Accuracy Benchmark" (gated asset), not a hard demo ask at this stage.

### Director of Sales Enablement

- **Pain**: Reps drift from the playbook; nobody knows which talk tracks actually win deals; ramp takes too long.
- **Angle**: Call intelligence surfaces what your best reps actually say — codify it, coach to it, cut ramp time.
- **Headline**: _"Stop guessing what your top reps say. See it, coach it, scale it."_
- **Proof point to source/validate**: ramp-time reduction %, win-rate lift on coached reps vs. control.
- **Format**: Short product-clip video or single-image ad showing a call-insight snippet.
- **CTA**: Direct — "See a live call-analysis demo." Enablement leaders respond well to seeing the product, so this role can go straight to demo.

### VP Sales / CRO _(assumed — confirm this is your 4th role)_

- **Pain**: Pipeline coverage looks fine on paper; deals stall with no visibility into why until they slip.
- **Angle**: Surface at-risk deals before the rep's next update, not after the quarter's already lost.
- **Headline**: _"Know which deals are slipping before your reps do."_
- **Proof point to source/validate**: % reduction in late-stage deal slippage, days of earlier risk detection.
- **Format**: Single-image ad, exec-tone — no product screenshots, lead with the business outcome.
- **CTA**: Higher-touch — "Get a pipeline risk assessment" (sales-assisted, not self-serve demo).

### CFO / VP Finance _(assumed — confirm this is your 5th role, and see note above on weak paid-social fit)_

- **Pain**: Revenue forecast isn't reliable enough to plan headcount/budget against; hard to defend forecast confidence to the board/investors.
- **Angle**: A forecast the finance org can actually plan the business on.
- **Headline**: _"Plan the business on a forecast you can actually trust."_
- **Proof point to source/validate**: forecast variance translated to $ planning impact.
- **Format**: Document ad — benchmark report cover, not a product shot.
- **CTA**: Content download only ("Get the Revenue Forecast Accuracy Benchmark Report"). No demo CTA — route responders to the ABM/sales-assisted track instead of running this as a standalone paid channel.

### ABM — 900-account list (role-filtered)

- **Creative 1 (lead, weeks 1–2)**: Peer proof point — _"See how [mid-market segment] revenue teams cut forecast variance by [X]%"_ — case-study format, no hard CTA.
- **Creative 2 (retarget after 1+ impression, weeks 2+)**: _"You already know Loopwell — let's show you what it does for [pipeline/forecast accuracy/ramp time] specifically."_ → Request a Demo.
- **Format**: Conversation Ads or Message Ads for the highest-intent segment within the 900 (e.g., anyone who's visited pricing/case-study pages) — personalization at this stage justifies the higher CPM.
- Exclude this 900-list audience from all five role-based prospecting campaigns above, and vice versa, so you're not double-paying to reach the same person twice under two different messages.
