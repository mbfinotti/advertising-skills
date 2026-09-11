## Short answer

No — don't build the before/after comparison or the spend regression. Both are observational designs, and for retargeting specifically they're almost guaranteed to reproduce the same inflated number your CFO is already rejecting. She's right to be skeptical, and a regression won't fix that; it'll just dress the same bias in a trend line.

## Why those two methods won't survive a CFO's questions

**Before/after** can't separate "the ads worked" from "everything else that changed that quarter" — seasonality, other channels, organic growth, pricing changes, even normal PLG virality. Any finance person's first question will be "how do you know it wasn't [X]?" and you won't have an answer.

**Regression of weekly signups on weekly spend** has a worse, structural problem: retargeting spend isn't randomly assigned. You spend more in weeks when you have a bigger warm pool of people who already showed intent — i.e., people who were more likely to sign up *regardless* of the ad. The regression will show a positive coefficient on spend even if the ads changed nothing, because spend and "would-have-converted-anyway" move together. That's endogeneity, not causation, and it's exactly the failure mode retargeting is most exposed to: **it targets exactly the people most likely to convert on their own.**

This isn't a hunch — it's measured:

- Gordon, Zettelmeyer et al. (2019), across 15 large-scale RCTs at Facebook: observational methods (the kind both your proposals are) overstated experimentally-measured lift by roughly **7x to 9.5x**, depending on funnel position.
- Blake, Nosko and Tadelis (2015), eBay: brand-keyword ads mostly cannibalized traffic that would have arrived anyway — the same pattern you're describing.

## What your numbers are actually telling you

**14x platform ROAS + flat total new revenue is the textbook signature of cannibalization**: you're paying to intercept people who were converting anyway, and the platform is claiming credit for it. That combination — not either number alone — is the tell. If the campaigns were driving real incremental revenue, total new revenue should have moved even a little; it didn't.

Two things I'd check before even running a new test, because they can make the reported "640 signups" itself misleading, independent of incrementality:

1. **Audience overlap.** If your retargeting stages aren't mutually exclusive (a visitor sitting in "all site visitors," "feature viewers," and "trial abandoners" at once), the platform can report the *same* signup as a conversion in more than one ad set. That alone inflates the headline count without inventing a single real user.
2. **Converter suppression.** If existing signed-up users/teams aren't excluded from retargeting, some of those 640 could be re-engagement of people who already converted — not new revenue at all.

Both are five-minute audits, worth doing before you spend a quarter on a formal test.

## The actual proof: a randomized incrementality test

This is what will hold up in front of a CFO — because it's the same class of evidence the RCTs above used.

**Design (pick by what's available, in this order):**
1. **Platform ghost-ad / conversion-lift study**, if your ad account has access to one (Meta Conversion Lift, or equivalent) — check with your rep first; not all accounts qualify, and where it exists it's the cleanest, cheapest option.
2. If not available: **randomized audience holdout** — this is almost certainly your path, given a self-serve product with presumably no matched-market/geo infrastructure already in place.
3. Geo/matched-market holdout — only if you already run geo tests for other channels; otherwise it's a quarter of coordination overhead you don't need to take on.

**Recommended design, concretely:**
- **Holdout:** randomly withhold **15–20%** of every retargeting-eligible audience (across stages) from all retargeting ads for the test period. Everyone else gets ads as normal.
- **Duration:** run for a **full quarter**, matched to the same window your CFO is already comparing — that makes the result directly comparable to the "flat revenue" observation she's reacting to. If your signup cycle is short (days, typical for self-serve), a 6–8 week minimum would technically be enough statistically, but running the full quarter removes "wrong window" as an objection.
- **Metric:** new signups (and ideally activated/paying accounts, since signups alone repeats the same vanity-metric problem) in holdout vs. exposed group, tested for statistical significance (95% CI is the safer bar for a finance audience).
- **Pre-registered decision rule, agreed with the CFO *before* the test starts:** if the holdout group's signup rate is statistically indistinguishable from the exposed group's, retargeting spend is cut or folded back into prospecting — regardless of what the platform ROAS says. Getting her sign-off on this rule in advance is what converts the exercise from "marketing grading its own homework" into something she'll trust.

**Alongside the test, report a blended-efficiency metric every month:** total new revenue ÷ total marketing spend. This deliberately drops the whole attribution layer and is the number that already told you something was wrong — keep it visible so platform ROAS can never again tell a story the top-line contradicts.

## What to tell the CFO now

- The 14x/640-signup numbers are platform-attributed, not incremental, and the literature says that gap is typically 7–9x — which would turn a "14x ROAS" into something close to breakeven or worse, consistent with the flat revenue she's seeing.
- You're not defending the old numbers; you're proposing the test that either proves the campaigns work or gives her the basis to reallocate the budget.
- Expect the answer in **one quarter**, not this meeting — that's the cost of real evidence over a plausible-looking chart.