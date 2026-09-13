**None of my available skills fit this.** My skill set covers SEO/GEO audits, content writing, docs/decks/spreadsheets, and dev tooling — not paid-media CPA forensics. This isn't a "load 3 skills" problem, it's a causal-inference problem, and running all three fixes at once destroys your ability to solve it.

## The real issue

Launching creative + tracking + landing page in the same sprint means whatever happens next, you'll have **zero idea which fix worked** — or whether one fix masked another fix failing. Worse: if tracking is actually broken, your CPA numbers are lying to you right now, which means your media buyer and you are both arguing about a signal that might not be real.

## Diagnose in this order

**1. Rule tracking in/out first — before touching anything else** 🎯

- Cheapest to check, fastest to check, and it can fully explain a 2.4x CPA jump on its own (missing/duplicated purchase events → platform under- or over-counts conversions → reported CPA diverges from real CPA).
- Pull actual backend/CRM order count for the last 3 weeks and compare it line-by-line against what Meta/Google Ads reports as conversions for the same period.
- Match: tracking is clean, the CPA move is real → go to step 2.
- Mismatch: tracking is broken → fix it, then **re-baseline CPA for at least one full learning-phase cycle** before deciding creative or the landing page are actually the problem. Everything downstream depends on this being clean.

**2. Find the timing, not just the symptom** ⏳

- Plot weekly CPA against three dates: creative batch launch, tracking/pixel change from the rebuild, landing page redesign launch.
- Whichever change's date lines up with the inflection point is your prime suspect. If all three landed in the same week, you have a confound you can't resolve retroactively — which is exactly why they shouldn't launch together again.

**3. Test the remaining hypotheses one at a time, not simultaneously**

- Once tracking is confirmed accurate: A/B the landing page (old vs. new, split traffic) before doing a full rollback. A full rollback answers "was the LP the problem" with a yes/no you can't decompose from a blended metric.
- Creative fatigue is testable independently via frequency/CTR decay in the ad platform itself (rising frequency + falling CTR + flat CVR = fatigue; falling CVR on stable frequency/CTR points at the page, not the creative).

## Decision gate before this sprint

- 🔴 Don't ship all three changes in the same window again — you'll be back here in another three weeks with the same argument and less data than you have now.
- 🟢 Ship tracking fix alone first (it's not a real "fix," it's restoring ground truth — do it regardless of what else you decide).
- 🟠 Hold creative and landing page changes as separate, sequenced tests once you trust the numbers.

If you want, tell me what platform(s) (Meta/Google) and what's serving the pixel (GTM, server-side, native), and I can help write the specific verification query/steps for step 1.
