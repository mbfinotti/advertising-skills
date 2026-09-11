## Reconciliation Answer — Loamworks Attribution Gap

**No.** "Biggest number first" is the exact trap this analysis is built to catch. The skill's rule is: rank defects by **revenue at stake per unit of fix effort**, never by revenue alone — because the two orderings invert, and cross-device is the textbook case of a number that's large *and* expensive to fix, which pushes it toward the bottom of an effort-constrained quarter, not the top.

Three things to flag before the ranking, because they change what "fixing" each item actually buys:

- **These four numbers don't sum into one gap.** They're four different variance pairs: (a) is platform-vs-anchor, (b) is the anchor's own count, (c) is analytics-vs-anchor, (d) is a channel-mix shift with no total-level change. Don't report "$99k/month at stake" as a single figure.
- **Only (b) and (c) touch real revenue exposure.** (a) corrects what the ad platform *claims* — no dollars move, but it's currently distorting bid optimization. (b) corrects the anchor's own order count. (d) shifts channel *credit*, not total revenue — the $9k already landed in the order system, just mislabeled "direct." (c) is genuinely unattributed: revenue with no channel credit anywhere.
- All four pass the direction check against their named mechanism (duplicate tag → platform high; test orders → anchor high; cross-device → analytics low; stripped UTM → direct share up, total flat), so all four classify as Bucket 3 (unexplained residual / defect), not Bucket 1 (timing) or Bucket 2 (definitional — those never get "fixed," these do).

### Fix order

| # | Defect | Bucket 3 mechanism | Revenue at stake | Fix effort | Position after adjustment |
|---|---|---|---|---|---|
| 1 | Duplicated purchase tag | Duplicate-firing tag (platform high) | $29k/mo over-claimed by the platform (not real revenue — see above) | An hour: one owner edits one tag container, fully reversible | **First.** Efficiency leader in this class — largest ratio of impact to effort, and it doesn't touch the booked engineering queue. Tag container edits are normally owned by marketing ops/analytics, not core engineering — confirm that's true here before assuming it's blocked. |
| 2 | ~220 test orders/month | Anchor pollution (anchor high — the anchor can be wrong too) | $6k/mo of the order system's own reported revenue | Near-zero: analyst filters known internal/test accounts out of the reporting query | **Second.** Smallest number on the list, but cheapest fix by far — the analyst owns this outright, no other team involved. Knock it out same week as #1. |
| 3 | UTM stripped by link shortener | Stripped tracking parameters (channel-mix shift to "direct," no total-level change) | $9k/mo misattributed, not lost | An hour, but a *second* team's hour — whoever owns the redirect/shortener config | **Third, conditionally.** If it's a shortener setting (pass-through params), it's a config change, keep it in the fast lane. If it needs custom redirect-service code, it now competes for the same booked engineering capacity as #4 — confirm ownership before committing a slot. This is the one item on the list actually at risk of the engineering constraint. |
| 4 | Cross-device tracking losses | Cross-device/identity gap (analytics low, platform less affected) | $55k/mo unattributed — biggest number on the list | A quarter of engineering, or a standing job — structural at any effort | **Last, despite the size.** Three reasons: it needs exactly the resource that's fully booked this quarter; it's been *stable* for four months, not growing, so the one condition that would promote it above the hour-scale fixes doesn't fire by default; and fixing it recovers attribution *visibility*, not $55k of new revenue — that money already landed in the order system, it's just uncredited to a channel. |

### What this means operationally

- Ship #1 and #2 this week. Both are analyst/marketing-ops work, zero engineering dependency, fully reversible, and together they clean up $35k/month of reporting distortion without touching the booked queue.
- Confirm ownership on #3 before scheduling it — it's the swing item between "another quick win" and "competes with #4 for the same scarce resource."
- Don't let #4 disappear. Document it as a known delta to carry forward this quarter (stable ≈ $55k/mo unattributed, cause: cross-device/identity), not as a solved or dropped item. Two things would override the "last" placement and justify pulling it forward even with engineering booked:
  - the $55k stops being stable and starts **growing** period over period, or
  - a channel-level budget reallocation decision this quarter is actually being **distorted** by the missing attribution (e.g., a channel is about to get cut because cross-device losses make it look worse than it is).
  If neither is true, the cheap interim move is self-reported attribution (a post-purchase "how did you hear about us" field) — it doesn't need engineering, gives a rough independent channel signal, and can run in parallel while the real identity-resolution build waits for capacity next quarter.
- Hand off #1, #3 (if engineering-owned), and #4 to `mbfinotti/advertising-skills@ad-conversion-tracking` for the actual technical fixes — this reconciliation's job stops at naming, quantifying, and ranking them.

**Bottom line:** fix duplicate tag → test orders → stripped UTM (ownership-permitting) → cross-device, in that order. The $55k number is real and worth tracking, but ranking it first would spend your one scarce resource — engineering — on the slowest-resolving item on the list while three cheaper, faster fixes worth $35–44k/month sit untouched.