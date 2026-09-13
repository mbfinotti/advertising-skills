# Negative keyword setup — Corvale Systems (Microsoft Advertising, 6 campaigns)

## First, the broad-match idea won't work as proposed

Two problems, one platform fact and one mechanics issue:

- **Microsoft Advertising has no negative broad match at all** — only phrase and exact. There's nothing to add "broad match negatives" to; that option doesn't exist on this platform, full stop.
- Even on a platform that did have it, broad match negatives aren't the right tool for "cover a whole theme." Broad blocks any query containing _all_ the listed words in any order — it's the narrowest-intent, widest-blast-radius match type, reserved for terms that are wrong in _every_ recombination, not a bulk-coverage tool. **Phrase is the one built for exactly what you want**: one phrase negative (e.g., `"certification"`) blocks every query containing that word sequence, so it already kills the theme with far less risk of silently zeroing a converting query.

So: reject the broad-match plan on platform grounds, and redirect the underlying goal (kill the theme in one move) to phrase match, which does that job natively.

## Account lock changes the level structure — here's what's still open to you

The skill ranks exclusion levels `shared list > campaign/ad group > account`. With account settings locked:

- **Account-level is off the menu entirely** — not deprioritized, deleted. You have no way to express it, so don't plan around it.
- Good news: on Microsoft Advertising, **negative keyword lists attach at the campaign level, and attaching a list to a campaign is a campaign-level action** — it doesn't require account access. So the shared-list rung, which is exactly what a recurring cross-campaign theme calls for, is fully available to you despite the lock.

**Recommended structure:**

1. Build **one shared negative keyword list** — name it something like `Informational Intent - Training-Certification-Webinar`.
2. Populate it with **phrase-match negatives** covering the theme (see below).
3. **Attach that same list to all 6 campaigns.**

One caveat to check before building: Microsoft allows **only one negative keyword list per campaign**. If any of the 6 campaigns already has a different shared list attached, you can't stack a second one — you'd need to either merge the new theme into the existing list, or fall back to direct campaign-level (or ad-group-level) negatives for that specific campaign. Check this before you build the list, not after.

## Match type and variant expansion

Phrase negatives, one entry per stem, then manually expand — Microsoft doesn't filter close variants any more than Google does (plurals, synonyms, misspellings all still get through unless you list them):

| Root term       | Variants to add manually                           |
| --------------- | -------------------------------------------------- |
| `webinar`       | webinars, web seminar, online seminar              |
| `course`        | courses, training course, e-learning, online class |
| `certification` | certifications, certified, certificate, cert       |

Treat this as a **draft skeleton**, not a final list — I haven't seen the actual search term report yet, so these are theme-level placeholders from the informational-intent category, not evidenced candidates.

## What I still need before naming specific terms with real evidence

Per this skill's evidence gate, I won't hand you a finished additions table (specific terms + click/cost numbers) without the search term report — a list built from assumption has no evidence of what it actually matches, and the cost of a bad call (a blocked converting query) stays invisible until it's too late. Send the export and I'll run it through the click/cost gates and the overblocking review before anything goes live.

Also, four quick things to size the gates and protect against overblocking correctly:

1. **Does Corvale sell or promote any training, certification, or webinar offering itself?** If yes, those exact terms may be self-cannibalizing, not junk — this needs checking before any of them go on the list.
2. What counts as a conversion, and what's the target CPA?
3. What CPC range does the account run at? (Sets whether we use the standard 15–20 click gate or tighten to 10–12 for high CPC.)
4. Roughly what's the spend and date range on the report you're pulling?

## Cadence and the failure mode this setup is most exposed to

- Run this as a **recurring search-term pass** (weekly if any campaign is north of ~$10k/month or still learning; bi-weekly/monthly otherwise), 30–45 minutes, 7–14 day lookback.
- Because you're centralizing this theme into one shared list attached to 6 campaigns, the single biggest risk is **conflict with an active keyword** — a negative sitting above a live keyword silently zeros it while it still shows "active." Microsoft has a **dedicated negative keyword conflict report** — run it as part of your quarterly conflict sweep, and re-run it specifically whenever you add to this list, since a shared list touching 6 campaigns multiplies the blast radius of any one bad entry.

## Once the report is in hand

I'll deliver the pass in the standard shape: spend analyzed and wasted-spend %, an additions table (term / match type / level / evidence / category / variants), a do-not-negate list for anything with conversion history, a watchlist for terms that haven't cleared the gate yet, and the next review date.
