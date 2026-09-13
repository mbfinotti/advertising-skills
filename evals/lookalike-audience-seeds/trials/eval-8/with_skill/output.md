## Pushback memo: Calloway Cycles lookalike/similar-audience plan

This reads like a template that predates two platform deprecations and cherry-picks the looser of two conflicting minimums twice. Five items to send back before signing off.

### 1. "Google Similar Audiences" — doesn't exist

Google removed Similar Audiences from all ad groups and campaigns on **August 1, 2023** (new segments stopped generating in May 2023). There's nothing to build. Ask the agency to name the actual target: your converter list now works as a **signal** feeding Smart/Performance Max bidding, or as the seed for a **Demand Gen lookalike** (see #4). If they meant the latter, this item and item 4 are the same thing double-counted.

### 2. "LinkedIn Lookalike Audiences" — also doesn't exist

Sunset **February 29, 2024**, replaced by **Predictive Audiences** (300-matched minimum, max 30 per ad account). Get the doc corrected to that name. Separately, check the math: 2,400 work-email contacts at LinkedIn's typical 30–40% match rate is ~720–960 matched — clears 300, but with little cushion, and LinkedIn's own recommendation for a contact list is 10,000+ rows to _reliably_ clear that floor. Ask for the actual expected match rate (not the row count) before trusting this one. Also confirm these 2,400 are closed-won wholesale accounts, not a raw MQL/contact export — seed quality depends on it.

### 3. TikTok — 400 customers will not clear the real floor

TikTok's Help Center floor is **1,000 matched**; the "100" the doc cites is from a lower-authority FAQ page mentioned alongside it. Standard practice is to plan against the stricter of two conflicting platform numbers, not the friendlier one. Even optimistically matching 400 rows at an 80% rate yields ~320 matched people — under 1,000 either way. This lookalike will fail to build or won't serve. Push back hard: either grow the seed toward TikTok's practitioner-recommended 10,000, or drop this channel from the plan.

### 4. Google Demand Gen lookalike — same cherry-pick, same problem

Google's API docs put the Demand Gen lookalike floor at **1,000 active matched**; the Help Center's "100" is the looser, lower-authority figure, exactly like TikTok. Same rule applies: plan against 1,000. Ask what seed feeds this one and whether it can actually clear 1,000 matched — if it's the same converter list as item 1, that's fine in principle, but the doc needs to state the real floor and show the match-count math, not assert "100, so that's fine."

### 5. Meta "hard-restrict delivery to the lookalike" — not a real guarantee

On Meta, **inclusion audiences are suggestions, not hard rules** — Advantage+ delivery can and does serve outside a lookalike it's been pointed at. Detailed-targeting exclusions were removed in March 2025; the only thing that still hard-blocks delivery is a **custom-audience exclusion** under Audience Controls. So "no budget leaks outside it" isn't achievable by restricting inclusion — it's achievable by adding the _unwanted_ segments (e.g., existing customers, wholesale accounts, geos you don't serve) as an **exclusion audience**, which Meta does enforce. Ask the agency to reframe this as an exclusion strategy, not a delivery restriction promise they can't keep.

### Two things missing across all four uploads

- **No privacy/consent gate anywhere in the doc.** Uploading the converter list, the 2,400 wholesale contacts, and the 400 customers to three separate ad platforms each needs a documented lawful basis — hashing doesn't exempt you (Munich Higher Administrative Court, 2018, on Meta customer-list audiences), and Meta value-based audiences need a separate terms acceptance. Ask who confirmed this and where opt-outs/deletions are enforced before export.
- **No negative-selection pass mentioned.** Since Calloway sells both B2C and wholesale, the Google/TikTok/Meta seeds need wholesale accounts _stripped out_ (bulk buyers are a different behavioral profile and will dilute the consumer signal) — while the LinkedIn seed is correctly built _from_ those same wholesale accounts. The doc doesn't say this separation was made deliberately; confirm it wasn't just one undifferentiated customer export split three ways by convenience.

**Bottom line:** two of five tactics are built on deprecated products, two of the remaining three cite the wrong side of a documented floor dispute, and the fifth promises a delivery guarantee Meta's targeting model doesn't honor. Worth asking whether this was reused from a pre-2024 client before agreeing to a timeline built on it.
