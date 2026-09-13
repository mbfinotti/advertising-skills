## Question 1: Who's actually performing better?

You can't answer that from these two numbers — they're not measuring the same thing. Comparing 160% (app) to 4.2x (web) as if they were on a shared scale is the actual mistake here, not either team's execution.

**Why they're not comparable:**

- **Attribution windows differ.** App UA on iOS almost certainly runs through SKAN (SKAdNetwork), which uses short, delayed, and probabilistically-conflated postbacks — it structurally under-reports conversions compared to a web team pulling last-click or even 90-day lookback windows in GA4/Google Ads.
- **"Revenue" isn't the same line.** Web ROAS is very likely gross revenue, last-click, often crediting branded/direct traffic that would have converted anyway. App ROAS from an MMP is usually stricter and closer to incremental.
- **Platform fees are invisible in "ROAS."** In-app purchases pay Apple/Google 15–30%. A 160% gross ROAS nets to roughly 110–135% after store cut — that's the number that should sit next to web's margin-adjusted figure, not the raw 160%.
- **Incentives point in opposite directions.** The app agency is grading itself against a metric (SKAN-based ROAS) that structurally makes them look worse than reality. The web team is grading itself on a metric (last-click ROAS) that structurally makes them look better than reality — brand search and retargeting inflate it for free.

**What to actually do:** don't rank the teams on self-reported ROAS at all. Get both onto one shared, audited definition — same revenue basis (net of store fees and returns), same attribution window, same treatment of brand/retargeting — and run an incrementality check (geo holdout or conversion-lift study) on at least the web side, since that's where inflation risk is highest. Until that exists, "web is winning 4.2x vs 160%" is not a finding, it's a measurement artifact. My prior, given how these two channels typically get reported, is that the gap is real but much smaller than 26x — likely app is closer to break-even-to-modestly-profitable, web is genuinely better but not by 26x.

## Question 2: Do you flip on PMax?

Not as "just another campaign type," and not for "most of the web budget." That framing is the thing to push back on with your boss, not the recommendation itself.

**Why the Google rep's framing is misleading:**

- PMax isn't a campaign type, it's an automated budget/targeting reallocation across Search, Shopping, Display, YouTube, Discover, Gmail and Maps with a black box you can't see into — no placement-level reporting, only partial search-term visibility, minimal exclusion control versus standard Search/Shopping.
- It systematically over-indexes on your _existing_ highest-intent inventory — brand search, cart abandoners, people already in your remarketing lists — because that's what's cheapest to "win." That inflates reported ROAS the same way last-click already inflates your web number, compounding the exact measurement problem in question 1, not fixing it.
- Google's account team is compensated on spend growth and product adoption, not on your incremental profit. A rep pushing "just flip it on" for most of the budget is not a neutral signal.

**What to do instead:**

1. Add brand exclusions / negative brand where the account allows it before ever turning PMax on, so it can't just eat your existing branded conversions.
2. Start with a minority slice of budget (10–20%), not "most of it," and structure it as a controlled test — ideally a geo or new-customer-only holdout — against your current Search/Shopping structure.
3. Judge it on incremental new-customer revenue, not platform-reported ROAS, using the same audited measurement standard you should be building for question 1.
4. Only scale if the lift test shows real incremental revenue, not just reallocated credit from campaigns you already run.

Bottom line: fix the measurement standard before ranking the teams, and treat PMax as a test of incrementality with guardrails, not a budget switch to flip because a rep called it "just another campaign type."
