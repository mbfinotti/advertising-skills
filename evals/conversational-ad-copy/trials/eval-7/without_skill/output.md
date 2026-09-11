## Thornquist feed & review plan

### 🔴 Kill the $25-for-5-star voucher

Rewards conditioned on a positive rating are:
- **Illegal in the US** — FTC's 2024 Reviews & Testimonials Rule bans compensation contingent on star rating or sentiment.
- **A platform ToS violation** — Google, Trustpilot, G2, Capterra, Amazon all prohibit gated/incentivized-for-positive reviews; detection risk is real, spikes in 5-star volume tied to an email blast are exactly the pattern review-fraud detection looks for.
- **Anti-compounding** — a suspended Merchant Center / review-platform account resets you to zero, worse than doing nothing. It also poisons the very signal you're trying to feed the AI model with reviews that get discounted or purged later.

**Compliant swap:** email the same list asking for an honest review, offer a small incentive ($5–10 gift card or a raffle entry) for *submitting any review regardless of rating*, disclosed as such. Legal, keeps the volume goal, doesn't blow up the account.

### ✅ Fix the price field today

Feed says $149/mo, live price is $179/mo. This isn't just a copy problem — a landing-page/feed price mismatch is a **policy violation** on virtually every shopping-feed network (Google Merchant Center, Bing Shopping, etc.) and can get the whole feed suppressed, not just the one listing. This is the single highest-priority, zero-dependency fix you have:

- `price`: `149.00 USD` → `179.00 USD`

Do this before anything else — a suppressed feed makes every other improvement moot.

### ✅ Rewrite the description for what the model can actually use

`"Best-in-class AI-powered price intelligence for winners."` gives the model nothing to extract — it's an unsubstantiated superlative with no entity, no use case, no differentiator. Replace with concrete, structured claims (fill the brackets with real numbers — don't invent them, that's the same trust problem as fake reviews):

> "Automated competitor price tracking for e-commerce brands. Monitor pricing across [N] competitor retailers in real time, get instant alerts on price changes, and set repricing rules to protect margin. Built for DTC and marketplace sellers managing [N]+ SKUs."

Why this works better for an AI-generated ad: it gives the model an audience (e-commerce brands), a mechanism (real-time competitor tracking), a benefit (margin protection), and a scale signal (SKU count) — all things a generative ad engine can recombine into varied ad copy. "Best-in-class" and "winners" are not.

### 🎯 Make it compound, not just this flight

Since the site is frozen and you have no dev time, the feed is your only lever — so make it a durable asset instead of a one-off edit:

1. **Fill every optional feed attribute your platform supports** (`product_highlight`, `product_detail`, `custom_label_0-4`, `additional_image_link`). More structured fields = more raw material for next year's ad variants, not just this quarter's.
2. **Version the feed copy** — keep a changelog of description/attribute edits so next quarter builds on this one instead of starting blank.
3. **Route reviews to durable, indexable surfaces** — G2/Capterra/TrustRadius for a B2B SaaS tool, acquired the compliant way above. These often get pulled into AI answer/shopping engines independently of your feed, so they compound across every future campaign, not just this placement.
4. **Set a quarterly cadence**: each quarter, update `custom_label` fields with a current promo/positioning angle while the core description/attributes stay stable — gives the ad engine fresh material without needing dev or agency involvement.

**This week, in order:** fix price → rewrite description → send compliant (non-contingent) review request → fill remaining feed attributes.