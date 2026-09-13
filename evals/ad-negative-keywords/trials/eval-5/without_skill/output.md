## Where the $7k went

The search terms report only covers **actual keyword-matched Search traffic**. It systematically excludes three buckets of spend, and for an ecommerce account any of these three can easily add up to ~40% of budget:

**1. Performance Max and Shopping spend (usually the biggest chunk)**
PMax and standard/Smart Shopping don't produce a queryable, row-level search terms report. Google only exposes a _category-level_ "Search terms insights" panel in the UI — no cost, no clicks, no CPA per row, and it's not available via the API (`search_term_view` simply doesn't populate for these channel types). If Fernhaven Kitchens runs PMax for Shopping (very common for ecommerce), that spend is real, it converts, but it is structurally invisible in the report you're summing.

**2. Google's privacy threshold on rare queries**
Google explicitly withholds search terms that don't meet a minimum query-volume threshold, to avoid exposing near-unique/PII-ish queries. On a long-tail account this can hide a real slice of spend — rows exist in aggregate cost but never surface as an individual term. This is normally single-digit-to-teens percent, not the whole gap, but it stacks on top of #1.

**3. Network/channel mismatches**
If any Search campaigns have "Search Partners" or "Display Network" opted in (default on some older campaigns), or you're running Dynamic Search Ads grouped oddly, some of that spend reports under different views (`campaign` cost vs. `search_term_view` cost) and won't reconcile to the row-level report either.

**Bottom line:** you're not missing $7k of "junk" — you're missing an entire _channel type's_ worth of visibility. The 9k you can see is Search; the other 7k is very likely PMax/Shopping (opaque by design) plus normal privacy suppression.

## Step 1 — confirm this diagnosis instead of guessing

Pull cost by campaign _type_ and compare it against `search_term_view` cost per campaign, via the Ads API. This nails down exactly which channel is eating the 7k, in minutes:

```python
from google.ads.googleads.client import GoogleAdsClient

client = GoogleAdsClient.load_from_storage("google-ads.yaml")
ga_service = client.get_service("GoogleAdsService")
customer_id = "XXXXXXXXXX"

# Cost per campaign, with channel type — the "true" total
query_total = """
    SELECT campaign.name, campaign.advertising_channel_type,
           metrics.cost_micros
    FROM campaign
    WHERE segments.date DURING LAST_30_DAYS
"""

# Cost visible in the search terms report — the "9k" total
query_search_terms = """
    SELECT campaign.name, metrics.cost_micros
    FROM search_term_view
    WHERE segments.date DURING LAST_30_DAYS
"""
```

Sum `metrics.cost_micros` (÷1,000,000) from both, grouped by `campaign.advertising_channel_type`. You'll almost certainly see `PERFORMANCE_MAX` and/or `SHOPPING` rows present in the first query and **absent entirely** from the second — that's your $7k, with an exact number attached to each campaign instead of a mystery.

## Step 2 — find junk queries, per channel, using what's actually available

The two halves of your budget need different tooling because they're genuinely different levels of transparency.

**Search / DSA campaigns (your visible $9k) — full row-level control, mine it properly**
You have complete data here, so this is the easy half:

- Pull `search_term_view` for the full account (query above, extend `SELECT` with `metrics.clicks, metrics.conversions, metrics.conversions_value, search_term_view.search_term`).
- Build an n-gram cost table in `pandas`: tokenize each search term, group by unigram/bigram, sum cost and conversions per token. Tokens with high cost and zero conversions are your negative-keyword candidates — this catches junk you'd never spot term-by-term (e.g. "free", "diy", "used", "parts", competitor brand names).
- Flag terms with `cost > X` and `conversions == 0` over a rolling 30/60/90-day window as the actual negative-keyword queue, reviewed weekly.

**Performance Max / Shopping (the invisible $7k) — you don't get search terms, so work around it, not through it**

1. **Search terms insights (UI only, categorical)** — go to the PMax asset group's Insights page. It groups auto-generated queries into _categories_ with a relative volume trend, no cost/conversion numbers, no export via API. It's the only Google-native window into what's being matched. Check it weekly; it's the closest thing to a search terms report PMax gives you.
2. **Account-level negative keyword lists** — PMax respects account-level brand-exclusion and negative-keyword lists (brand exclusions self-serve in UI; broader negatives require a request to your Google rep for full negative keyword support on PMax, though brand-safety exclusions and some negatives are now self-serve — check current UI, this has been loosening). This is your only lever to actually block junk, since you can't see individual queries to exclude one-by-one.
3. **Listing group / product-level reporting** — pull `shopping_performance_view` (for standard Shopping) or asset-group/listing-group performance (for PMax) to at least see _which products_ are burning spend with no conversions, even without the query that triggered it. This tells you to fix product titles/GTINs/feed quality rather than negatives — often the real lever for PMax waste.
4. **Audience signals** — tightening/removing bad audience signals in PMax narrows the matching the algorithm does, indirectly cutting junk-query exposure even though you never see the queries themselves.
5. **GA4 cross-check** — if UTM/auto-tagging is on, GA4 landing-page + session data (not query-level for privacy, but campaign/ad-group/device/geo level) can surface which PMax segments are converting vs. not, to redirect budget even without term-level detail.

## The honest tradeoff to put to the account owner (you)

PMax/Shopping trades query-level control for automated reach and usually better ROAS at scale — that's the deal Google is offering, not a bug. If junk-query visibility matters more to you than the automation, the concrete move is to carve a test budget out of PMax into a standard Shopping + Search combo, run it 4-6 weeks, and compare CPA — that tells you whether the $7k of opacity is costing you in waste, or whether it's converting fine and the opacity just _feels_ bad. Given ecommerce PMax often outperforms manual Shopping on ROAS, I'd quantify with Step 1 before assuming it's actually wasted spend.
