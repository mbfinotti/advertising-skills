This is a bad idea — merging these four buckets will actively hide the information you need to manage spend, and 30 days of account-level ROAS will tell you almost nothing useful. Here's why, in order of severity.

**1. It launders brand search's cheap conversions across the whole account**

Brand search at $9 CPA is capturing people already searching for "Loamside" — mostly demand you generated some other way (word of mouth, other ads, past customers). It converts cheap because there's almost no competition for the click and near-certain purchase intent. Once it's blended into one campaign, its cheap conversions will subsidize the account-level average, making prospecting and non-brand search look far more efficient than they actually are. You could pour more budget into weak prospecting and the account-level number would still look fine, because brand is carrying it.

**2. Automated bidding will chase the cheapest conversions — i.e., it will defund prospecting**

If budget is shared and the algorithm optimizes to a single ROAS/CPA target, it will systematically reallocate spend toward whichever segment converts easiest — brand search and retargeting — because that's the fastest path to hitting the target. Non-brand search ($52 CPA, done acquiring new demand) and prospecting (1.7x ROAS, top-of-funnel) will get starved of budget, even though they're your two channels doing actual customer acquisition. Retargeting's 8.4x ROAS looks great, but it's not creating demand — it's converting people who already showed intent. You can't retarget your way to growth once the retargeting pool (from prospecting/non-brand) dries up.

**3. You lose the ability to see the problem when it happens**

If account-level ROAS drops after 30 days, you won't know whether it's prospecting underperforming, brand traffic softening, retargeting pool shrinking, or seasonality — because there's no line-item to diagnose. If it holds steady or improves, that's equally uninformative: it could just mean the algorithm quietly shifted budget to brand+retargeting while prospecting starved, and you'd only discover that a quarter later when new-customer volume has cratered.

**4. Different funnel stages need different judgment criteria, not one number**

- Brand search: protect it, it's basically free money — but it has a ceiling (limited search volume for your own name).
- Non-brand search: judge on CAC/LTV, not ROAS alone — this is net-new customer acquisition and inherently costs more.
- Prospecting: judge on new-customer volume and downstream LTV, not immediate ROAS —1.7x on a first-touch channel may be perfectly healthy if those customers repeat-purchase.
- Retargeting: judge on incrementality, not raw ROAS. A meaningful share of that 8.4x is people who would have converted anyway (direct traffic, brand search, email) — retargeting often claims credit it didn't earn. Have you run a holdout/incrementality test on it? If not, that 8.4x is likely inflated.

**5. 30 days is too short a window regardless**

Merged or not, 30 days barely covers one purchase cycle for most home goods categories (research → consider → buy, often with a repeat-purchase tail). You won't have enough conversion volume per segment to distinguish signal from noise, and you'll be making a structural decision (should we have kept these separate?) off what could just be a month of algorithm learning-phase volatility.

**What I'd suggest instead:**

- Keep campaigns/budgets separated by intent type (brand, non-brand, prospecting, retargeting) — that structure exists precisely so each can be judged and optimized against the right metric.
- If the consultant's actual goal is reducing manual bid-management overhead, that's better solved with automated bidding _within_ each campaign (tROAS/tCPA per segment) rather than merging the campaigns themselves.
- Set segment-appropriate targets: protect brand's efficiency, evaluate non-brand and prospecting on CAC vs. LTV over a longer window (60–90 days), and run an actual incrementality/holdout test on retargeting before trusting its reported ROAS.
- If you want one combined view for leadership reporting, build it as a blended _dashboard_ metric — not as the actual bid/budget optimization target. Reporting and optimization structure don't have to be the same thing.

I'd push back on this specific recommendation before implementing it — ask the consultant what problem they're trying to solve (usually "too many campaigns to manage manually"), since there's almost always a better fix for that than collapsing acquisition and retention spend into one undifferentiated bucket.
