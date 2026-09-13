# Solvenne — Google Ads channel + bidding plan

Ran this through `ad-platform-selection` (channel/test design) and `ad-bidding-strategy` (bid policy) — the platform-selection skill explicitly hands off bidding to the second one, so both apply here.

**Bottom line up front:** ✅ Google Ads is the right channel. ⚠️ Your $500/10-day test is undersized for the decision you're hanging on it, and the $150 cost-per-demo gate isn't actually calibrated to your $700 CAC target — it's missing one number.

---

## 1. Economics

| Input                         | Value                                                                    |
| ----------------------------- | ------------------------------------------------------------------------ |
| ACV                           | $9,600 (assumed ~$800/mo recognized, not paid upfront — see check below) |
| Gross margin                  | 75%                                                                      |
| Monthly gross profit/customer | $9,600 ÷ 12 × 0.75 = **$600**                                            |
| Outbound CAC / payback        | $700 / ~6 weeks                                                          |
| Target for paid               | Match outbound: **$700 CAC**                                             |

**Cross-check:** $700 CAC ÷ $600 monthly GP = 1.17 months ≈ **5.1 weeks** payback. You said "about 6 weeks" — close enough that it confirms the $800/mo-recognized assumption rather than an upfront-annual model. If Solvenne actually bills annually upfront, say so — the math changes a lot (payback would be near-instant).

**Derived ceiling:** at a 6-week payback target, allowable CAC = 1.38 months × $600 = **$829**. Your $700 target sits $129 (18%) below that — a real margin buffer, not a razor's edge. Good.

**Affordability gate on paid search:** ✅ clears easily. Legal-vertical search CPC averages ~$9.87 (range $1.50–$50+, unverified-current, reverify live). Against a $700+ allowable CAC there's enormous headroom — paid search was never going to fail step 1 here.

## 2. The gap in your test design: cost-per-demo isn't CAC

Your pass rule — "CPD < $150 → scale to $10K/mo" — silently assumes a demo→customer close rate. Solve for it:

**$150 CPD ÷ $700 target CAC = 21.4% demo-to-close rate required for the gate to mean what you think it means.**

- If your real close rate is above ~21%, $150/demo is a genuinely good number.
- If it's 10% (not unusual for a new-motion B2B demo funnel), $150 CPD actually implies a **$1,500 CAC** — more than double your target, while your dashboard shows a "pass."
- If it's 30%, CAC is $500 — you could afford to pay *more* than $150/demo and are underbidding.

⚠️ **Before you trust the $150 threshold, pull your actual demo→close rate** — from the outbound motion if the sales process is comparable, or from any existing inbound demos. Until then, treat "CPD < $150" as a provisional proxy, not a validated CAC gate.

## 3. Your $500/10-day plan is underfloor

$500 ÷ 10 days = **$50/day**.

The skill's signal floor for paid search: daily budget should run 3–5x target CPA to plausibly clear ≥1 conversion/day and ~10 clicks/day. At a $150 target CPD, that's **$450–750/day** — you're proposing roughly 7–11% of that.

At $9.87 avg CPC that's ~5 clicks/day; even at a cheap niche CPC of ~$3–5 it's 10–17 clicks/day, and B2B cold-search landing pages typically convert 2–5% to a demo request. Realistic outcome: **1–5 total demos over the full 10 days.** That's not a 90–95%-confidence read on CPD — it's price discovery with a "real test" label on it.

**Recommended fix — split it into two stages instead of one:**

| Stage              | Budget                                       | Window                                          | Goal                                                                                                                 |
| ------------------ | -------------------------------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| 1. Price discovery | Your $500 stands                             | Mon Sept 14 – Wed Sept 23 (as planned)          | Learn real CPC/CTR/landing-page conversion for this niche. Directional CPD only.                                     |
| 2. Real test       | $450–750 (3–5x $150 target) at $150–250/day  | ~2–4 weeks after Stage 1 (through mid-late Oct) | A CPD number you can actually act on.                                                                                |
| 3. Scale decision  | Step to $3–5K/mo first, not straight to $10K | After Stage 2, before full $10K commit          | Confirm CPD holds _and_ first Stage-2 demos are progressing to opportunities in CRM before betting the full $10K/mo. |

Full CAC parity (the $700 number) can't be confirmed until closed-won data exists — that needs the full ~6-week cycle from Stage 2's first demos, independent of the CPD read. Treat "$700 CAC confirmed" as a mid-November milestone, not a day-10 one.

If you'd rather keep $500/10 days exactly as a hard constraint, that's a legitimate call — just don't let it single-handedly authorize a 20x jump to $10K/mo. Use it to rule out a badly mispriced account (e.g., $40+ CPCs) and nothing stronger.

## 4. Bid strategy

Phased — matches your actual conversion volume at each stage rather than setting a target you can't yet defend.

```
BIDDING POLICY — Google Ads / Search — Solvenne demo-gen
Objective   : Stage 1 traffic/price-discovery → Stage 2 volume → Stage 3 cost efficiency
Archetype   : Stage 1: Manual CPC / Maximize Clicks (manual/exploratory)
              Stage 2: Maximize Conversions, uncapped (volume-maximizing)
              Stage 3: Target CPA (cost-goal) — only once Stage 2 produces a trailing actual
Evidence    : conversion event = "demo booked" (proxy, not the real outcome — sales cycle
              is too long to optimize on closed-won yet); event depth: reasonable, demo
              requests are typically pre-qualified, not raw newsletter fills
Target      : Stage 3 initial tCPA = at/slightly above Stage 2's trailing actual CPD
              (never set at the aspirational $150 — that's the documented #1 cause of
              delivery collapse). Tighten ~10-15% per evaluation window toward $150,
              or toward the close-rate-adjusted true number once you have it.
Evaluation  : 1-2 conversion cycles per step. Lag here is short (click→form same day,
              maybe a few days lag) — but don't judge the whole flight before Stage 2's
              full 2-4 week window closes.
Change rules: no target changes mid-flight; one switch (volume-max → cost-goal) at the
              end of Stage 2, not before.
Rollback    : 2-3x target CPD spent ($300-450) with zero demos after a readable sample
              → pause, diagnose landing page/keywords/offer before rerunning.
Switch trig.: Target ROAS (return-goal) only once deal values flow back to Google Ads
              AND you clear Google's documented Search minimum of 15 conversions/30 days
              — not close at current volume. Revisit once CRM close data is piped back.
```

**Why not jump straight to Target CPA:** Google documents no conversion-volume minimum for it, so it's _technically_ eligible even at zero history — but with an expected 1–5 conversions over your Stage 1 window, a tight cost target has nothing to learn from and risks choking delivery (spend far under budget while looking "efficient"). Maximize Conversions accumulates the trailing actual Target CPA needs; that's the whole point of Stage 2.

**Why not Target ROAS:** no deal values are flowing back to the platform yet, and you're nowhere near the documented 15-conversions/30-days minimum for Search. Revisit once CRM close data is piped back — that's also the moment value-based bidding becomes possible.

No special-ad-category exposure here (not credit/employment/housing/health) — no targeting stripped, no extra compliance review needed for search text ads.

## 5. Measurement

Capture-heavy plan at a small budget → default rung is fine: **UTM discipline + last-non-direct**, plus a source field on the demo-request form tied to your CRM. Add self-reported attribution ("how did you hear about us") the moment you add any second (creation-type) channel — not needed yet for search alone.

Critically: tag every demo's source in the CRM now, so when closed-won data lands in ~6 weeks you can join it back to Stage 2's demos and get the real CAC, not just CPD. This is what fixes the gap in section 2.

## 6. Second channel — not yet

Per the concentration rule, don't add a second channel until paid search saturates or budget crosses ~$50K/mo — you're not there at $10K/mo. When you do, B2B professional networks (LinkedIn) is next in the default B2B order; it needs ~$5K/mo minimum and an LTV of $10–15K+ to clear its own gate — Solvenne's $9,600 ACV is close to that floor, closer once renewals are counted, so it's plausible later but not a day-one candidate.
