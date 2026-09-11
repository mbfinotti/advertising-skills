# MMM: don't green-light it — not yet

The skill's own readiness bar for MMM: **2+ years of clean weekly data (3 for national-scope models) plus a dedicated analyst.** Nordvale has ~9 months of order history and no in-house analyst. Both prerequisites fail — this isn't a borderline call.

Why that bar matters here, not just as a rule to cite:

- **9 months doesn't even span a full seasonal cycle.** Outdoor apparel has hard seasonality (fall/winter gear, holiday). An MMM fit on under a year of data will extrapolate response curves for seasons it has never observed — exactly where these models are least reliable.
- **MMM is observational.** Even with enough data, its coefficients need validation against a holdout or geo test before you trust them — "a model with priors you set can be pointed at the conclusion you wanted." Without that validation step (which your agency's $65K pitch doesn't appear to include), you're buying a confident-looking number, not evidence.
- **No dedicated analyst means no maintenance.** MMM isn't a one-time deliverable — coefficients drift and need re-fitting. A model nobody owns goes stale and gets trusted anyway, which is worse than not having one.
- On the skill's own effort/value/efficiency ranking, MMM is highest effort, highest value, **and lowest efficiency** of the four ways to estimate marginal return. It's the right tool eventually — not the right first purchase for a 9-month-old data warehouse with no analyst.

**Verdict: pass on the $65K engagement as scoped.** Don't spend it on a model your data can't support and nobody can maintain.

## What actually answers "is Meta working" — cheaper and faster

You said confidence in Meta's true contribution is low. Meta is also 61% of your $95K budget ($58K). That combination — biggest line, lowest confidence — is exactly the case where the skill says to promote incrementality testing above its normal rank, because a misread here costs real money.

**Recommend instead: a geo-lift holdout test on Meta**, this quarter:

- **Hypothesis:** Meta's incremental contribution to orders is materially below its platform-reported ROAS (the pattern is well-documented — platform ROAS overstates true return 1.75–2.97x on average, and this is the standard failure mode for saturated prospecting/retargeting mixes).
- **Design:** 10–15+ matched geographies, ~10–20% held out from Meta spend, 4–6 week read (safe default for a considered-purchase apparel buy; shorten only if your typical purchase cycle is genuinely days, not weeks).
- **MDE:** set before you run it — ask the agency (or whoever designs it) what lift is detectable at this spend and geography count; don't run it without one.
- **Decision date:** end of week 6.
- **Stop condition:** if the holdout shows no significant revenue gap, cut Meta's marginal allocation at the next resplit rather than defending its average ROAS.
- **Cost:** design + read effort, not incremental media spend — this uses budget you're already spending, just held out geographically. Materially cheaper than $65K. If you want outside help, get a quote for *this* specifically, not a full MMM.

This is the one test that directly answers your actual question ("is Meta's contribution real") — an MMM would answer it too, eventually, but only after buying 15+ more months of data and an analyst you don't have.

## Meanwhile: what to do with the $95K split, this cycle

**Gates first — two are unresolved, name them rather than guess:**

| Gate | Status |
|---|---|
| Data-basis | **Fails as-is.** None of the three lines' platform-reported ROAS is a safe input. This is the whole reason confidence in Meta is low — you're likely seeing average, platform-attributed numbers. |
| Measurement-maturity | **Unknown — needed before any move.** Score 1–3 each on blended dashboard, per-channel dashboard, conversion tracking, web analytics, attribution process. If it's under ~6/15, fix tracking before reallocating anything. |
| Funding floor | **Check Pinterest.** $10K/month ≈ $333/day. Floor ≈ target CPA × 50 ÷ 7. If your target CPA is above roughly $47, Pinterest is already under its learning floor and can't be optimized meaningfully at this spend — that's a "cheaper channel or kill it," never "thin the spread" further, question. Run this with your real target CPA. |
| Payback/affordability | **Unknown — need CAC, contribution margin, retention.** Can't confirm any line clears ~12-month payback without these. |

**Decision for this cycle: hold the current split ($58K / $27K / $10K), don't reallocate on the numbers you have.** Platform ROAS is exactly the input this skill bans as a reallocation basis, and it's the only number you currently trust or distrust Meta by. Moving money now would be reallocating on the same noise that's causing the low confidence in the first place — and flat spend under uncertainty has consistently beaten reactive moves.

**But don't sit idle — pull three cheap numbers this week (near-zero effort, this is the "directional proxies" rung, not a proxy for the real answer):**

1. **Meta — penetration band.** 30-day reach ÷ addressable audience size (Ads Manager → Audience Insights). Under 25% = headroom to hold or raise; 25–35% = hold; 35%+ = scale horizontally into new audiences, not more budget into the same ones.
2. **Google non-brand — impression-share headroom.** Pull "Lost IS (budget)" from Auction Insights. High lost-IS = budget-responsive, room to raise; near 0% at 60–80%+ share = additional budget won't move it.
3. **Pinterest — same penetration-band read as Meta**, paid social treatment.

These are directional only — they tell you headroom, never magnitude, and they don't resolve the Meta confidence question. Label them as proxies if you act on them at all, and cap any move at 15–20% of a line, never more.

**What I'm explicitly not doing:** producing a reallocated dollar split right now. I don't have your margin, CAC, measurement-maturity score, or actual penetration/impression-share figures, and inventing proportional weights from missing data is the one thing this exercise is built to prevent. Pull the three numbers above, or share margin/CAC/measurement-maturity, and I'll turn this into a real change packet (current → proposed, per line, with rollback thresholds).

## Cadence and governance

- **Now → week 6:** hold the split, run the Meta geo-lift test, pull the three directional proxies in parallel.
- **Week 6:** real quarterly resplit, using the geo-lift result for Meta (measured, not proxy) and the directional-proxy reads for Google/Pinterest.
- **Governance:** any move above ~10% of a channel's monthly budget goes through a standard approval; above ~25% needs marketing + finance sign-off with rationale and review date logged.
- **Annual:** revisit with a full zero-based review once you have a real analyst and 12+ months of clean data — that's also the point where MMM becomes a legitimate ask, not before.

## What's ruled out, and why

- **MMM, this cycle:** deleted — data history and analyst headcount both miss the bar. Revisit once you're at 12+ months of clean weekly data and have hired for the analyst seat; even then, budget a validating geo test alongside it, don't skip that step.
- **Full marginal-evidence rebuild of the whole $95K:** not warranted yet — Google and Pinterest aren't "inherited and untrusted," only Meta is, and Meta gets the targeted test rather than a portfolio-wide teardown. Save the full rebuild for the annual zero-based review.

## Open questions I need from you

- Contribution margin and CAC (sets the payback gate and whether "aim for Nx ROAS" folklore applies at all).
- Measurement-maturity self-score (1–3 across blended dashboard / per-channel dashboard / conversion tracking / web analytics / attribution process).
- Target CPA (to actually check Pinterest against its funding floor).
- Who approves budget moves, and how much of the $95K they'd accept seeing move in one cycle.
- Any committed seasonal flights in the next 6 weeks that the Meta test window needs to avoid or account for.