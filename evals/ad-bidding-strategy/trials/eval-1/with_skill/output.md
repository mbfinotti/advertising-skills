## Short answer

**The agency is wrong about the mechanism, right to be cautious about volume, and wrong to freeze you on manual CPC while you wait.**

## Fact-check on "15 to unlock, 50 to work properly"

| Claim                                                     | Status                                                                                                                                                                                                                                                             | Source tier            |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------- |
| "15 conversions in 30 days is required to use Target CPA" | ❌ False for Target CPA. Google Ads Help states Target CPA "can start with no conversion history" and is "effective for campaigns of all sizes."                                                                                                                   | documented             |
| "15 conversions in 30 days" figure exists                 | ✅ True, but it's the **Target ROAS** (return-goal) minimum for Search/Shopping campaigns — a different strategy than the one you'd actually want first                                                                                                            | documented             |
| "50 conversions before it works properly"                 | ⚠️ Real number, wrong context — it's Meta's ~50-events-per-ad-set-per-week learning-phase guidance (and similar figures for Demand Gen/App/Video campaigns), not a Search Target CPA rule. Even where it applies, it's a _reliability recommendation_, not a gate. | documented, misapplied |

This is a textbook conflation of two different kinds of number: an **enablement gate** (am I allowed to turn this on) versus an **evaluation sample** (how confidently can I read the result once it's on). The agency merged them. Folklore travels this way because the two archetypes share a UI tab in some accounts and the "15" number is memorable.

⚠️ These thresholds drift roughly yearly (Google has renamed and re-merged Target CPA/ROAS into "Maximize + optional target" and back within the last two years) — worth a 30-second check against the live Google Ads Help page before you act on this, since I answered from documented-but-dated reference material rather than a live fetch this session.

## Why it matters here specifically

You don't have deal values flowing back to Google (nothing in what you've described suggests it), so **Target ROAS isn't the right next step regardless of volume** — it would optimize on a value signal you haven't fed it. The archetype that actually matches your stated goal (get demos at a cost you can afford) is **Target CPA — cost-goal, not return-goal** — and that one has no documented minimum at all. So even citing the correct number, it's pointed at the wrong strategy for your situation.

## What your volume actually costs you

9 conversions/month ≈ 2/week is genuinely thin. That doesn't block eligibility, but it does cost you something real: **variance and slow diagnosis**. At this rate, a bad week and a bad target look identical for a while, and a target change needs roughly a month just to read cleanly. That's a legitimate reason for caution — just not a reason to sit on manual bidding.

## Recommended interim policy

```
BIDDING POLICY  -  Google Search / B2B compliance software, demo-request lead gen
Objective        : cost efficiency (hold cost per demo request near current level)
Archetype        : cost-goal (Target CPA), NOT return-goal.
                   Why: no deal-value pass-back exists yet, so a return target would
                   optimize on noise. Runner-up (stay manual) rejected: manual buys
                   per-auction control you haven't asked for and no documented
                   eligibility barrier justifies the wait.
Evidence         : event = demo request. Depth check: UNCONFIRMED - confirm with
                   sales that demo requests convert to real pipeline at a stable
                   rate before trusting the platform's read of "good" vs "bad" weeks.
                   Volume: 9/month (~2/week). Lag: unknown - get an average
                   click-to-demo interval before setting the evaluation window.
Target           : $370 (= trailing actual). Held flat, not tightened, at launch.
                   Economics: UNCONFIRMED - need average deal size (or contribution
                   per closed deal) and demo-to-close rate to compute break-even CPA
                   and a real margin buffer. Until then this target is a starting
                   point, not a validated ceiling.
Evaluation       : 2 conversion cycles. Cannot convert to a day count without the
                   lag figure above - get it before setting a calendar date to review.
Change rules     : no target changes in the first evaluation window. After that,
                   ±10% max per step (practitioner-convergent, not a platform rule),
                   one window between steps. Approver: whoever owns the agency
                   relationship on your side.
Rollback trigger : spend falls meaningfully under $120/day with demo volume dropping
                   and impression share lost to rank rising -> target was set too low;
                   raise back toward $370 or above.
Switch triggers  : CRM deal values start flowing to Google AND you clear the
                   documented Target ROAS minimum for Search (15 conversions in 30
                   days, re-verify live) -> revisit return-goal then, not before.
```

## What to actually do this week

1. **Turn on Target CPA now, set at $370** (your trailing actual, not an aspirational number). Moving to an aggressive target would choke delivery; moving to today's actual just removes the manual guesswork while changing nothing about your economics.
2. **Don't touch the target again for one full evaluation window.** With unknown lag, ballpark 3-4 weeks before judging it.
3. **Get two numbers before the next review**: average deal size (or contribution margin per closed deal) and demo-to-close rate. Without them nobody — not you, not the agency — can say whether $370 is even affordable, let alone what to tighten toward.
4. **Sanity-check the demo-request event with sales** in parallel: are these demos turning into real pipeline, or is volume being bought with unqualified sign-ups? That's the one gate that actually matters here, and it's not one the agency mentioned.
5. **Hold off on Target ROAS entirely** until deal values are piped back to Google — that's the real 15-conversions-in-30-days rule, applied to the strategy it actually governs.
6. Push back on the agency specifically on the mechanism, not just the outcome: ask them to point to the Google Ads Help page for Target CPA (not Target ROAS) if they still think a conversion minimum blocks you. If they can't, that's your answer.

## What's still open

I don't have your deal economics (contract value, demo-to-close rate) or the click-to-demo lag, so the target above is deliberately held at trailing actual rather than computed against a break-even ceiling — treat it as provisional until those two numbers exist. Also unconfirmed: whether $120/day is currently capping delivery (budget-limited status) — that's a separate lever from the bid strategy and worth checking before you conclude the strategy change alone will move volume.
