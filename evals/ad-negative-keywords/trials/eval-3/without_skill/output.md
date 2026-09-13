No, Google isn't ignoring your negatives — this is expected behavior based on how Google Ads matches negative keywords, and it trips up most advertisers at some point. Here's what's actually happening:

## 1. "tent repair kit" not blocking "tent repair kits"

**Match type is the cause.** When you add a negative straight from the Search Terms report, Google Ads defaults it to **exact match** unless you explicitly choose otherwise. An exact-match negative only blocks that literal string (plus very close variants — but plural/singular is _not_ guaranteed to be treated as a close variant for negatives the way it is for positive keywords).

- Negative exact `[tent repair kit]` → blocks searches for "tent repair kit" only
- Search "tent repair kits" → different string → **not blocked**

**Fix:** Use negative **phrase match** instead: `"tent repair kit"` (with quotes, no brackets). Phrase match negatives block any search that contains that sequence of words, including "tent repair kits," "tent repair kit reviews," "cheap tent repair kit," etc. This one change would have caught your plural problem without you lifting a finger.

## 2. Broad negative "free camping checklist" not blocking "free tent"

**This is the single biggest misconception about broad match negatives**, and it's the important one to fix before you add 45 more keywords.

Broad match negative keywords only block a search if **ALL the words in the negative appear somewhere in the search term** (in any order, not necessarily adjacent). They do **not** work like a broad match positive keyword, which expands to synonyms/related concepts/individual terms.

- Negative broad `free camping checklist` → only blocks searches containing "free" **AND** "camping" **AND** "checklist**"** all together
- Search "free tent" → has "free" but not "camping" or "checklist" → **not blocked**

If your actual goal was "block anything with the word 'free' in it," you needed a broad match negative of just **`free`** by itself — a single-word broad negative. `free camping checklist` as one broad negative is really an AND condition across three words, not an OR.

**Fix:** Add `free` (single word, broad match) as its own negative. Be careful though — this will also block legitimate queries like "free shipping tent" or "free camping guide" if you actually want that traffic; broad single-word negatives are blunt instruments, so sanity-check against your Search Terms report first.

## Why this matters more than it looks

These two mechanics explain the "junk keeps coming back" pattern almost entirely — this isn't Google ignoring you, it's 45 negatives that were each narrower than intended. Before you add capitalized versions or typo variants, know that **capitalization never matters** — Google Ads negative matching (like all keyword matching) is case-insensitive, so `Tent Repair Kit` and `tent repair kit` behave identically. Adding capitalized duplicates would do nothing except clutter your list.

## What I'd actually do instead of adding 45 more negatives

1. **Switch match type, don't just add more exact negatives.** Go back through last month's ~45 negatives. For any of them meant to block a _concept_ rather than one literal query, convert to phrase match `"..."`. Exact match `[...]` should be reserved for cases where you deliberately want to block only that one specific string (rare).
2. **Build broad negatives word-by-word for "kill everything containing X" intent.** If you want to nuke all DIY/free-related traffic, add single broad-match terms like `free`, `repair kit`, `how to`, `diy` individually rather than bundling them into one multi-word broad negative.
3. **Skip typo variants entirely for now.** Typos are a long tail — you'll spend forever chasing them one by one. Instead, at the ad group or campaign level, review Search Terms weekly and add negatives in batches; or consider a **negative keyword list** shared across campaigns so match-type fixes propagate everywhere at once instead of being fixed per-campaign.
4. **Check where the negatives were added.** If any were added at the _ad group_ level, they won't block that query in other ad groups/campaigns. Since you're managing this across "the store," confirm your negatives that are meant to be account-wide are in a shared negative list applied to all relevant campaigns, not stuck in one ad group.
5. **Re-audit last month's 45 after switching match types**, rather than layering 45+ new ones on top — you'll likely find 15-20 of them were exact-match when they should've been phrase, and that alone will silently fix most of the "it's back" reports you're seeing this month.

**Bottom line:** the negatives aren't broken or ignored — exact match negatives are literal-string-only, and broad match negatives require every word to be present (not "any word"), which is the opposite of what most people assume "broad" means when applied to negatives. Fix the match types on your existing list before expanding it.
