This is a data-integrity and stakeholder-management problem wearing a data-analysis costume. Here's my advice, straight:

## Don't present it as reconciled. Present it as reconciled *to 66%*, and say so on the slide.

Fabricating certainty in a board deck is the single fastest way to lose credibility as the first data hire. The first time anyone — a board member, an auditor, next quarter's you — finds the 470-conversion hole after you said "fully reconciled," every number you ever present afterward gets re-checked. You're trading one uncomfortable slide now for a permanent discount on your credibility. That trade is never worth it.

## On the ROAS-of-4.1 / "Google as source of truth" request specifically

This is the bigger issue, and it's separate from the reconciliation question. Push back on it, but with data, not opinion:

- **Google Ads is not a neutral measurement system — it's an interested party.** Google's own attribution counts view-through conversions, uses its own lookback windows, and has every incentive (algorithmic and commercial) to attribute credit generously to itself. Using the ad platform that sold the clicks as your "source of truth" for whether those clicks worked is a structural conflict of interest, not a data-quality choice.
- **"Most complete data" ≠ "most accurate data."** Google sees more *of the internet*, but your order system sees more *of your actual revenue* — it's the one system tied to money that actually landed in the bank. Completeness and accuracy are different axes; the CMO is conflating them.
- **Standardizing reporting on Google Ads numbers going forward locks in the inflation.** If the platform overstates by ~10-25% (940 of 1,410 conversions, i.e. ~67%, are explainable by window/view-through/refund effects — that's a real, structural overstatement, not noise), every future budget decision made against that number will over-credit Google spend relative to other channels, which then gets more budget, which generates more (inflated) reported conversions — a self-reinforcing loop that misallocates spend.

**Recommendation: order system (or a blended MMM/incrementality view, if you have the maturity for it) is source of truth for revenue and ROAS. Google Ads is a diagnostic/optimization tool, not a P&L input.** This is standard practice at any B2C company past seed stage — say so, it's not a radical position.

## How to build the slide

**One slide, three numbers, one sentence of honesty:**

| | Conversions |
|---|---|
| Gross gap (Google vs. order system) | 1,410 |
| Explained (window differences, view-through, refunds) | 940 (67%) |
| Unexplained — under investigation | 470 (33%) |

Then one line: *"Remaining gap being investigated; likely candidates are [your best hypotheses — e.g. cross-device attribution, ad blockers/consent-mode data loss, coupon/affiliate double-count, direct-to-Google-Ads misattribution of organic]. Update at next board meeting."*

This is a **stronger** slide than "fully reconciled," not a weaker one, because:
- It shows you found and quantified a real discrepancy the CMO wasn't tracking.
- It shows you have a methodology (explainable-cause bucketing) rather than a vibe.
- A board that's seen a few of these decks will trust "67% explained, actively chasing the rest" far more than a suspiciously clean "100% reconciled" — the latter reads as either not-looked-hard-enough or massaged.
- It gives you a legitimate reason to own the "source of truth" conversation instead of just complying with the CMO's ask.

## Before the meeting

1. **Talk to the CMO privately first, not in the room.** Walk them through the 940/470 split and the conflict-of-interest argument on Google-as-source-of-truth. Give them the chance to co-present the correction rather than being surprised by it live — you want an ally, not an adversary, on stage.
2. **Spend a few hours on the 470 before the deck is final if you can.** Common suspects worth ruling out fast: consent-mode/cookie-loss under- or over-counting, coupon-code or affiliate-channel double-attribution, test/internal orders, refund timing mismatches beyond what you already bucketed, and multi-touch households where Google credits a device Google itself introduced but your order system attributes to a different last-touch. Even shaving 470 down to 200 "unexplained" strengthens the slide further — but don't let this become a rabbit hole that delays the deck; "investigating, next update in N weeks" is a fine place to land.
3. **Propose a forward-looking fix, not just a mea culpa**: recommend the company adopt order-system-of-record (or incrementality testing) as the standard, with Google Ads numbers shown alongside as "platform-reported" for context. That reframes the whole conversation from "gotcha, the CMO's number is wrong" to "here's how we get more reliable numbers going forward" — which is the actual job.