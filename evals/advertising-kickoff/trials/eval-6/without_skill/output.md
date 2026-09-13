I dropped the idea of shipping a spreadsheet file — code execution is blocked in this sandbox — so here's the full plan, including the dashboard structure written out so you can build it in Sheets in five minutes.

---

## 1. Set your CAC ceiling before you benchmark against anyone else

Industry numbers only matter relative to what _you_ can afford to pay. Compute this first:

- **LTV = price × gross margin × avg. subscriber lifetime (months)**
  At $12/mo, ~85% margin, and (say) a 10-month average lifetime → LTV ≈ $102.
- **Target CAC = LTV ÷ 3** (standard subscription guardrail) → ≈ **$34**.
- **Target payback period = Target CAC ÷ (price × margin)** → ≈ 3.3 months.

If you don't know your average subscriber lifetime yet, that's the real gap — pull it from Stripe/App Store Connect before spending a dollar. Use 8–12 months as a placeholder and correct it within 60 days; don't let ad spend outrun an unproven retention assumption.

## 2. Benchmark ranges (consumer subscription / journaling-wellness category)

I don't have live data access this session, so treat these as **directional industry ballparks**, not sourced facts — validate against RevenueCat's _State of Subscription Apps_ report and each platform's own benchmark tool once you have real spend data.

| Metric                                                  | Typical range | Note                                                                                           |
| ------------------------------------------------------- | ------------- | ---------------------------------------------------------------------------------------------- |
| Blended CAC, paid sub ($5–15/mo apps)                   | $25–$80       | Journaling/self-improvement sits mid-pack vs. dating/finance (pricier) or utilities (cheaper). |
| Apple Search Ads — CPI, long-tail keywords              | $2–$8         | Highest available intent at this budget size.                                                  |
| Apple Search Ads — cost per paid conversion             | $15–$45       | Best first channel to test.                                                                    |
| Meta — CPI, wellness category                           | $2–$6         |                                                                                                |
| Meta — cost per trial start                             | $8–$25        |                                                                                                |
| Meta — cost per paid sub                                | $30–$100      | Tightens fast past ~50 conversions/week.                                                       |
| TikTok — CPI                                            | $1–$4         | Cheap reach, lower intent — awareness more than direct CAC at this budget.                     |
| Reddit — CPC (r/journaling, r/DecidingToBeBetter, etc.) | $0.30–$1.50   | Often underpriced relative to intent; small audience, $3k/mo can meaningfully saturate it.     |
| Trial-to-paid conversion, free-trial apps               | 15–35%        | Use your own funnel data the moment you have any.                                              |

At ~$34 target CAC, you're inside or below every one of these ranges except the top of Meta's paid-sub range — meaning the plan is fundable, but Apple Search Ads and Reddit are your safest starting points, not Meta or TikTok.

## 3. Tracking, before spend — not optional

$3k/mo has no room for guessed attribution. Before launch:

1. Wire trial-start and paid-conversion events with platform attribution (SKAdNetwork/AdAttributionKit for Apple, Meta AEM for Meta).
2. Skip a paid MMP (Adjust/AppsFlyer) for now — at this budget it eats a meaningful % of spend; native platform attribution is enough for one or two channels.
3. Every channel must report to the _same_ two numbers: cost, and paid conversions. If a channel can't give you that cleanly, don't fund it yet.

## 4. Weekly budget pacing dashboard — structure

Build one Sheet with these tabs:

**Tab "Targets"** (set once, referenced everywhere else)

- Monthly budget, price, margin, avg. lifetime, trial→paid rate → computed LTV, Target CAC, Target payback, Weekly budget target (`monthly ÷ 4.345`).

**Tab "Weekly Pacing"** (log every Monday for the prior week)

| Wk  | Week start | Weekly target | Cum. target | Actual spend | Cum. actual | Pacing % | New trials | New paid conv. | Weekly CAC | Trail-4wk spend | Trail-4wk conv. | Trail-4wk CAC | Target CAC | Status |
| --- | ---------- | ------------- | ----------- | ------------ | ----------- | -------- | ---------- | -------------- | ---------- | --------------- | --------------- | ------------- | ---------- | ------ |

- `Pacing % = Cum. actual / Cum. target` — your early-warning signal for over/under-spend.
- Judge CAC on the **trailing 4-week** column, not the weekly one — a single good or bad week is noise at this budget.
- `Status = IF(trailing CAC ≤ target, "on target", IF(≤ target×1.25, "watch", "over target"))`.

**Tab "Channel Breakdown"** — same weekly log split by channel (Apple Search Ads / Meta / TikTok / Reddit / Other), with CPI and CAC per channel. Sum of channel actual spend should reconcile to the Weekly Pacing tab each week — use it as a cross-check.

Cadence: every Monday morning, spend 10 minutes logging last week's actuals. That's the entire "dashboard maintenance" cost.

## 5. Guardrails / kill criteria

- Hard stop at 115% of weekly budget target — no exceptions without a deliberate decision.
- If trailing 4-week CAC exceeds Target CAC by 50%+, pause that channel and reallocate rather than "give it more time."
- Don't scale a channel until it's beaten Target CAC for 2 consecutive trailing-4-week readings — one good week is luck, two is signal.

## 6. Rollout for month 1, with a $3k budget

Two people, no ad experience, one month, $3k — concentrate, don't spread thin.

1. **Weeks 1–2 — Apple Search Ads only** (~$1,500). Highest-intent, cheapest to learn on, smallest blast radius if wrong. Bid on branded/long-tail journaling and habit-tracking keywords, exact match.
2. **Week 2 review** — compare trailing CAC to the $34 target. Adjust bids/keywords, don't add a channel yet.
3. **Weeks 3–4 — keep ASA running, add Reddit as a second test** (~$1,200 combined), leaning on the underpriced-CPC niche-community angle. Hold Meta and TikTok back until you have clean attribution proven on two simpler channels.
4. **End of month 1** — full review: actual blended CAC vs. $34 target vs. the industry ranges above. Decide whether month 2's fixed $3k goes deeper on the winner or adds Meta as a third test.

Don't touch TikTok until Apple Search Ads and Reddit have both proven the tracking pipeline works — TikTok's volume is only useful once you can trust the CAC number it reports.
