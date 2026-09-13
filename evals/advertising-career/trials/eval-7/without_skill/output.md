Here are full answers for all three, structured the way a strong candidate would actually talk through them in a scenario round — framework first, then specifics, then a closing insight that shows judgment (which is what these questions are really testing).

---

## Q1: "Account ROAS dropped 30% over the last three weeks — walk us through your diagnosis."

**Opening frame (say this first, out loud):** "Before I dig in, I'd want to know: is this blended ROAS or platform-reported ROAS, and is revenue down too, or did spend go up while revenue held flat? Those are different problems." This signals you think in MER/contribution margin, not just platform ROAS — important for a DTC supplements brand where subscriptions and LTV matter more than day-1 ROAS.

**Then walk the diagnosis top-down, ruling out layers in order:**

**1. Tracking/measurement first (cheapest to check, most commonly the actual answer)**

- Any recent pixel, CAPI, or GA4 changes? iOS/Android privacy updates, browser cookie changes, a site replatform, or a tag manager update can silently break attribution without touching real sales.
- Compare Shopify/backend revenue to platform-reported revenue over the same window — if backend revenue is flat but platform-attributed revenue dropped, it's a measurement problem, not a performance problem.

**2. External/demand-side factors**

- Seasonality: is this a known trough (e.g., post-New-Year drop-off in supplements, back-to-school lull)?
- Competitive pressure: did a competitor launch a big promo or increase spend, driving up auction CPMs?
- Macro: any change in iOS/Meta policy, platform algorithm updates, or broad CPM inflation across the account (check Meta's auction overlap/CPM benchmarks)?

**3. Supply-side / account structure**

- Creative fatigue: pull frequency and CTR trend by ad — for DTC supplements, creative fatigue is often the #1 cause of a slow 3-week bleed, since audiences are relatively small and frequency climbs fast. I'd check frequency >3-4 as a red flag.
- Audience saturation: has the campaign exhausted lookalikes/interest stacks, forcing the algorithm into more expensive, lower-intent inventory?
- Budget/bid changes: did anyone increase budgets, change bid strategy (e.g., cost cap to highest volume), or launch new campaigns that are cannibalizing budget from winners?
- Landing page/offer changes: did CRO, pricing, subscription terms, or the offer change in that window? A site change can tank CVR while spend keeps flowing.

**4. Funnel breakdown**

- I'd segment the drop: is CPM up, CTR down, or CVR down? Each points somewhere different:
  - CPM up + CTR/CVR flat → auction/demand-side issue (seasonality, competition, budget scaling too fast).
  - CTR down → creative fatigue or audience mismatch.
  - CVR down → landing page, offer, pricing, or site speed/trust issue (reviews, stock-outs).

**Close with a plan, not just a diagnosis:** "I'd build a simple table — week over week, CPM/CTR/CVR/AOV/ROAS — segmented by campaign and creative, layer in site-side conversion data, and present findings within 48 hours with a prioritized fix list, starting with whatever's cheapest to test (creative refresh, audience refresh) before touching structure or budgets."

---

## Q2: "An A/B test shows a 5% lift at p=0.08 — what do you do?"

This question is testing whether you understand statistical rigor without being paralyzed by it — DTC brands want people who make good calls under uncertainty, not academics.

**Core answer:** p=0.08 misses the conventional 0.05 threshold, so strictly speaking, I can't reject the null — I can't say with 95% confidence this isn't noise. But I wouldn't treat "not significant at 0.05" as "definitely nothing." I'd look at:

1. **Sample size and test duration.** Was this underpowered? If the test ran only 5-7 days or hit a low sample size, I'd rather extend the test to get a real read than make a call on a coin-flip p-value. Supplements often have longer consideration windows (people research ingredients, check reviews), so I'd want at least one full purchase cycle, ideally 2+ weeks including a weekend.

2. **Effect size and business impact.** A 5% lift on a scaled campaign is real money even if the confidence interval is wide. I'd calculate what a false positive costs (rolling out something with no real lift — minor cost, easy to revert) versus what a false negative costs (missing a real 5% lift because I was too conservative — real opportunity cost). In paid social, the cost of being wrong is usually low and reversible, so I lean toward continuing to test rather than either fully committing or fully discarding.

3. **What decision is actually on the table.** If this is "should I turn off the losing variant entirely," I'd want tighter confidence. If it's "should I let the test keep running one more week before deciding," 0.08 is a clear "yes, extend" — not a "kill" signal.

4. **Directional consistency.** Is the lift consistent across days/segments, or is it one good day carrying the average? I'd check the daily trend line, not just the topline p-value — a noisy pattern that averages to +5% is very different from a consistent +5% every day.

**My actual decision:** I wouldn't roll out on 0.08 alone, and I wouldn't kill it either. I'd extend the test to reach either significance or a pre-set sample size ceiling, while capping the downside (e.g., cap losing-variant spend rather than an even split) so I'm not burning budget on a coin flip while I wait. If timelines don't allow extending, I'd make the call based on business risk: low cost to implement, easy to revert → ship it and monitor; expensive or hard to unwind → don't.

**One-liner to land the point:** "p=0.08 means 'inconclusive,' not 'no.' My job is to decide whether it's worth more time to find out, not to treat 0.05 as a magic line."

---

## Q3: "We doubled a winning campaign's daily budget from $2K to $5K and ROAS fell while CPM nearly doubled — why?"

This is a classic scaling-mechanics question — they want to see you understand _auction dynamics_, not just say "audience fatigue" vaguely.

**The core mechanism:**

1. **Auction pressure / audience depth.** Jumping budget 150%+ in one move forces the algorithm to find that much more volume, fast. It exhausts the highest-intent, cheapest-to-reach slice of the audience within hours and starts bidding for lower-intent, more competitive inventory to hit spend — that's exactly what drives CPM up almost linearly with budget on a capped audience. This is especially sharp for a supplements brand with a narrower core buyer profile (health-conscious, existing customers, lookalikes off a modest purchase list) versus a mass-market product.

2. **Learning phase reset.** A budget change of that magnitude (generally >20-30% in Meta's case) can knock the ad set out of its learning phase and back into exploration. During re-learning, the algorithm spends more inefficiently while it re-calibrates who to show ads to, which shows up as worse CPM and CPA for days, not just hours.

3. **Delivery pacing pushing into worse placements/times.** To spend 2.5x in the same 24 hours, the system may deliver more aggressively into higher-competition dayparts or lower-performing placements (e.g., more Audience Network, less high-intent Feed/Reels) that it would otherwise avoid at a lower budget.

4. **Frequency and diminishing returns on the existing audience.** If the "winning" campaign was already efficient at $2K partly because it was tightly targeted, more budget on the same audience raises frequency, and you start re-showing the same people who already converted or already said no — classic diminishing marginal returns.

**What I'd say I'd have done differently, since that's the real point of this question:** Scale budget incrementally — roughly 20-30% every 2-3 days, giving the algorithm time to re-stabilize between increases — rather than 150% in one jump. If aggressive scale is genuinely needed fast, I'd do it by _duplicating_ the ad set/campaign with fresh budget (a "horizontal" scale) instead of inflating the existing winner, so the proven ad set keeps its learning and efficiency intact while the new copy explores incremental volume. I'd also pre-check audience size/saturation and have backup creative ready, since scaling spend without scaling creative supply is one of the most common ways a "winning" campaign breaks.

**Close:** "So the CPM/ROAS pattern here isn't a red flag that something's broken — it's the expected signature of scaling too fast into a limited audience. The fix isn't to panic and cut budget back to $2K, it's to step the scale-up down to something the algorithm and the audience can actually absorb, and diversify how we reach incremental volume rather than just turning up the dial on the same audience."

---

### A meta-note for the round itself

All three answers follow the same shape recruiters are grading for in a scenario round: **diagnose before prescribing, quantify the decision (cost of being wrong in each direction), and end with what you'd actually do next** — not just an explanation. If you only have time to sharpen one thing before tomorrow, practice saying the opening frame/clarifying question out loud first for each — it's what separates "knows the concepts" from "has actually run these accounts."
