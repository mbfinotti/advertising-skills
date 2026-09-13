## Where the $7k went

It's not missing — it's real spend that the search term report is structurally forbidden from itemizing. Two separate mechanisms cause this, and they stack:

**1. Google's query-string privacy threshold (most likely the bulk of it).** Since September 2020, Google Ads omits any individual search term from the report if it didn't clear an internal minimum query-volume threshold — the cost still rolls up correctly into your keyword, ad group, and campaign totals (so your $16k account total is accurate), it's just never broken out at the term level. Practitioner measurements put this at **~40% of spend on average, ranging 20-80%**. $7k of $16k is **43.75%** — almost exactly on that midpoint. This is the leading explanation, not a bug or a tracking error.

**2. Campaign types with no real search-term report.** If any of that $16k runs through Performance Max or standard Shopping, those don't have a conventional search terms report at all — PMax gives you "search category insights" (thematic, not literal queries), Shopping's term-level visibility is partial. If a chunk of your budget is there, that alone explains part of the gap independent of #1.

I need one fact to tell you which of these dominates: **what's your campaign type mix — pure Search, or some PMax/Shopping in there too?** That changes where you point effort next.

## How to find junk you can't see

Be precise about what's actually possible here, because two different problems get conflated under "hidden queries":

- **Junk buried in the visible $9k** — real, fixable today. You _can_ see these rows; you're just not going to spot every bad pattern by eyeball-scanning hundreds of one-off long-tail queries, especially ones that individually sit under the click/cost gate but repeat the same junk theme dozens of times.
- **Spend Google suppressed from the report entirely (the $7k)** — you cannot recover the literal query text. No tool, script, or API call gets it back; Google doesn't expose it, full stop. Anyone selling you a way to "unhide" it is selling snake oil.

So the approach splits in two:

### A. Mine the visible $9k harder (n-gram/token mining)

Instead of gating on individual search terms, tokenize every visible query into unigrams/bigrams/trigrams and aggregate cost/clicks/conversions **per token** across every query that contains it. A theme like "free," "repair," "jobs," or "wholesale" that never individually trips the 15-20-click gate on any single query can easily blow past it once you sum every query carrying that token.

I've sent you `mine_search_terms.py` — it does exactly this:

```bash
python mine_search_terms.py search_terms_export.csv --target-cpa 40 --out token_report.csv
```

- Reads your search term export (cost, clicks, conversions per row — Google Ads UI export or GAQL pull both work).
- Builds every 1-, 2-, and 3-word n-gram per query, aggregates spend/conversions per token across the whole file.
- Applies the same gates as the manual workflow: zero conversions **and** (≥15-20 clicks at normal CPC / ≥10-12 at $3+ CPC, tightened automatically from your average CPC) **or** spend ≥1.5-2x target CPA.
- Outputs `token_report.csv` sorted by cost, flagged `candidate=True/False`, with sample queries per token so you can eyeball what's actually in there before acting.
- This is a surfacing tool, not a decision-maker — every flagged token still needs the overblocking review (did this token, or a close sibling, ever convert? would negating it also kill a converting query?) before it becomes a negative.

### B. Attack the invisible $7k indirectly

You can't see the queries, but you can see where the money that generated them sits:

1. **Break down cost by campaign/ad group**, compare it against search-term-report cost for the same container. The gap concentrates unevenly — a broad-match, top-of-funnel ad group leaks far more into the hidden bucket than a tight exact-match one. That tells you _where_ to be aggressive even without literal query text.
2. **Use PMax search category insights** if applicable — thematic, not literal, but it's the closest thing to visibility that surface has.
3. **Apply the taxonomy proactively, not reactively**, on the ad groups the gap analysis flags: job-seeker, DIY/free, informational, wrong-product-tier phrase negatives at the shared-list level, based on what you already know is irrelevant to your catalog — you don't need to see the exact query "free stand mixer template" to know "free," "template," "diy," and "wholesale" are never going to buy kitchen appliances at your price point.
4. **Re-measure the gap next pass.** If it shrinks, the shared-list negatives are catching hidden-bucket queries even though you never saw them individually — spend on a token moves whether or not the report itemizes the query.

## What I need before naming actual negatives

I haven't proposed a single specific term to block — I don't have your report, and this skill's evidence gate is explicit: no negatives without query-level data to check against. Once you export and run the script, send me `token_report.csv` (or the raw export) and answer these so I size the gates and pick levels correctly:

1. Conversion definition, and target CPA or ROAS/margin?
2. Average CPC range? (sets the click-gate tightness)
3. Any protected terms — brand, deliberate competitor bidding?
4. What levels can you edit — shared list, campaign/ad group, account?
5. One-off cleanup or standing weekly pass? At $16k/month you're solidly in weekly-cadence territory (7-14 day lookback).

Once I have the export, I'll deliver: additions table (term, match type, level, evidence, category, variants), do-not-negate list with reasons, watchlist, and next review date — same shape as the token report, just decided.
