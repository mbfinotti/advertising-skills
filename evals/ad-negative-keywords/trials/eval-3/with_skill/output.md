## Short answer: No, Google isn't ignoring your negatives — you've hit two documented mechanics gaps, not a bug.

### 1. "tent repair kit" negated, "tent repair kits" still shows

Negative keywords in Google Ads **never expand to close variants** — that's the opposite of how positive keywords behave. Plurals, synonyms, and word stems have to be added as their own separate negative entries. "kit" and "kits" are different tokens to the matching engine, so neither phrase nor exact match on "tent repair kit" will catch "tent repair kits."

**Fix:** add "tent repair kits" as its own negative (phrase match), plus any other plausible forms — "tent patch kit," "tent repair patches," etc.

There's a compounding suspect here too: when you add negatives straight from the Search Terms Report screen, **Google pre-selects Exact match by default** — the single most common trap in this workflow, because Exact blocks only that one literal string and nothing else. If your ~45 negatives from last month were added that way without manually switching the match type, that alone explains why "the same junk is back" under slightly different wording. Worth checking now: open your negative keyword list and look at the Match Type column — if most of last month's batch shows "Exact," that's very likely your real bottleneck, not just this one term.

### 2. Broad negative "free camping checklist" isn't blocking "free tent"

This is the classic broad-negative misunderstanding. A broad match negative blocks a search only when **all** its words are present (in any order) — it is not "block anything containing any one of these words." "free camping checklist" only fires when a query contains "free" *and* "camping" *and* "checklist" somewhere in it. "free tent" has none of "camping" or "checklist," so it sails through untouched. This is the exact mistake the skill flags as a known failure mode: people assume a multi-word broad negative acts like a single-word catch-all, and it doesn't.

**Fix, with a caution attached:** to actually block every query containing "free," you need a standalone negative on the single word **"free"** itself (broad or phrase — for a single word they behave the same). But before you add it: run the overblocking check first. "Free" is a common word in converting queries too (e.g. "free shipping," "free returns," any promo-driven search), and Google negative matching is word-level, not substring — so a "free" negative would *not* accidentally block "freestanding tent," but it *could* silently zero out a converting query you haven't checked for. Pull conversion history for anything containing "free" before you flip this on account-wide.

### 3. Don't add capitalized versions or typo variants

Stop that plan — it's wasted effort. Google Ads matches casing and common misspellings automatically for both positive and negative keywords. "Tent Repair Kit," "TENT REPAIR KIT," and "tent repare kit" are already covered by your existing negative; adding case/typo variants adds zero incremental blocking. Redirect that effort into what actually doesn't auto-match: plurals, synonyms, and word stems (kit/kits, checklist/checklists, repair/repairing, etc.) — that's the gap that's real.

### Why this keeps recurring monthly

Both failures point at the same root cause: negatives were added quickly from the report UI without checking match type or variant coverage, so the list *looks* maintained (45 entries!) while the actual query patterns keep leaking through gaps the entries were never built to close. To stop the monthly Groundhog Day:

- When adding from the Search Terms Report, manually switch match type to **phrase** by default (per-entry), reserving exact for surgical single-query blocks and broad only for single words or terms that are wrong in every word order.
- For every negative you add, immediately think through plural/synonym/stem variants and add them as separate entries in the same pass — don't wait for next month's report to show you the gap.
- If this is a recurring theme (it is — "tent repair kit[s]" is a service/DIY-adjacent query, "free X" is a DIY/free-intent theme), put it on a **shared exclusion list** rather than a one-off campaign negative, so it compounds across campaigns instead of needing rebuilding every month.

### What I'm not doing here

I haven't proposed a fresh batch of negative keyword candidates beyond fixing these two named terms, because that requires your actual Search Terms Report (cost/clicks/conversions per query) — I don't have it. If you want a full pass on Trailforge Outdoors' current junk traffic, send the report (7–30 day lookback) and answer quickly:

1. What counts as a conversion, and target CPA/ROAS?
2. Roughly what's the account's CPC range? (sets the click gate — 15-20 clicks default, tighter at $3+ CPC)
3. Any levels I can't edit (account vs. shared list vs. campaign)?
4. Any themes that must never be touched (brand terms, deliberate competitor bidding)?

With that I can run the full workflow — n-gram mining included, since Google only shows ~40–60% of actual search terms in the report — and hand you an additions table plus a do-not-negate list, not just point fixes.