# Push back before signing: Calloway Cycles targeting doc

Two of the five tactics rely on features that are being retired or don't exist as described. That's the strongest signal this doc is templated, not written for you.

## 1. Google Similar Audiences (converter list) — 🔴 dead feature

Google fully sunset Similar Audiences (Similar Segments) in 2023 — it's not buildable in Google Ads anymore, on Search, Display, Video, or Gmail. If the agency is proposing to "build" one, they're either working from stale documentation or planning to configure something else and mislabeling it.

**Ask them to specify**: do they actually mean uploading your converter list as a Customer Match segment and letting **Optimized Targeting / Audience Expansion** find similar users automatically? That's the real current equivalent — different mechanics, different reporting, no manual "similar audience" object to review.

## 2. LinkedIn Lookalike Audiences (2,400 wholesale contacts) — 🟠 being phased out, plus a data-use question

LinkedIn has been sunsetting Lookalike Audiences in favor of AI-driven **Predictive Audiences** inside Matched Audiences. Confirm in their live Campaign Manager account that classic Lookalike is still available before this becomes a line item you're paying for — don't take the doc's word for it.

Separate issue, independent of the tooling: those 2,400 contacts are wholesale/B2B records, almost certainly collected for order and account management, not marketing. Before they get hashed and uploaded to LinkedIn:

- Confirm your privacy notice or wholesale contract terms actually cover using this data for ad-audience matching.
- Confirm a Data Processing Agreement is in place with LinkedIn for this use.
- Don't let this become "we had the emails, so we used them" — that's the kind of thing that gets flagged in a GDPR complaint, not a hypothetical.

Also set expectations: LinkedIn's match rate on non-LinkedIn-registered business emails is often 20–30%. 2,400 contacts could net you a source audience in the hundreds, which is thin for a lookalike/predictive seed.

## 3. TikTok lookalike from 400 best customers — 🟢 minimum is real, but "meets the minimum" ≠ "good idea"

Verify the exact current minimum in TikTok's own docs rather than trusting the doc's number, but the bigger issue is upstream of the minimum: list-matching typically drops 40–60% of rows (hashing mismatches, non-TikTok users), so a 400-row CSV could land you _at_ or _under_ the functional floor after matching, not comfortably above it. Push for a bigger, less arbitrarily-curated seed — e.g. top 1,000–2,000 customers by spend rather than a hand-picked "best 400" — for a stabler, higher-quality lookalike.

## 4. "Google Demand Gen lookalike, 100 minimum" — 🔴 this feature doesn't exist as described

Demand Gen has no manually-built "lookalike" audience type with a stated minimum size. It uses **Custom Segments** plus algorithmic **Optimized Targeting/Audience Expansion** off signals you provide (including a Customer Match list) — there's no user-facing lookalike object to size-check against a "100 minimum." This line reads like it was copy-pasted from the old, now-sunset Similar Audiences concept and relabeled for Demand Gen. Ask the agency to point to the exact setting in the Google Ads UI they mean — if they can't, that's your answer.

## 5. Meta: hard-restrict delivery to the lookalike, no leakage — ⚠️ fights the platform, and may not be your best option

Meta has spent two-plus years pushing advertisers toward Advantage+ Audience and away from hard manual restriction — heavy exclusion/restriction is associated with higher CPMs and slower learning, particularly at a mid-size retailer's spend level. If this runs as an Advantage+ Shopping campaign (Meta's current default recommendation for ecommerce), manual hard-locking to one audience with expansion off may not even be the intended workflow — Advantage+ Shopping is built around letting Meta's algorithm find audiences, not fencing them in.

**Ask**: which campaign type are they actually planning (Sales/Advantage+ Shopping vs. classic)? And is the "zero budget leakage" purity worth the reach/cost tradeoff — or should you at least A/B test a locked lookalike against one with expansion on before committing full budget to the restricted version?

## Cross-cutting, before you sign

- **This reads recycled.** Two dead/mislabeled features in a five-item doc isn't a typo pattern — ask directly whether this was written for Calloway or adapted from another client's plan. Their answer tells you a lot about whether to trust the rest of the account setup.
- **Consent chain, all four lists.** Converters, wholesale contacts, best-400 customers — confirm for each that your privacy notice/terms support ad-platform matching use, and that upload happens via a proper hashed/API integration, not a raw CSV passed around.
- **B2B vs. B2C mismatch.** Your wholesale-buyer list is a business-purchasing audience; building consumer-platform lookalikes (TikTok, Meta) off _your best customers_ is fine, but don't let wholesale contacts bleed into consumer-facing lookalikes — different buying motion, likely to misfire.
- **Overlapping seed pools, four platforms.** Converters, wholesale buyers, and best-400 customers likely overlap heavily. Ask how they'll avoid the same people getting hit (and bid against each other) across all four campaigns simultaneously, and whether there's a suppression/frequency plan.
- **Ask for effective audience size, not list size.** For every one of these, get the post-match, post-hash number they expect to actually activate — not the row count of the source file.
