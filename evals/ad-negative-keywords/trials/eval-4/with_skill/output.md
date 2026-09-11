## Diagnosis: the new "project management" negative is blocking your own core ad group

**Root cause:** the account-level phrase negative `project management` your new hire added conflicts with Novapoint's own core non-brand keywords. Since your core ad group is project-management software, its keywords almost certainly contain the phrase "project management" (e.g. *project management software*, *project management tool*, *best project management app*). A phrase negative blocks the words in that order with anything around them — so it silently blocks every query your own core keywords are supposed to match.

This is a known failure mode for this exact action (killing "how-to"/informational search terms with a bare `project management` negative) — it's flagged as the canonical mistake to avoid when negating that phrase.

## Why every symptom you listed fits

- **Keywords show "active", zero impressions:** Negatives always beat positives. A blocked active keyword still displays as active in the UI — it just never enters the auction. This is exactly what account-level exclusions do to keywords they conflict with.
- **Budget and bids untouched:** Irrelevant. The keyword isn't losing auctions on bid/budget — it's not reaching the auction at all. Nothing about bid strategy would produce this symptom.
- **Started 3 weeks ago, right after the search-term cleanup:** Matches the timing of the negative-keyword addition exactly.
- **"Review your bid strategy" from platform support:** A common, wrong first read — support tools generally don't surface "an account-level negative is shadowing this keyword" as a diagnosis; they see healthy bids/budget and default to bid-strategy advice. It's not looking at negative-keyword conflicts.

## Immediate fix

1. Open the account-level negative keyword list and find the phrase negative `project management`.
2. Remove it, or narrow it — this is the core conflict-check step this kind of change always needs and evidently didn't get.
3. Replace it with negatives that target the actual junk (informational/how-to intent) without matching your core phrase, e.g. phrase negatives: `what is project management`, `project management definition`, `project management meaning`, `how to do project management`, `project management course`, `project management tutorial`. These hit the how-to searches without containing your core buying-intent phrase as a standalone block.
4. Move these to a shared "informational" exclusion list rather than the account-wide raw list, if your platform supports it — same reach, easier to audit and reverse next time.
5. Re-check impressions on the core ad group within 24-48h once the negative is removed; they should resume immediately (no other lever — bids, budget, keyword status — needs to change).

## Prevent recurrence

- Before any negative goes in at account level, run the conflict check: does it match any active keyword anywhere in the account? Account-level is the hardest rung to audit and reverse — reserve it for universal disqualifiers that can never legitimately match a real keyword (e.g. `jobs`, `salary`, `free template`), never for a phrase that's also your product category.
- Add a **quarterly conflict sweep**: a full check of the account's negative lists against active keywords, specifically for this failure — "a negative silently zeroing a keyword that was serving" is the single most expensive mistake this kind of list produces, because impressions just go to zero with no error, no alert, and a support team that reads it as a bid problem.
- When negating informational/how-to queries, don't negate the bare product-category phrase — negate the informational *modifiers* (what is, how to, meaning, tutorial, course) instead, so the block can't collide with buying-intent queries containing the same core phrase.