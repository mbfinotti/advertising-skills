## Verdict: this structure won't work as planned. Two structural failures and one major gap, all fixable.

### 1. Budget floor — every ad set fails it, and so does the whole account

Meta's ad-set learning threshold is ~50 optimization events/week. Budget floor per ad set ≈ (target CPA × 50) ÷ 7.

At your $42 CPA that floor is **$300/day per ad set**. Your six ad sets:

| Ad set                | Budget/day | Conversions/week _at target CPA_ | vs. $300/day floor |
| --------------------- | ---------- | -------------------------------- | ------------------ |
| Cast iron enthusiasts | $25        | ~4.2                             | 8% funded          |
| Home chefs            | $25        | ~4.2                             | 8% funded          |
| Cooking show viewers  | $20        | ~3.3                             | 7% funded          |
| Wedding registry      | $20        | ~3.3                             | 7% funded          |
| 2% lookalike          | $20        | ~3.3                             | 7% funded          |
| Competitor brand fans | $10        | ~1.7                             | 3% funded          |

None gets close. This isn't fixable by reshuffling the split — even if you collapsed **all $120/day into one ad set**, that's still only 40% of the $300/day floor a $42 CPA needs. At this budget/CPA combination, the account will run "learning limited" almost regardless of structure. That's a budget-vs-CPA mismatch, not just a segmentation mistake — worth knowing before you fix the split.

### 2. Audience size floor — "competitor brand fans" fails it hard

900 people is far below Meta's delivery threshold (pools under ~1,000 struggle to deliver at all) and nowhere near the 500K–2M range Meta's own guidance targets for a prospecting audience. At $10/day it also can't be funded to significance.

Keeping it "for coverage" is the specific trap to avoid here: an audience that can't be funded to significance doesn't produce coverage, it produces a line item that never learns and drags blended account CPA down while it burns its $10/day. Cut it as a standalone ad set.

### 3. The bigger gap: no first-party or retargeting tier at all

Of the six tiers this kind of plan should draw from, efficiency order is `first-party custom > retargeting > lookalike > behavioral/in-market > cold broad > interest & affinity`. Your plan is built almost entirely from the **least** efficient tier — five of six ad sets are interest/affinity audiences (treated as loose suggestions by Meta's delivery algorithm, not hard constraints), plus one lookalike. There's no website-visitor/cart-abandoner retargeting pool and no first-party customer list audience.

For a live storefront these two are nearly free to stand up (an hour each, once a seed/pixel pool exists) and they're the cheapest, highest-intent conversions you're not currently capturing. This is very likely your single highest-leverage fix, ahead of anything else here.

Open question I can't answer without more info: do you have pixel traffic and a customer/email list? If either exists, both tiers should be added before you touch the six ad sets further.

---

## Revised structure

Fix order for underfunded tiers, in order of effort: merge upward > cheaper proxy event > cut. Applied here:

| Tier                              | What                                                                                                                                                                                 | Budget/day                                         | Why                                                                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Retargeting                       | Site visitors / cart abandoners (up to 180 days)                                                                                                                                     | ~$15–20                                            | New. Highest intent, cheapest to run, near-zero setup if pixel exists.                                                                                                                                                                                                                                                                                                                           |
| First-party custom                | Customer list, if one exists (email/orders)                                                                                                                                          | fold into retargeting spend or keep tiny/near-free | New. Also seeds a better lookalike than a generic one.                                                                                                                                                                                                                                                                                                                                           |
| Consolidated interest prospecting | Merge "cast iron enthusiasts" + "home chefs" + "cooking show viewers" into **one** ad set, stacked as detailed-targeting suggestions                                                 | ~$55–65                                            | These are all attribute signals on the same core ICP (people who cook/buy cookware) — Meta doesn't reward splitting near-identical interests into separate learning pools, since detailed targeting already gets treated as a soft suggestion, not a hard filter. Three ad sets buying the same audience three times just triples your distance from the learning floor for no precision gained. |
| 2% lookalike                      | Keep, but verify seed ≥1,000 (ideally an actual customer list, not a guess)                                                                                                          | ~$25–30                                            | Verify seed quality — this is `lookalike-audience-seeds` territory (mbfinotti/advertising-skills@lookalike-audience-seeds), not this skill's job.                                                                                                                                                                                                                                                |
| Wedding registry                  | Keep _only if_ you have evidence (past sales data) that gift-occasion buyers convert differently from self-purchasers — otherwise fold into the interest stack as a life-event layer | $0 or small                                        | It's a genuinely different signal (occasion, not attribute) if real, but "6 different ad sets" is a persona list, not evidence any of them behaves differently in your funnel. Name the source if you're keeping it separate.                                                                                                                                                                    |
| Competitor brand fans             | Cut as a standalone ad set                                                                                                                                                           | $0                                                 | 900 people can't be funded to significance at any split of $120/day. If you want it at all, add it as one more detailed-targeting layer inside the interest stack — costs nothing extra, no dedicated learning pool wasted on it.                                                                                                                                                                |

Roughly: $15–20 retargeting / ~$60 prospecting-interest / ~$25–30 lookalike. Skews prospecting-heavy, which is right for a launch-stage account (80–90% prospecting is standard here, not the 70–80% steady-state default) — but this still won't clear the $300/day floor. Treat this as the best structure available at $120/day, not a structure that will exit learning cleanly. Two honest paths from here, not mutually exclusive:

1. **Raise budget** toward the floor if the economics allow it, or
2. **Optimize to a cheaper upstream event** temporarily (e.g. Add to Cart or Checkout Initiated instead of Purchase) to get ad sets out of "learning limited" faster, then switch back to Purchase once volume builds — accepting a softer proxy metric in the meantime that you reconcile against actual CPA afterward.

### Before launch

- Build the exclusion matrix: retargeting/customer-list pool excluded from lookalike and prospecting; existing customers and employees excluded everywhere. None of this exists in the current plan.
- Audit overlap between the lookalike and the consolidated interest stack once both are live — a 2% lookalike seeded from converters will likely share real overlap with "people who cook," and >30% overlap between funded tiers should trigger an exclusion, not coexistence.
- No regulated-category flags here (cookware isn't a Special Ad Category), so no restricted-targeting mode to plan around.
