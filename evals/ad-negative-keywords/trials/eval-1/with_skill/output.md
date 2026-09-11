# Negative keywords for Brightpath HR — two different situations, two different rules

You asked for two things. They get different treatment, and I want to flag why up front rather than blur it:

- **The live $12k/month account** — I don't have (and haven't seen) a search term report for it. I'm not going to hand you a list of "junk keywords" invented from a general sense of what B2B payroll software attracts, because I'd have no idea whether any of those terms have actually converted for you. That's exactly the mistake this playbook exists to prevent — a specific term can look like junk in general and be a real closer in your account.
- **The new product line launching Monday** — zero history is the one case where a starter list is legitimate, precisely because there's no real data to ignore. Below is that list, clearly labeled as a pre-launch placeholder to be revised against real queries.

---

## 1. Existing account — what I need before I can give you specific terms

Send me the **search term report** (Google Ads: Insights & reports → Search terms, or pull via API). Once I have it, here's exactly what happens, no back-and-forth needed beyond that:

1. Sort by cost descending, filter to zero conversions.
2. Flag candidates at **15–20 clicks with zero conversions** (tightened to 10–12 if your average CPC is $3+ — tell me your CPC range and I'll set the right gate).
3. Run each candidate through the overblocking check — has it or a close sibling ever converted? Would the match type also catch a real buyer query?
4. Deliver additions with match type, level, evidence, and a do-not-negate list of anything that looked junky but has converted.

To move fast the moment the report lands, answer these (skip any you've already implicitly answered):

- What counts as a conversion, and what's your target CPA?
- Average CPC range on this account?
- Any terms that must never be touched — brand terms, converting themes, or competitor names you deliberately bid on?
- Can you edit account-level shared lists, or only campaign/ad group?
- At $12k/month you're squarely in the weekly-cadence bracket — want me to set this up as a recurring 7–14 day pass rather than a one-off?

I'm not stalling for the sake of it — at $12k/month, a blind list has real odds of silently zeroing out a keyword that's actually paying for itself, and you'd have no way to see that it happened.

---

## 2. New product line campaign — pre-launch starter list (exception, per no-history rule)

**Label: pre-launch starter — review against real queries 7–14 days after launch (Mon Sept 14 → review window Sept 21–28, 2026).**

Scoping note: I've deliberately kept this at **campaign level only** (a negative list attached just to the new campaign), not account level. Account-level would silently apply these unevidenced terms to your existing $12k/month campaigns too — which breaks the same rule I'm applying to part 1. Once your search term report comes in and confirms which of these categories are genuinely universal junk for Brightpath, we can promote the confirmed ones into a proper shared list across both.

All match type = **phrase**, since that's the best waste-blocked-per-risk ratio for a set with no conflict check run yet. In the Google Ads UI, remember it defaults new negatives to **exact** — switch each one to phrase before saving.

**Job seeker**
```
payroll jobs
payroll job
payroll careers
payroll clerk jobs
payroll administrator jobs
payroll specialist salary
payroll specialist salaries
payroll manager salary
payroll internship
payroll intern
```

**DIY / free intent**
```
free payroll software
free payroll calculator
free pay stub template
free pay stub templates
payroll excel template
payroll spreadsheet template
diy payroll
open source payroll software
```

**Informational**
```
what is payroll software
what is payroll
how does payroll software work
how to calculate payroll taxes
payroll process explained
payroll tutorial
payroll for dummies
payroll definition
```

**Wrong segment (B2B tool, not a personal/household payroll tool)**
```
personal payroll
individual payroll calculator
household payroll
```
Flag: if Brightpath's new line ever serves nanny/household employers, drop these — tell me and I'll pull them.

### Flagged, not included — need your call first
Per the taxonomy, competitor and comparison terms are strategy decisions, not automatic junk:
- **Competitor names** (ADP, Gusto, Paychex, Rippling, QuickBooks Payroll, OnPay, Justworks, etc.) — do you want to bid on these deliberately, or block them? I left them out either way; say the word and I'll add them as negatives or confirm you're targeting them.
- **Comparison terms** (`best payroll software`, `payroll software reviews`, `payroll software vs`, `[competitor] alternative`) — often early-funnel research, not junk. Recommend leaving these open until you see whether they convert.

### Open questions that would tighten this list further
- Which countries/regions does the new product line serve? (Wrong-geography negatives need this — I haven't guessed at any.)
- Anything else specific to this product line I should know before Monday (e.g. a name close to an unrelated common term, a vertical you're explicitly not targeting)?

### Before you go live
Check this list against the actual keyword list you've built for the new campaign — I don't have visibility into it, and a phrase negative sitting one word away from a keyword you're bidding on will silently zero it out. That's the single most expensive mistake on this list, and it's on you to catch it since I can't see your ad groups.