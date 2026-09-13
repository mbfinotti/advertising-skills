No web access granted, so this is based on my own knowledge of platform policy — I'll flag where you should double-check with Meta/Google support and your compliance counsel before launch, since ad policy details shift.

## The plan as described won't run on Meta. Fix that first.

Personal loans fall under Meta's **Special Ad Category: Credit**. Every credit-access campaign must be flagged as such, and that flag strips out most of what you just described:

- **No age targeting.** You cannot target 25-45. Special Ad Category campaigns are locked to the broadest available age range (18+, no upper bound).
- **No ZIP-code / pinpoint geo targeting.** You're restricted to broad radius targeting (Meta enforces a minimum ~15-mile radius around a point) — you cannot hand-pick a list of high-income ZIP codes.
- **No Lookalike Audiences.** Meta discontinued Lookalike/Special Ad Audiences for Special Ad Categories (Credit, Housing, Employment) following the 2022 DOJ/HUD settlement. Your 1% lookalike from the best-customer list is not available.
- **No homeowner/renter targeting, no exclusions based on it.** Detailed-targeting options tied to housing status, income proxies, and similar attributes are removed from the picker entirely for these campaigns.
- **Custom Audience upload still works, but only for suppression** — e.g., exclude existing customers so you don't waste spend re-targeting people who already have a loan with you. You cannot use it as a lookalike seed.

This isn't a technicality to route around — the underlying reason is fair-lending law, not just a Meta rule. Stacking "high-income ZIP" + "homeowner" + "exclude renters" for a credit product is close to a textbook redlining/disparate-impact pattern under ECOA/Reg B, regardless of which ad platform enforces it. I'd get this specific targeting concept signed off by counsel before it goes anywhere, Meta or not — Meta blocking it in-product is actually doing you a favor here.

## Google has its own gate, but different in kind

Personal loan advertisers must go through **Google's Personal Loans advertiser certification** (state license info, entity verification) before ads serve in the US — start this now, it's not instant. Google also bans short-term/high-APR loan products outright (originally aimed at payday lending); a standard installment personal loan should qualify once certified, but confirm BrightHarbor's APR/term structure clears the threshold.

Google doesn't impose Meta's blanket ban on age/gender/geo targeting for credit ads, so **Search is where your original targeting instinct (income-correlated geography, life-stage intent) actually survives** — via geo-bid-adjustment by ZIP/DMA, income-tier household targeting on Display/YouTube (available, less restricted than Meta), and pure keyword intent on Search, which needs no demographic targeting at all to work.

## Recommended $40K/month mix

**Google Search — 55% (~$22K)**
Primary channel. Bottom-funnel intent ("personal loan Austin," "debt consolidation loan," "loan for home improvement") converts on its own without needing the demographic targeting Meta just took off the table. Run Austin-metro geo + income-tier household targeting where available, RLSA for site visitors who didn't convert. This is where certification effort should go first — nothing here launches until that clears.

**Meta — 30% (~$12K)**
Reframe its job: broad-reach prospecting and retargeting, not precision demographic sniping. Broad Special Ad Category audience (18+, Austin metro radius) + strong creative and a landing-page/application-flow that does the real qualifying (soft-pull pre-qual, income/homeownership questions asked post-click, not pre-targeted). Use the customer list only to suppress existing customers. Expect Meta to underperform Search on a pure loan-application CPA basis; it's earning its keep on volume and retargeting warm traffic into the funnel, not on landing the "right" 25-45 homeowner directly.

**Test / retargeting reserve — 15% (~$6K)**
Google Display + YouTube retargeting for site visitors who didn't finish an application, and headroom to shift toward whichever of Search/Meta is actually clearing your target CPA once real numbers come in for 4-6 weeks.

## Before you spend a dollar

1. Get the ZIP/homeowner/income targeting concept reviewed by fair-lending counsel — not a Meta workaround question, a legal one, and it touches your Google geo/income targeting too.
2. Start Google's personal loan advertiser certification this week — it's the longer pole.
3. Rebuild the Meta campaign brief around broad Special Ad Category targeting + creative/landing-page qualification instead of the ZIP/homeowner plan — the current brief won't get past Ads Manager setup.
4. Re-confirm current Meta/Google policy specifics directly in Ads Manager / Google's policy center before launch — both platforms revise these periodically and I don't have live access to verify today's exact wording.
