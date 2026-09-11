## Recommendation: don't swap tomorrow. Keep the current seed running, and fix the measurement problem before deciding anything.

**Direct answer to "which seed do we keep": neither, yet.** You don't have the data to make that call, and CPA alone already burned you once — swapping on CPA again repeats the exact mistake, just in the other direction.

### Why match rate doesn't back your "seed is solid" claim

72% match rate tells you Meta matched 72% of your uploaded customer records to real profiles. It's a data-hygiene metric (clean emails/phones), not a quality signal. It says nothing about whether those matched customers are *good* customers to look alike. Don't let it anchor your read of what's wrong.

### Why 5 days of CPA is not evidence

⚠️ A fresh lookalike audience is still in (or just exiting) Meta's learning phase. CPA is typically elevated and noisy until an ad set accumulates enough optimization events (rule of thumb: ~50/week) for the algorithm to stabilize. Five days on a brand-new audience is squarely inside that noise window. A 40%-over-target CPA at day 5 is not yet a verdict.

### The confound you must control for: this is the same trap as last time

Your old seed had "amazing CPA" and turned out to attract one-time, discount-driven buyers — cheap to acquire, bad LTV. If the new seed's CPA is *higher*, that is equally consistent with two opposite explanations:

- 🔴 the new seed is genuinely worse (less predictive audience), or
- 🟢 the new seed is finding less discount-motivated, higher-LTV customers who cost more to acquire but are worth more.

You cannot distinguish these without LTV data. Acting on CPA alone means you're optimizing for the same failure mode that finance already caught you in.

**Check now:** is the 40%-off welcome code still live? If yes, it contaminates any comparison between seeds — new-seed conversions using it will look artificially cheap/easy and will replicate the old problem regardless of seed quality.

### What to do this week

1. **Don't revert the seed tomorrow.** Let it keep running through learning phase.
2. **Instrument cohort LTV now**, retroactively and going forward: 30/60/90-day repeat purchase rate, AOV excluding first order, % of orders using the welcome code — split by acquisition campaign/seed. You don't need full LTV maturity to get a usable early read; 30-day repeat rate is a decent leading proxy.
3. **Set a guardrail, not a trigger**: cap CPA at ~1.5–2x target as a hard stop for budget bleed, but don't treat "40% over" alone as a swap signal.

### Next week's head-to-head test — keep it, but change the win condition

Your plan (two ad sets, old seed vs. new seed) is the right instinct. Fix the metric it's judged on:

- Primary metric: 30-day repeat purchase rate and AOV ex-welcome-code, not CPA.
- Run long enough to clear learning phase on both ad sets (minimum ~2 weeks, ideally until each has 50+ conversions).
- Tag and exclude/segment welcome-code redemptions in the readout for both arms.
- CPA stays a secondary/guardrail metric, not the decision metric — that's literally the lesson from the old seed.

**Bottom line:** the real fix isn't picking a seed, it's that you're one CPA metric away from repeating the same misdiagnosis that already cost you once. Build the LTV read this week; let the audience run; decide with next week's test using repeat-purchase behavior as the tiebreaker, not day-5 CPA.