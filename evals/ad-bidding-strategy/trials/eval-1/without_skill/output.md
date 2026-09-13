## Short answer

The agency is **directionally right to hold off on Target CPA, but wrong on the specifics**. "15 conversions in 30 days" is not a Google-enforced gate — you can flip Target CPA on today with zero conversion history, Google will not stop you. It's a _recommendation_, and even Google's own recommendation is usually stated as **~30 conversions/30 days for Target CPA**, not 15 — and ~50 is the number Google cites for **Target ROAS**, not for tCPA "working properly." It sounds like your agency has blended the two thresholds. That doesn't make their caution wrong, but it changes how urgently you should chase the number.

## Why the caution is still valid, even if the number's off

Target CPA is a machine-learning bid strategy: it needs enough conversion events to model your conversion probability per auction with low noise. At 9 conversions/month, the sample is small enough that one good or bad week skews the "learned" CPA target wildly — the algorithm can lock onto a distorted pattern and either overspend chasing phantom signal or throttle traffic. This is a real statistical problem, not a Google permission problem. So: agree with "don't switch yet," disagree with the framing that a hard number unlocks it.

## The math on your situation

- Current: ~$3,600/month spend → 9 conversions → ~$400 CPA (roughly matches your $370 figure).
- To reach 15/month at the same efficiency: ~$6,000/month (~$200/day) — a ~65% budget increase, and that's optimistic since you're already buying the highest-intent traffic; marginal conversions from more budget typically cost more, not the same.
- To reach 50/month: ~$20,000/month at current efficiency — over 5x your budget. For a niche B2B compliance buyer search volume, that ceiling may simply not exist — you could raise budget indefinitely and never get there because the _search demand itself_ is capped, not your spend.

Worth explicitly checking with the agency: is 50/month even reachable via Search for this vertical, or are they quoting a generic Google benchmark without checking your addressable search volume?

## What to do in the meantime

1. **Switch to "Maximize Conversions" (no CPA target), not manual CPC.** This is Google's actual stepping-stone strategy for low-volume accounts — no conversion-history minimum, it's Smart Bidding's auto-optimization within your budget cap, and it doesn't carry tCPA's target-lock risk. This is the standard answer to "what do we do below the threshold," and it's better than sitting on manual CPC, which wastes the auction-time signals Google could already be using.

2. **Consolidate conversion volume instead of fragmenting it.** If conversions are split across multiple campaigns/ad groups, each node individually has even less data than the 9/month total. Merge into fewer, tightly-themed campaigns so whichever bidding strategy you use has one denser pool to learn from.

3. **Feed the algorithm secondary signals without corrupting your real KPI.** Set up secondary conversion actions (form starts, pricing-page views, content downloads, chat opens) as _secondary_ (observation-only) conversions in Google Ads, keep "demo request" as the sole _primary_ conversion driving bidding. This gives Smart Bidding more data points to correlate against without diluting what you're actually optimizing for.

4. **Turn on Enhanced Conversions** if not already — improves match rate on the conversions you do have, which matters more when volume is thin.

5. **Consider importing sales-qualified outcomes via offline conversion import**, if your sales team scores demo requests (e.g., SQL vs. not). Don't bid on it yet at this volume, but start collecting it now — B2B compliance has a long cycle, and having that data ready matters once you do have enough volume to bid on a deeper-funnel event.

6. **Run manual CPC (or Maximize Conversions) actively, not passively.** Weekly search-term pruning, negative keyword additions, dayparting to business hours (B2B compliance buyers don't search evenings/weekends), and device bid adjustments will move CPA more at this volume than any bidding-strategy switch will.

7. **Push back on the agency for a volume-feasibility check**, not just a budget-increase ask: have them pull search volume/impression share data for your compliance keyword set and show what spend ceiling actually gets you to 30 (tCPA) — and whether 50 (tROAS-level) is realistic for this niche at all before you plan around it.
