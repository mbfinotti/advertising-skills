## Routing result: 4/4 map to named gaps — no skill in the collection covers any of them

I read `advertising-kickoff/SKILL.md` plus all three references (`skill-routing.md`, `context-artifact.md`, `routines.md`). No `advertising-context.md` exists for a Saltmarsh Outfitters project, so this would normally open a cold-start interview — but you already gave four fully-specified session goals, so I'm answering the routing question directly (matches invocation example 2: "Which advertising skill do I need?"), not running a full kickoff interview.

Per §3 and §9 ("Forcing a match" is a named failure mode), here is each task checked against the 31-skill table and the coverage-gap list:

**1. Positive keyword lists for hiking-boots, search term expansion, new match types**
→ **No skill fits.** Gap, stated verbatim in `references/skill-routing.md`: _"Positive keyword research and keyword expansion (`mbfinotti/advertising-skills@ad-negative-keywords` builds exclusions only)."_ `ad-negative-keywords` is the adjacent skill and will look plausible, but its declared scope is explicitly "positive keyword research or bid strategy → do not route here." Once you've built the positive lists yourself, that same skill becomes useful downstream for mining the resulting search term reports into negative lists.

**2. Geo-holdout incrementality test for the CMO**
→ **No skill fits.** Gap: _"Incrementality testing (holdout, geo-lift) and media mix modeling."_ Nothing in the budget cluster substitutes — `cac-roas-benchmark` judges CAC/ROAS health against benchmarks but doesn't establish causality, and `ad-attribution-gap` explains platform-vs-source-of-truth discrepancies, not whether ads caused incremental sales.

**3. Google account suspension appeal ("circumventing systems")**
→ **No skill fits.** Gap: _"Ad policy appeals, disapprovals, and account suspension recovery."_ `ad-account-diagnostic` is the closest-sounding skill but its own scope stops at diagnosing an underperforming account (tracking, structure, targeting, creative, bidding, offer) — it doesn't cover platform policy enforcement or reinstatement.

**4. 400 disapproved Merchant Center items**
→ **No skill fits.** Gap: _"Product feed / catalog management for shopping and retail media."_ Nothing in the creative or account clusters covers catalog attributes, GTIN/image/policy disapprovals, or feed structure.

## Bottom line

The collection has no skill for any of these four — they're all pre-named gaps in v1, not a routing failure on my part. All four also share the trait §3 calls out for "in-platform execution": they require hands-on work in Google Ads/Merchant Center/Meta itself (building the actual keyword lists, filing the actual appeal form, editing the actual feed, designing the actual geo split), which this collection is scoped to never do regardless of category.

What I'd suggest instead of a skill:

- **(1)** Standard SEM keyword research workflow (Keyword Planner / Search Terms report + manual expansion) — outside this collection.
- **(2)** A geo-lift methodology reference (e.g., platform-native geo experiments in Google Ads/Meta, or a third-party MMM vendor) — outside this collection.
- **(3)** File directly through Google Ads' policy-appeal form with your account rep/support if you have one; "circumventing systems" suspensions usually need documented proof of legitimate account ownership and activity — outside this collection.
- **(4)** Google Merchant Center's own Diagnostics tab lists the specific disapproval reason per item (GTIN mismatch, image policy, missing attributes, misrepresentation) — work the list from there; outside this collection.

None of these four should be force-fit to an existing skill entry — doing so would burn a session and hide the real gap, which is exactly what §9 warns against.
