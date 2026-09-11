# No deal — here's why, and what to actually do with your $1,800

I ran your two openings through the hook-analyzer workflow (gates → bands → pairwise rank). Short version: **your plan has two problems that would waste real money**, and the honest answer to "which one will win, and what's its hook rate" is that no pre-launch method — mine included — can tell you either of those things reliably. Here's the full scorecard, then what I'd actually do.

## Problem 1: these aren't two candidates. They're one.

Both openings are the **exact same pour footage**, differing only in on-screen text. That fails this skill's real-variation gate outright: Meta's delivery system doesn't register wording-only changes as a different creative, and — separately from the platform — asking "which wins" implies a horse race between two visual concepts that doesn't exist here. You have one visual opening wearing two shirts.

## Problem 2: "predict the hook rate and bet the budget on it" is the specific failure this method exists to prevent

Hook rate is a home-brewed ratio (not a platform metric), and the best available agency data on it (Sweat Pants Agency, 3,859 ads across 11 brands) found hook rate correlates **-0.19 with ROAS** — slightly the wrong direction. High attention with no qualification is exactly how you get a scroll-stopping ad that loses money (the documented "43% hook rate, mediocre ROAS" case). So I won't hand you a number like "38% hook rate" — anyone who does is selling you false precision; two competent analysts scoring the same script by hand won't agree to the decimal, and the number wouldn't predict your sales anyway.

## Scorecard

```
HOOK BATCH SCORECARD — Marrowbone Broth Co., Meta feed, cold B2C, 2026-09-12
batch        : 2 candidates (same footage) | input: cut description
hook window  : first ~3s | audience: cold B2C
dashboard    : hook rate assumed = 3-second video plays / impressions (Meta default — confirm in Ads Manager)

gates
  1 "Value/price"  : sound-off pass | promise-payoff pass* | qualification adequate | variation FAIL — merged with 2 (identical footage)
  2 "Craving"      : sound-off pass | promise-payoff adequate* | qualification adequate | variation FAIL — merged with 1

  * assumes the rest of the ad actually delivers taste + price proof (tasting reaction, ingredient
    shot, price/serving math). I don't have that footage description — confirm before you ship.

bands (one merged cell, two text treatments — not two ranked candidates)
  1 "Bone broth that actually tastes good. $3 a serving."
    time-to-signal strong | sound-off strong | qualification adequate-strong (price pre-filters
    for budget-conscious buyers) | specificity strong (checkable price + a named objection —
    "actually tastes good" answers the #1 reason people avoid bone broth) | brand timing adequate
    (pour shot isn't a distinctive brand asset yet) | continuity strong* | placement fit strong

  2 "Finally, bone broth you'll crave."
    time-to-signal adequate (emotional payoff needs a beat to land) | sound-off strong |
    qualification weak-adequate (universal aspirational language, doesn't self-select) |
    specificity weak (category wallpaper — any beverage/snack brand could run this line
    unchanged) | brand timing adequate | continuity adequate* (implies a past letdown the ad
    must pay off — plausible but vaguer promise) | placement fit strong

ranking : not applicable as a performance prediction — this is one test cell, not a batch to rank.
          If forced to pick which text carries the cell: Text 1 over Text 2, on specificity and
          qualification — it makes a checkable claim (price) and resolves the actual objection
          buyers have to bone broth, where Text 2 is generic craving language any beverage
          brand could run. That's a judgment call within one visual, not a hook-rate forecast.

shipping check : 1 real test cell, far below the 3-opening floor this skill treats as a minimum
                 batch. You are not testing creative variety — you're testing one opening.
calibration    : n/a — nothing to compare rank order against with a single cell.
```

## What I'd actually do with $1,800

1. **Don't run both as separate ads.** Splitting an already-tiny budget across two ad IDs that Meta sees as near-duplicates just fragments your learning phase for zero signal — you'd be paying twice to learn once, on a budget too small to even exit learning phase cleanly on one ad.
2. **Run Text 1** ("actually tastes good. $3 a serving") as your primary text, and **add Text 2 as a second primary-text option on the same ad** (Meta's multi-text-option field, not a second ad). You still get comparative delivery data on both lines in Ads Manager, at no extra learning-phase cost. That's the free version of a real test.
3. **If you have any other frame from that shoot** — steam, a bowl, ingredients, a sip reaction — recutting the opening on that shot instead of the same pour would give you a genuinely different visual for free (an hour of editing, not a reshoot) and produce a real second test cell for the next $1,800, not this one.
4. **Don't ask me for a hook-rate number before launch.** Ask me to compare this cell's *measured* hook rate against your account's own future batches once you have a dashboard definition locked (`3-second plays ÷ impressions` is Meta's standard construction — confirm that's what you're reading). That comparison is the thing this method can actually do.

Sizing the $1,800 itself (budget per day, learning-phase math, how long to let it run before judging) is outside what I do here — that's `ad-creative-test-plan`, worth a quick pass before you hit publish.