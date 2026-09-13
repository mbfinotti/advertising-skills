## Solvenne — Google Ads test: verdict + bid strategy

### 1. The $150/demo threshold is roughly right, but incomplete

Backward math from your real target (outbound CAC $700):

```
CAC_paid = cost-per-demo ÷ demo-to-close rate
$150 ÷ x = $700  →  x ≈ 21%
```

So $150/demo only matches outbound CAC **if paid demos close at ~21%+**. You don't know that number yet — and you won't, for 6 weeks, because that's your sales cycle. Outbound leads are pre-qualified (research, personalization); cold search clicks self-select on an ad and a landing page. Their close rate could easily be lower.

**Implication:** cost-per-demo is a good _leading_ gate (fast, cheap signal). It is not a substitute for CAC. Don't let a good cost-per-demo alone trigger $10K/month — that's committing $10K/month before you know if the channel produces customers, not just meetings.

### 2. The $500 / 10-day test won't produce a trustworthy number

- $500 over 10 days = $50/day.
- Legal-tech / B2B accounting keywords are expensive — realistic CPC range $15–40+.
- At $50/day that's roughly 1–3 clicks/day, ~10–30 clicks total, likely **0–3 demo bookings** over the whole test.
- With 1 vs 3 demos, cost-per-demo swings from $500 to $167 — the pass/fail decision is basically noise, not signal.

**Fix — same budget, better decision rule:**

1. Run the $500/10 days as planned — treat it as a **feasibility check**, not the scale gate: does the channel generate any qualified demo interest at all, what CPC/terms actually convert.
2. Don't gate on calendar days. Gate on **volume**: if you get fewer than ~5 demos in 10 days, extend the test (more days or more budget) before deciding anything — you don't have enough data yet either way.
3. If ≥5 demos land under $150 each → move to **Phase 2**, not straight to $10K/month: spend $2–3K/month for another 4–6 weeks to build a cohort of 20–30 demos.
4. Let that cohort run through the 6-week sales cycle. Only scale to $10K/month once **actual CAC** (ad spend ÷ closed customers from that cohort) is at or below $700.

This costs you a few extra weeks but avoids committing $10K/month on a metric (cost-per-demo) that hasn't been validated against revenue.

### 3. Bid strategy

**For the test (now, near-zero conversion history):**

- **Manual CPC**, or **Maximize Clicks with a manual max-CPC cap** — not Smart Bidding.
- Reason: Target CPA / Maximize Conversions need ~15–30 conversions per campaign in a rolling window to exit "learning" mode. At 1–3 demos over 10 days, Smart Bidding never learns — it either underspends or bids erratically.
- Search Network only. No Display expansion, no Performance Max (both are black-box and unsuitable for a tiny, unproven budget).
- Track **"demo booked"** (booking-tool completion, e.g. Calendly/HubSpot) as the _only_ primary conversion action — not clicks, not form starts.

**Once you scale (Phase 2/3, $2K+/month):**

- Switch to **Maximize Conversions** (no target) for 2–3 weeks to accumulate ~30 conversions.
- Then layer in **Target CPA**, set at $700 (your outbound benchmark) as a ceiling, and tighten once you know the real CAC from closed-won data.

**Campaign hygiene (applies from day 1):**

- Tightly themed ad groups, exact/phrase match, bottom-of-funnel terms only ("law firm accounting software," "legal accounting automation," relevant practice-management integrations).
- Negative keyword list from the start: free, jobs, students, DIY, template, other vendor names (unless deliberately conquesting).
- Landing page = direct demo-booking page, not the homepage — conversion rate matters enormously when your total click volume is this small.
