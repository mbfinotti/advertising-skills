Not quite — a few things in that plan will actively hurt lookalike quality on Meta. Here's the fix.

## What's wrong

**1. Currency mixing is the biggest issue.** Merging USD and EUR spend into one raw number means your "top 15%" is really "top 15% skewed toward whichever currency happens to have the larger face value at the moment," not top 15% by actual value. €500 and $500 are not the same spend, and Meta's value-based LAL has no idea one column secretly contains two currencies. Convert everything to one currency first (pick USD or EUR, use a consistent rate — ideally each order's rate at transaction time, or at minimum a recent fixed rate), or better, run **two separate value-based lookalikes** (one per store/currency) if the stores also correspond to different ad accounts or targeting geos. Given you likely run US and EU campaigns separately anyway, two lookalikes is probably the cleaner move regardless of the currency fix.

**2. The corporate account (~200x median) will distort the model, not just sit as an outlier.** Value-based LAL works by weighting seed users so Meta's model leans toward finding people who resemble your *highest-value* customers most. One account at 200x median doesn't just get included — it can dominate the weighting and pull the whole lookalike toward "whatever a bulk-buying B2B account looks like," which is almost certainly not the customer profile you're trying to prospect for as a DTC brand. Exclude it. Also worth checking if there are other B2B/wholesale accounts at 20-50x median that deserve the same treatment — this is usually not a n=1 problem.

**3. Top-15%-by-spend as your selection method compounds the corporate account problem** — you're building a segment specifically selected for containing extreme-value outliers, then feeding raw spend as the value signal. That's belt-and-suspenders for getting a distorted model. Consider capping/winsorizing extreme values (e.g., cap at some percentile like p99) or using log-transformed spend as the value column instead of raw dollars — this is standard practice for value-based LALs when spend is long-tailed, which retail spend almost always is.

**4. $0 gift recipients shouldn't be in a spend-based seed at all.** They're not customers by your own value metric — including them with a $0 value either gets floored/dropped by Meta or just adds noise. Filter them out entirely rather than uploading them with value=0. (If you want a separate signal for "gift recipient propensity," that's a genuinely different audience/campaign, not part of this one.)

**5. Minor but worth flagging: think about the lifetime spend window.** "Lifetime spend" for a 62k-customer base likely spans years, meaning a top-15%-by-total-spend list overweights your oldest/longest-tenured customers over people who are recently high-value. If you have customers acquired 4 years ago with high cumulative spend but who've since churned, the lookalike will look for more people like them — not necessarily people who convert well *today*. Consider whether a trailing-12/24-month spend window (or recency-weighted value) better represents "who we want more of" than pure all-time total.

## Revised plan

1. Convert EUR → USD (or vice versa) using a consistent methodology, or split into two currency-matched lookalikes.
2. Exclude $0 gift-recipient rows.
3. Exclude (or separately flag and exclude) the corporate/wholesale account and any other clear B2B outliers.
4. Decide on a spend window — lifetime vs. trailing 12-24mo — deliberately, not by default.
5. Cap or log-transform the value column to blunt remaining long-tail skew.
6. *Then* take your top 15% (or just upload the full qualifying customer file with value — Meta's value-based LAL doesn't require pre-filtering to a top percentile; you can let the algorithm weight the full base by value instead of truncating it, which often performs better than an arbitrary top-15% cutoff).

If your CRM/CDP can export a clean, currency-normalized, deduped file with a `customer_id`, `value` column, and hashed email/phone for matching, that's the ideal source — happy to help write that export query or clean an existing extract if you share the schema.