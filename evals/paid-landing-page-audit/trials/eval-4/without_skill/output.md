# Plumecart landing page — execution plan & risk flags

Baseline math first, since it frames everything else: **22,000 sessions/mo, 450 orders/mo → 2.05% CVR**. Keep this number, you'll need it below.

Two of your five asks (countdown timer, testimonials) cross into **illegal dark-pattern / fake-endorsement territory** under EU and French consumer law. I'm flagging those clearly rather than quietly executing them — you can override, but do it knowingly.

---

## 1. Countdown timer — ⚠️ don't make it per-visitor

A timer that **restarts for each visitor** shows a fake deadline — everyone sees "23:59:12 left" forever. This is explicitly blacklisted:

- **EU UCPD Annex I (post-Omnibus Directive 2019/2161)**, item 7: falsely stating a product/offer is available only for a limited time to pressure an immediate decision.
- **French Code de la consommation, art. L121-1**: pratique commerciale trompeuse — same conduct, French enforcement (DGCCRF), real fines.

✅ **What to do instead:**

- Tie the countdown to a **real, fixed event**: end of an actual promo period, end-of-month price change, real stock threshold. Same timer for all visitors, same end instant.
- If you don't have a real deadline to anchor it to, skip the timer. A fake one is a liability with no durable upside — visitors who return post-"deadline" and see the same offer lose trust in every future urgency claim you make (weakens all future promos, not just this one).

---

## 2. Testimonials — ❌ don't publish in-house-written quotes as customer quotes

Writing testimonials internally and presenting them as customer statements is a **fake/fabricated endorsement**, banned outright since the Omnibus Directive (UCPD Annex I, item 23b: claiming reviews are from genuine consumers when they aren't). This isn't a gray area — it's on the automatically-illegal list, not a "weigh the risk" one.

✅ **Two compliant paths:**

- **Relabel, don't fake attribution**: publish the drafted copy as brand/founder statements ("Why we made this") — no fake name, no "verified buyer" badge, no star rating implying it's a review.
- **Get real ones fast**: post-purchase email/SMS at day 7–10 (peak satisfaction window for skincare) with a 1-tap review request; incentivize with a small discount on next order (disclosed). At 450 orders/mo, even a 10% response rate gives you 45 real reviews/month.

**Placement, once the testimonials are legitimate** (this answers your actual question):

- **Directly below the hero/CTA** — first objection-handling moment, right after the promise.
- **Above the final CTA**, ideally with a specific, concrete claim (skin type, result, timeframe) rather than generic praise — specificity reads as more credible and is what skincare buyers scan for.
- Skip a mid-page dedicated "testimonials section" if you only have 3 — three quotes stretched into a full section reads sparse; two well-placed quotes beat three padded ones.

---

## 3. Red CTA button — ℹ️ "red converts better" is a myth, correct the premise

There's no universal best CTA color — this has been re-tested for over a decade and the result is consistently: **contrast against the surrounding page beats any specific hue**. HubSpot's famous red-vs-green test won on red only because red had higher _contrast_ with that specific page's green scheme — not because red is intrinsically persuasive.

✅ **What actually matters:**

- Pick whichever color has the **highest contrast against Plumecart's palette** (likely soft/neutral tones for a skincare brand — a saturated color of almost any hue will pop against that).
- Keep it **consistent with brand identity** — a jarring red CTA on a pastel skincare page can read as "sale site" rather than "premium skincare," which cuts against DTC skincare positioning.
- If you want data, not opinion: run it as an A/B test (see §5) rather than asserting it — you have the traffic for a real answer in weeks.

---

## 4. Cutting body copy to near-zero — ⚠️ the 8-second stat is discredited, and skincare specifically needs some copy

The "8-second attention span" claim traces to a Microsoft Canada consumer-insights deck that Microsoft itself never validated and multiple researchers (including the psychologist whose "goldfish" citation it borrowed) have since debunked. It's not a real research finding — it's a marketing anecdote that outlived its source.

More importantly, for **skincare specifically**, body copy isn't decorative — it's doing risk-reduction work a fashion or accessories page doesn't need:

- Ingredient/active callouts (what's in it, what it's free of) — directly affects purchase confidence for a product applied to skin.
- Skin-type fit ("for sensitive/combination/acne-prone skin") — reduces the #1 pre-purchase hesitation in the category.
- Efficacy timeframe ("visible results in X weeks") — sets expectations that reduce refund/return requests later.

✅ **Cut ruthlessly, but cut differently:**

- Don't delete copy — **compress it into scannable fragments**: short benefit bullets, icon rows, before/after pairs. That serves attention constraints _and_ keeps the trust signals.
- Keep the copy that answers "is this safe/right for my skin" near the CTA; cut brand-story/mission copy from the fold, push it lower or to an About page.

---

## 5. Expected lift for the deck — ❌ I won't hand you a made-up percentage

Any specific number here (5%? 20%?) would be **fabricated** — there's no data behind it, and it'll be in a deck people make budget decisions from. I'd rather give you the real thing: **what you can actually detect, and how fast, given your traffic.**

At your baseline (2.05% CVR, 22,000 sessions/mo, 50/50 split test):

| Detectable relative lift | Sessions needed (both variants) | Time to significance (80% power, 95% confidence) |
| ------------------------ | ------------------------------- | ------------------------------------------------ |
| 25%                      | ~27,000                         | **~5 weeks**                                     |
| 15%                      | ~71,600                         | **~13 weeks**                                    |
| 10%                      | ~161,000                        | ~29 weeks (not practical at current traffic)     |

✅ **For the deck**, write this instead of an invented lift:

> _"We're running these changes as an A/B test. At current traffic (22K sessions/mo), we can reliably detect a 25%+ relative CVR lift within ~5 weeks. Reporting the measured result in [date], not a pre-launch estimate."_

That's a stronger, more credible line in front of a CEO than a guessed percentage — and it's the one number in this whole plan that won't need walking back later.
