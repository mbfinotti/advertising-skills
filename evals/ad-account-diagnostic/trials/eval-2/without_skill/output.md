## The real problem probably isn't targeting breadth — it's what you're optimizing to

Before touching audience settings, sit with this pattern: CPL fell 28% and lead-to-SQL rate fell from 12% to 4% **in the same campaigns you shifted budget into**. That's not two unrelated facts — it's one fact. When you optimize a bidding algorithm (Google Smart Bidding, LinkedIn's auction) to a cheap, easy-to-hit event, and then feed it more budget, it will find you *more of the cheapest way to hit that event*. A gated whitepaper fill is a very cheap event to game — by the algorithm, not by fraud. It just finds people who'll trade an email for a PDF, which correlates weakly with "will buy data-quality software."

**"Reconciles fine against the CRM" only tells you tracking is accurate — it says nothing about quality.** You've confirmed that leads counted by the ad platform = leads landing in the CRM. You have not confirmed those leads are the right people. Those are separate questions, and it's easy to read the first as reassurance on the second. It isn't.

So the hypothesis to test first isn't "audiences are too broad," it's: **the campaigns are optimizing to a proxy metric (form fill) that has decoupled from the outcome you actually care about (SQL), and cheaper CPL is the symptom of that decoupling, not a win.**

## Audit checklist — run this before changing any targeting

I don't have a connector into your Google Ads / LinkedIn Ads accounts in this session, so I can't pull the numbers myself — here's exactly what to pull and what each result would tell you.

**1. Isolate where the collapse lives**
- Break lead-to-SQL rate by platform, campaign, ad group/audience, and — for LinkedIn — placement (LinkedIn feed vs. **LinkedIn Audience Network**). LAN placements are notoriously cheap and notoriously low-intent; if LAN is on and got more budget, that alone could explain this.
- For Google: pull the **placement/network report**. If budget shifted toward Display, Discovery, or Search Partners (common side-effect of Performance Max or loosened Search campaigns), that's cheap junk traffic wearing a "lead" costume.
- Cut by firmographics your CRM should already have (company size, industry, job title/seniority). Compare last quarter's SQL-converting leads' profile to this quarter's non-converting ones. A seniority/title shift (e.g., fewer "VP/Director/Head of" and more individual contributors, students, or job titles outside your ICP) is the single most common cause of exactly this symptom.

**2. Check what changed mechanically, not just budget**
- Did the bid strategy change when budget shifted (e.g., to Maximize Conversions / a lower cost cap)? A cost-cap that's too aggressive is a classic cause of a CPL drop paired with quality collapse — same mechanism as above, just at the bidding-strategy level.
- LinkedIn: is **Audience Expansion** enabled on the campaigns that got the extra budget? It explicitly lets LinkedIn serve outside your defined targeting criteria to hit volume/cost goals.
- Any recent audience list changes — did an account manager (yours or an agency's) "refresh" targeting in a way that dropped exclusions (e.g., students, competitors, existing customers, job-seekers)?

**3. Sanity-check for low-effort/bot-adjacent fills**
- Form completion time (near-instant fills are suspicious), disposable/free email domains, mismatched IP-geo vs. stated company location, and duplicate/near-duplicate submissions. Doesn't need to be outright fraud to matter — "filled the form in 4 seconds to get the PDF" people convert to SQL at ~0%.

**4. Check the content-market fit of the whitepaper itself**
- If the campaigns that got more budget point at a broader-appeal or more "generic" gated asset than the ones that kept 12% SQL rate, the creative/offer is attracting researchers, students, and adjacent-but-wrong roles — not fixable by narrowing geography or company size alone.

## Why "just tighten targeting" will likely disappoint you

Tightening audiences (narrower titles, smaller company-size band, exclude students/junior roles, add negative keywords, turn off LAN/Display) is a reasonable *tactical* move once you know where the junk is coming from — do it as part of the fix, not instead of the real fix. But if the underlying issue is that you're bidding an algorithm toward "cheapest form fill," narrowing the audience just makes the same algorithm find the cheapest form-fillers *inside* a smaller pool. CPL will likely creep back up, and there's no guarantee SQL rate recovers, because the optimization target — not the targeting — is what's misaligned with revenue.

## The fix that actually addresses the root cause

1. **Stop optimizing to whitepaper fill as the terminal event.** It's fine as a mid-funnel signal, not as what you tell the algorithm to maximize.
2. **Feed SQL (or even closed-won) data back into the platforms via offline conversion imports** — Google Ads offline conversions, LinkedIn Conversions API — so Smart Bidding and LinkedIn's auction optimize toward people who actually become SQLs, not people who download PDFs. Expect a lag (your sales cycle) before the algorithms have enough signal; that's normal and worth the patience.
3. **Add 2–3 qualifying fields to the gated form** (company size band, role, or a use-case dropdown) and use obviously-disqualifying answers as a negative signal you feed back — this pre-filters before the lead ever reaches sales, and gives you a faster proxy than waiting for SQL data to accumulate.
4. **Move to value-based bidding once you have SQL/opportunity value flowing back**, so the algorithm isn't just chasing conversion *count* but conversion *value*.
5. **Only then** tighten audience settings — using what the audit in step 1–3 above actually shows (kill LAN if it's the culprit, fix seniority/title targeting, exclude the network placements eating budget) rather than a blanket "make audiences narrower."

## Fix the dashboard so this doesn't happen again

CPL alone is a vanity metric once the conversion event is this cheap to game. Add **cost per SQL** and **SQL rate** as first-class dashboard metrics next to CPL, per campaign — not just reconciled in the CRM after the fact once a quarter. If cost per SQL had been visible in real time, this quarter's budget shift would have shown its damage within days, not after a full quarter of spend.