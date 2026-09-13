No search access granted, so this is from standing knowledge of how Google Ads Smart Bidding tools work — this guidance has been stable for years. Here's the sanity check:

## Two problems with the plan as described

**1. Seasonality adjustment scoped to "all of November" is the wrong tool for that job.**

Seasonality adjustments are built for short, sharp spikes — Google's own guidance caps recommended use at 1–7 days (14 max). They work by telling Smart Bidding "expect conversion rate to jump by X% for this window," and the algorithm bids up accordingly for the _entire_ window you specify.

Your BFCM weekend genuinely triples (+200% is right _for that weekend_). But the rest of November only "runs hot" — some smaller, sustained lift, not 3x. If you apply +200% across all 30 days, you're telling Smart Bidding to bid as if every November day converts at BFCM-weekend rates. Result: overbidding (and overspending) on the ~26 non-peak days, since the multiplier doesn't taper.

**Fix:** Scope the seasonality adjustment tightly to the actual sale window (e.g. Black Friday through Cyber Monday, adjust start a day earlier if your sale opens before Thanksgiving). Leave the rest of November alone — Smart Bidding's own ML adapts to a real, sustained conversion-rate lift within roughly 1–2 weeks on its own. Don't fight it with a static manual override for a month; if the non-peak lift is real and sustained, that's a target (tCPA/tROAS) conversation, not a seasonality-adjustment one.

**2. The data exclusion over the sale weekend contradicts the seasonality adjustment — and shouldn't be there at all.**

Data exclusions exist for genuinely anomalous data you _don't_ want the model learning from because it won't recur or doesn't reflect real customer behavior: a tracking outage, a payment processor failure, a site crash, a bugged promo code — not-representative noise.

BFCM is the opposite of that. It's a real, recurring, predictable annual event, and the conversion spike has a real cause you're intentionally creating (25% off sitewide). That's exactly the kind of signal Smart Bidding should learn from, not discard — both for calibrating bids for _next_ year's BFCM, and because Smart Bidding models use trailing conversion history to spot seasonal patterns automatically over time.

Stacking both changes at once is also internally inconsistent: you'd be telling the algorithm "bid aggressively, expect 3x conversion rate" via the seasonality adjustment, then telling it "and forget everything that actually happened" via the exclusion. You lose the ability to verify the adjustment even worked, and you blind the model to your single highest-intent, highest-revenue weekend of the year.

**Fix:** Don't exclude BFCM weekend data. Only add a data exclusion if something actually breaks during that window (conversion tracking hiccup, checkout errors, an outage) — and scope the exclusion to just that broken sub-window, not the whole weekend.

## What I'd actually set up

- One seasonality adjustment, +200% conversion rate, scoped to the sale dates only (BF→CM, extend a day if the sale opens early) — Black Friday 2026 falls Nov 27, Cyber Monday Nov 30 — applied at the campaign level to whatever campaigns run the promo. Set it up a few days ahead, remove it right after.
- No data exclusion for the sale weekend, unless something technical actually breaks — in which case exclude only that specific broken window, not the whole event.
- Nothing special for the rest of November's moderate lift — let Smart Bidding adapt naturally; watch tCPA/tROAS daily and nudge targets manually only if it's underdelivering, rather than pre-setting a blanket adjustment.
- Remember the 25% discount itself is a real driver Smart Bidding should be allowed to see (it partly explains the CVR lift) — another reason not to exclude the data.
