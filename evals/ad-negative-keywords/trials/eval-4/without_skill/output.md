## Root cause: your new hire's negative keyword is silently blocking your own core keywords

The account-level phrase-match negative **"project management"** is a self-inflicted keyword conflict. It's not just filtering out the informational "how-to" searches — it's blocking the exact commercial queries your core non-brand ad group targets.

### Why this produces exactly the symptoms you're seeing

- Phrase match negatives block **any search query that contains the phrase in order**, with extra words allowed before/after. "project management software," "best project management tool," "project management app for teams" — all contain "project management" as a contiguous phrase, so all get blocked too.
- If your core non-brand ad group's positive keywords are variants like `project management software`, `project management tool`, `[project management app]`, the account-level negative neutralizes essentially the entire ad group. Zero impressions, three weeks straight — matching when the change was made.
- **Keyword status stays "active"** because a negative-keyword conflict doesn't disapprove or pause the keyword — it just prevents the auction from ever being entered for matching queries. Nothing in the standard status column reflects this.
- **Budget and bids are irrelevant** because the ad never reaches the auction stage. That's exactly why everything "looks normal" — you're checking downstream levers (bid strategy, budget, quality score) for a problem that happens upstream, before auction eligibility is even evaluated.
- **Platform support's "review your bid strategy" advice is a generic, wrong first pass.** First-line support almost never checks shared/account-level negative lists against ad-group-level positives — that cross-check isn't part of their default triage.

### Why it went unnoticed at creation time

Google Ads warns you about conflicts when you add a positive keyword that collides with an *existing* negative in the same ad group/campaign. It does **not** reliably warn you the other way around — when you add a negative to a shared, account-level list that collides with positive keywords living in a completely different ad group. That gap is exactly what let this slip through.

### How to confirm it in the account (do this first)

1. **Change History** (Tools & Settings → Change History): filter by "Negative keywords," find the date your new hire added `project management` phrase negative, and overlay it on the ad group's impressions graph. They should align exactly.
2. **Keyword diagnosis tool**: on the Keywords page for that ad group, click the status/magnifying-glass icon on any core keyword → "Why isn't my ad showing?" It will explicitly report a negative keyword conflict if this is the cause.
3. **Search terms report**: for that ad group, over the last 3 weeks, it should be essentially empty — another signature of queries never reaching auction at all, as opposed to reaching auction and losing (which would show impressions with low CTR/position).
4. Open Shared Library → Negative keyword lists, find the list containing `project management` (phrase match), and check which campaigns it's applied to — confirm your non-brand campaign is one of them.

### Fix

1. **Remove the phrase-match negative `project management`** from the account-level/shared list — it's too broad; it negates the head term your whole business is built on.
2. **Replace it with negatives that target the informational intent specifically**, not the core phrase:
   - `how to project management`
   - `project management tutorial`
   - `project management course`
   - `what is project management`
   - `project management definition`
   - `learn project management`
   - `project management jobs` / `salary` / `certification`
   - `free project management templates`
   
   Use phrase match on these longer, intent-specific strings so they don't collide with your commercial head terms.
3. **Scope future broad negatives at the campaign or ad-group level first**, not account-wide. If a negative is meant to clean up search terms for one campaign's irrelevant traffic, apply it there — only promote to the shared/account-level list once you've confirmed no other campaign's core keywords contain that phrase.
4. **Process fix**: before adding anything to an account-level negative keyword list, cross-check it against every ad group's core positive keywords across the account (export keywords, search for the negative term as a substring). This is the step that was skipped.

Once the phrase negative is removed or narrowed, impressions should resume within minutes to hours — there's no bid, budget, or Quality Score issue to fix.