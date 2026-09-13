**Frequency cap: 3 per week** (hard cutoff), not per campaign lifetime — with a 3,200-person warm audience, "per week" is the only window that matters since you'll blow past any 30-day number in days.

**Why 3, not lower or higher:**

- Your CTR/CPM data shows the fatigue curve kicked in well before freq 9 — CPM rising as CTR falls is Meta's relevance score penalizing repetition, not just "market conditions."
- Single-video-creative retargeting on Sales objective typically holds up to freq 4–6/week before decay; you're already past that, so cap below where you broke, not at it.
- 3/week ≈ 9,600 impressions/week max against this pool — still enough delivery to convert, but you stop the spiral before CPM eats the campaign.

**The catch:** Sales-objective auction campaigns (which is what you're running) don't expose a native frequency-cap field in Ads Manager — that dial only exists under "Reach and Frequency" buying, which requires audience/impression minimums your 3,200-person pool won't clear. So you can't just type "3" into a box. Enforce it indirectly:

1. **Switch bidding to Cost Cap or Bid Cap** (Ad Set → Budget & Schedule → Cost per result goal). "Highest volume" is what drove frequency to 9 — it will keep spending into the same pool until the budget forces it to. A cost cap throttles delivery instead of exhausting reach.
2. **Add 2–3 more video variants now.** One creative absorbing all impressions is why frequency and fatigue are the same curve. Splitting the same budget across 3 ads roughly divides per-creative frequency by 3, even with total audience frequency unchanged.
3. **Exclude all converters/purchasers** from the retargeting custom audience if not already — every dollar hitting someone who already bought inflates frequency for no return.
4. **Check the Frequency breakdown weekly** (Ads Manager → Breakdown → By Delivery → Frequency) and manually pause/refresh once weekly freq crosses ~3–4, since there's no automated cap to do it for you.
5. **Grow the pool.** 3,200 is small for retargeting a Sales campaign — widen the lookback window (e.g., 30→90 or 180 days) or add engaged-video-viewer/engaged-with-page audiences so the same budget spreads over more people instead of hammering the same 3,200.

Bottom line: target ≤3 impressions/person/week, achieved via cost-cap bidding + creative rotation + weekly manual monitoring, since Ads Manager won't let you set that number directly for this campaign type.
