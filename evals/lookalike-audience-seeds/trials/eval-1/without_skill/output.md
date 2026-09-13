Two assumptions in your framing need a correction before you build anything, then here's the setup.

## Correct the premise first

**1. "Lookalike Audiences" as a named LinkedIn product doesn't exist anymore.** LinkedIn sunset Lookalike Audiences and folded that capability into **Predictive Audiences**, built on top of a **Matched Audience** source list (contact list or company list) you upload in Campaign Manager. Mechanically similar idea, different pipeline — worth knowing before you go hunting for a "Lookalike" button that's been renamed/moved.

**2. 700 uploaded rows ≠ 700 matched LinkedIn members.** The 300 minimum applies to the _matched_ audience LinkedIn can actually resolve against real profiles, not your CSV row count. Work-email-to-LinkedIn-profile match rates for B2B contact lists typically land somewhere in the 40–65% range depending on how clean the emails are and whether you supply extra match keys (name, company, company domain). At the low end of that range, 700 rows could resolve to ~280 matched profiles — under the floor, not comfortably above it. **Don't treat 700 as a safe cushion. Upload it and check the actual matched count in Campaign Manager before you plan campaigns around it.** If it comes in light, add first name, last name, and company domain columns to the upload — multiple match keys measurably lift match rate versus email alone.

**3. Don't pad the seed with the 6,000 MQLs. This is the part most likely to quietly wreck the whole exercise.** A predictive/lookalike model learns "what does a person who converts look like" from the statistical signature of your seed list. Closed-won at $42K ACV has a very specific signature: right company size, right industry, right buying-committee seniority, right budget authority. MQLs are, definitionally, people who clicked a form — most never got near a champion role or a signed contract. Blend 700 real buyers into 6,700 rows that are 90% "generic top-of-funnel lead," and the model optimizes toward finding more MQLs, not more $42K customers. You'd be diluting your one genuinely high-signal asset to solve a volume problem you don't actually have yet — check the matched count first.

If you do end up short on volume after matching, better levers than MQLs, in order of preference:

- Add **late-stage lost opportunities** (proposal/contract stage, lost on timing/budget, not on fit) — they carry buyer-committee signal even without a signed deal.
- Add **expansion/upsell closed-won from existing accounts**, if not already in the 700.
- Switch to a **company-based** seed instead of person-based (see below) — company lists need far fewer rows to be useful than contact lists.
- If truly stuck, run it at 700 and accept a slightly less precise model rather than corrupting the seed.

## The setup I'd actually run

**Step 0 — GDPR check, before anything touches LinkedIn.** You're a French company uploading personal data (names + work emails) to a US ad platform for profiling/targeting purposes. This is a distinct processing activity from "closed-won contact stored in CRM" — confirm your legal basis (legitimate interest assessment is the usual route for B2B, but it must be documented and cover _this_ use), that your privacy notice mentions ad-platform sharing, and that LinkedIn's DPA/SCCs are in place on your ads account. Don't skip this because the emails are "just work emails" — work email + full name is still personal data under GDPR.

**Step 1 — Build two seed lists, not one:**

- **Contact list**: the 700 closed-won, work emails + first name + last name + company name/domain columns for match-rate lift.
- **Company list**: dedupe the 700 down to unique closed-won _accounts_ (probably 300–500 companies given multi-contact deals) and upload their domains as a separate Matched Audience.

Given your ACV ($42K, clearly mid-market/enterprise, multi-stakeholder deals) I'd actually bet the **company-list Predictive Audience outperforms the person-list one**. Company-fit signal (industry, size, tech stack, growth stage) is more stable at n≈300–500 accounts than person-level signal is at n=700 individuals, and you then layer LinkedIn's own seniority/function targeting (VP+ Data/Analytics/Eng, whatever your actual buying committee is) on top to pick the right people _within_ those predicted-similar companies. That combination — predicted company fit × explicit persona targeting — is usually tighter than a pure contact-based lookalike for this deal size.

**Step 2 — Campaign Manager → Account Assets → Audiences → Create Audience → Matched Audiences.** Upload both lists. Wait the 24–48h processing window, then check matched size on each before doing anything else.

**Step 3 — Build the Predictive Audience** from whichever seed(s) clear the eligibility bar (confirm the current minimum in-app — it's moved before and I'd rather you see the live number than trust a figure from me that may be stale). Predictive Audiences typically also want the seed list to have been used in an active campaign with some conversion history, not just sit static — if Campaign Manager tells you that, run the raw matched list as a retargeting/ABM campaign for a few weeks first to generate the signal it wants, then build predictive on top.

**Step 4 — Stack firmographic filters on top of the predictive audience** (company size band, industry, seniority) rather than trusting the model at full reach. Predictive audiences tend to over-expand if left unconstrained, which is fine for demand-gen volume plays and bad for a $42K ACV product with a narrow real buyer pool.

**Step 5 — Launch as its own campaign, held out against your current targeting**, and judge it on **pipeline-stage conversion (SQL/opportunity rate), not CTR or even lead volume**. At your ACV, a lookalike that produces cheap junk leads is worse than no lookalike — the whole point is buyer-shaped traffic, and clicks don't tell you that.

**Step 6 — Refresh the seed quarterly** as closed-won accumulates. At 700 total, each new quarter's crop meaningfully shifts the seed's centroid — don't let it go stale for a year.

**Bottom line on your two questions:** verify the _matched_ count before trusting 700 as your cushion, and don't touch the MQL list for this — it solves the wrong problem by breaking the one thing that makes a lookalike worth building.
