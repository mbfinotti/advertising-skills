## Fix for the Corvale Systems junk-query problem (Microsoft Advertising)

### First, a correction on the "broad match negatives" plan

Broad match negatives are the right _type_ in principle, but "one broad match negative covering the whole theme" is ambiguous and likely to do one of two wrong things:

- **One negative keyword with all the junk words together** (e.g. `-webinar course certification`) only blocks queries containing **all three words at once**. That's nearly nothing — this plan would barely fire and give a false sense of coverage.
- **A single broad negative per word** (`-webinar`, `-course`, `-certification`) _would_ work, but broad and phrase behave almost identically for single-word negatives — there's no real advantage to broad here, and a lone generic word blocks that word in **every context**, including any legitimate query where it might co-occur with something relevant to Corvale.

So: reject the "one broad negative for the theme" framing. Build a **list of individual phrase-match negatives**, reserving single-word broad negatives only for terms with zero legitimate use case for Corvale.

### Step 1 — Build the list from evidence, not guesswork

Pull query (search term) reports from all 6 campaigns, filter for the recurring theme, and cluster the actual offending queries into canonical phrases — e.g. `"online course"`, `"get certified"`, `"certification exam"`, `"free webinar"`, `"training program"` — rather than isolated words. Check each candidate against what Corvale actually sells: if they run any real certification, course, or webinar offering, some terms need to stay allowed in whichever ad group covers that offering.

### Step 2 — Choose match type per term

- **Phrase match** as the default for anything with plausible ambiguity — blocks the theme pattern without necessarily nuking every isolated occurrence of a word.
- **Broad match** only for single words that are unambiguously junk in 100% of contexts for this client.
- Avoid multi-word broad negatives meant to "catch everything at once" — they underperform, as shown above.

### Step 3 — Structure around the account-level lock

You can't rely on one account-wide shared negative keyword list if the client has locked account settings — but first clarify with the client whether that lock actually includes **Shared Library → Negative keyword lists**. In many Microsoft Ads client setups, shared-library negative lists are a separate permission from account settings (billing, UET tags, etc.) and might be grantable with a narrow, easy-to-approve ask: _"we need edit access to negative keyword lists in the shared library for cross-campaign query hygiene."_ That single unlock solves the whole duplication problem — worth pursuing before building a workaround.

If it's genuinely locked out:

1. Maintain the negative list as a spreadsheet — this is your single source of truth, not any one campaign's UI.
2. Use **Microsoft Advertising Editor** to bulk-push identical campaign-level negative keyword sets to all 6 campaigns at once. Editor operates within your campaign/ad-group access even without shared-library permissions, so this is the practical substitute for a shared list.
3. Every time you add a term to the spreadsheet, re-push via Editor to all 6 campaigns — never hand-edit one campaign's negatives directly, or the 6 campaigns will drift out of sync.

### Step 4 — Level: campaign, with ad-group exceptions

Apply the negatives at the **campaign level** in each of the 6 campaigns — the theme cuts across ad groups, so ad-group-level application would multiply your maintenance burden on top of the account lock you're already working around.

Exception: if one ad group in a campaign legitimately targets course/certification/webinar terms (Corvale's own training offering, say), Microsoft Ads has no "allow override" for a campaign-level negative. So instead: don't add the negative at that campaign's level at all — apply it individually to every _other_ ad group in that campaign, and leave the legitimate ad group untouched.

### Step 5 — Verify and govern

- Use the **negative keyword / search term exclusion report** in Microsoft Ads to confirm the negatives aren't silently suppressing converting queries — check this within the first week of adding broad-leaning entries especially.
- Re-pull query reports biweekly for the first month (the theme is entrenched, expect 1–2 cycles before it's fully suppressed), then monthly.
- Track clicks/spend avoided from the junk theme as a specific metric — useful both to justify the cleanup to the client and as evidence for the shared-library access ask in Step 3.
