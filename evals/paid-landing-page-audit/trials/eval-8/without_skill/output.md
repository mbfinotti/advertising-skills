# On the 10.9% target

Don't adopt it as-is. Unbounce's benchmark blends lead-gen forms (one email field) with real purchase flows. A subscription meal kit checkout — plan selection, delivery day, payment — carries far more friction than the median "paid search" page in that dataset. You're not comparing like for like.

- 3.9% → 10.9% is a 180% relative lift. That's not a CRO roadmap, that's a different business.
- Benchmark medians say nothing about your traffic quality, price point, or category (meal kits face heavier comparison-shopping than most lead-gen verticals).
- Use the benchmark as a sanity check, not a commitment. Set target from your own baseline: e.g. 3.9% → 5.5–6% next quarter via a defined test roadmap, revisit after data comes in.

**Verdict:** kill the 10.9% team target. Replace with a phased, self-referential goal.

# On "Submit" → "Get my box"

Directionally right, magnitude wrong. "Submit" is dead microcopy — no value reinforcement, no clarity on what happens next. Fix it.

But it's a cheap, low-variance test. Expect low single-digit relative lift, not a path to 10.9%. Don't let it be the _only_ thing in flight — ship it alongside higher-leverage tests below, and don't credit it if a bundled test moves the number.

# On the speed sprint

Look closer before committing a month to this. Your own numbers contradict each other:

- Lighthouse 68/100 is a **lab** score — synthetic run, throttled network, penalizes things (unused JS, third-party tags, image format warnings) that don't necessarily touch real users.
- CrUX **field** data at p75 mobile: LCP 2.1s (green, <2.5s), INP 140ms (green, <200ms), CLS 0.04 (green, <0.1). All three Core Web Vitals are passing, on mobile, where 78% of your traffic already lives.

You're proposing a speed sprint to fix a problem your real users aren't experiencing. That's chasing a lab score, not user experience or conversion.

**Recommendation:** don't spend a month here. If you want a speed workstream, scope it narrowly to items with a plausible link to conversion (hero image weight, render-blocking JS on the button/CTA path) — not a blanket "get Lighthouse to 90" effort. Field data should override lab score whenever they conflict.

# On mobile sessions vs desktop revenue (78% / 70%)

This is a bigger flag than page speed and untouched by the team's current plan.

- Could mean genuine mobile checkout friction (small-screen plan/meal selection, payment entry).
- Could mean cross-device behavior: mobile research → desktop purchase. If so, session-based CPA on mobile is misleading — mobile isn't "failing," it's doing top-of-funnel work that last-click accounting doesn't credit.

**Before touching the mobile page**, pull cross-device/assisted-conversion paths (GA4 or equivalent). If it's cross-device, mobile CRO fixes won't move revenue much on their own — but the mobile page still needs to hold interest, not necessarily close the sale. If it's real friction, prioritize mobile-native payment (Apple/Google Pay), autofill, and cutting form steps.

# On CPA ($92 vs $40 target)

CPA scales roughly with 1/CVR at constant CPC. To hit $40 from $92 via conversion alone, you'd need CVR near 9% — which, incidentally, lands close to the "market benchmark" number, but for the wrong reason: it's arithmetic, not a target borrowed from Unbounce.

Don't rely on landing page work alone to close a $52 gap. Pair CRO with campaign-side efficiency: tighter keyword match types, negative keyword pass, Quality Score work. Splitting the gap (e.g., CVR to ~6%, CPC down 15%) is more realistic than asking the page to do it all.

# Copy audit

| Element                   | Verdict                       | Why                                                                                                                                                                                                                                                                                        |
| ------------------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Headline "Dinner, solved" | ⚠️ Risky for cold paid search | Emotionally fine, but doesn't confirm to a non-branded searcher they landed on the right thing. Pair with a subhead that echoes the ad/keyword ("Fresh meal kits delivered weekly") for message match and Quality Score.                                                                   |
| 3 benefit bullets         | ⚠️ Unverified                 | Structure is right. Content must hit real objections (time saved, cancel anytime, dietary flexibility) — not generic "fresh, healthy, easy."                                                                                                                                               |
| One box photo             | ❌ Weak                       | A sealed box doesn't sell food. Appetite appeal (plated meals, people eating) converts better than packaging shots for a food product. Add real food imagery, ideally above the fold.                                                                                                      |
| CTA "Submit"              | ❌ Fix now                    | Covered above — cheap, correct, low-impact-alone fix.                                                                                                                                                                                                                                      |
| FAQ accordion             | ⚠️ Misplaced                  | Fine as objection-handling depth, but if pricing/cancellation/commitment terms only live inside a collapsed accordion, you're hiding trust signals behind an extra click — costly on mobile.                                                                                               |
| No price before checkout  | 🔴 Primary suspect            | This is your highest-probability conversion killer, ahead of button text and page speed. Meal kits are a comparison-shopped category (HelloFresh, Blue Apron, etc.); a paid-search visitor who can't see a price will price-check a competitor instead of starting your multi-step signup. |

# Priority order

1. **Show a starting price above the fold** ("from $X/meal") — test this first, highest expected impact.
2. **Re-scope the target**: drop 10.9%, set a phased self-referential goal (e.g. 3.9% → 5.5–6%).
3. **Ship the CTA copy change** — cheap, low risk, but bundle with bigger tests, don't treat as the strategy.
4. **Pull cross-device data** before diagnosing mobile as broken.
5. **De-prioritize the speed sprint** — CrUX is already green on mobile; redirect that month to the pricing/copy tests above.
6. **Attack CPA on both sides** — CRO and campaign efficiency in parallel, not CRO alone.
