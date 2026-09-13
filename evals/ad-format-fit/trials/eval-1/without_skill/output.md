Three of your four setup choices fight each other. Here's where it breaks.

## The core problem: budget × CPA can't feed the algorithm

Meta's (assuming Meta — same logic applies to Google Ads Smart Bidding) conversion optimization needs roughly **50 conversions of the optimization event per week** to exit learning phase and deliver a stable CPA. Below that, it stays "learning limited" indefinitely: CPA swings wildly, delivery is erratic, and the algorithm never gets enough signal to find the right people.

Your numbers: $25/day ÷ $80 target CPA = **~2 conversions/week, best case**. That's not a slow ramp to 50/week — it's a permanent ceiling roughly 25x below what the algorithm needs. This campaign will likely never leave learning phase. Expect CPA to be unstable for as long as it runs, not just the first week or two.

## Second problem: you're optimizing for an event you almost have no data on

2-3 demo requests/week _across all channels_ means your pixel has seen maybe 100-150 of these events total, ever, if you've been running a while — likely far fewer. Meta needs volume to model who converts. You're asking it to learn a rare event from a rare event.

This also poisons your lookalike: a "demo requesters" LAL built from a tiny, low-volume seed is noisy and won't resemble your real buyer profile well.

## Third problem: format mismatch for cold traffic

A 5-card feature-tour carousel is a consideration asset — it assumes the viewer already knows they have the problem you solve and is evaluating solutions. Cold lookalikes don't know Fienzo exists yet. For cold + bottom-funnel CTA (demo request), a single strong hook (the problem, the outcome, one proof point) usually outperforms a feature walkthrough. Save the carousel for retargeting people who already engaged.

## What I'd actually change before building

1. **Don't optimize for demo request yet.** Optimize for a higher-funnel event you have real volume on (landing page views, or a lighter "lead"/micro-conversion like a content download or pricing page view). Build pixel data and an engaged-visitor custom audience for 2-4 weeks first.
2. **Seed the lookalike from something bigger than demo requests** — your full site-visitor pixel audience, email list, or a broader "engaged" custom audience. Layer in demo-request LAL later once volume exists.
3. **Raise the budget or lower the ambition, don't do both at once.** Either bump budget toward ~$50-70/day so $80 CPA yields closer to 6-9 conversions/week, or accept you're running a data-collection phase, not a CPA-optimized campaign, and set expectations accordingly.
4. **Swap the carousel for a single strong creative** for this cold/bottom-funnel campaign. Keep the carousel in reserve for a retargeting campaign once you have a pool of engaged visitors.
5. **One ad set, one audience, don't fragment the budget.** At this spend level, testing multiple LALs or interest stacks in parallel splits an already-thin data pool further.
6. **Sanity-check the $80 CPA against actual unit economics** (demo→close rate × deal value) before locking it as the bid — if you don't have that math yet, this is a good moment to build it.

Bottom line: as configured, this campaign is structurally set up to sit in perpetual learning limbo rather than to actually find and prove out a CPA. Fix the funnel stage you're optimizing for and the audience seed before you turn it on — the budget and creative can stay roughly as-is once those two are right.
