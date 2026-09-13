# Landing Page Audit — Plumecart paid social LP, response to the 5-point plan

```
traffic    : paid social | model: B2C/DTC skincare
goal       : purchase | downstream truth: revenue
window     : last 30 days | volume: 22,000 sessions, 450 orders | volume floor: CLEARED
             (>1,000 sessions, >30 conversions — real A/B tests are viable; >100 orders/mo clears the second floor too)
economics  : current CVR ≈ 2.05% (450/22,000) — context only, not a target (see below)
inputs     : ad creative: no | page URL/screenshots: no | analytics funnel: no | recordings: no
```

**VERDICT:** I can't audit the page itself — no URL, screenshots, or ad creative were shared, so message-match, above-the-fold layout, and current trust placement are all unrenderable and go under "Could not check." What I _can_ do is evaluate the five-point plan against evidence, because four of its five items are checks this skill runs on every page it sees, and three of them are named failure modes it's built to catch. Here's the straight answer, point by point.

## 1. Countdown timer that resets per visitor

**Don't ship it.** A timer that restarts for each visitor isn't urgency, it's a fabricated deadline — nothing is actually running out. That's called out explicitly as a finding _against_ a page, never a fix for one, and it's also FTC-relevant territory (deceptive scarcity claims). It also risks ad disapproval: Meta and Google both review claims made on the destination page, and a countdown that's provably fake is exactly the kind of thing that gets flagged.
— _Evidence: established policy risk (FTC fake-scarcity enforcement, platform destination policy). Severity: critical. Action: ruled out, not deprioritized._

If there's a _real_ deadline (an actual promo end date, real limited stock), state it plainly with the real date — genuine urgency is fine, resetting urgency isn't.

## 2. Three in-house-drafted testimonials

**Don't post them as customer testimonials.** Fabricated reviews/testimonials are illegal under the FTC's fake-review rule, not just weak practice — this isn't a style note, it's the same severity class as the timer. Posting them opens Plumecart to enforcement risk and, on the ad side, to disclosure violations if they read as endorsements.
— _Evidence: established (FTC rule + ad-platform endorsement disclosure requirements). Severity: critical. Action: ruled out._

What to do instead, and where — since the _placement_ question is worth answering even though the content can't be what you drafted:

- Real testimonials go **at the point of friction**, not bunched in one block: one near the top (addresses "is this legit / for someone like me") close to the hero, one near price/CTA ("worth it?"), one near ingredients or how-it-works if skepticism is the objection there.
- Sources that don't require fabrication: pull existing verified reviews (even a handful) from your review platform or Shopify/Yotpo, request a few UGC clips with a small incentive, use a founder or dermatologist-partner statement (attributed, real), or lead with the guarantee/return policy as objection-handling in place of proof you don't have yet.
- If genuinely nothing usable exists yet, it's fine to under-index on social proof for now rather than manufacture it — a page with no testimonials outperforms a page with fake ones the moment anyone checks.

## 3. Red CTA "because red converts better"

**Refuse the premise, keep the question.** "Red beats green" is refuted folklore — no hue wins universally; what matters is contrast against its surroundings (WCAG AA: 4.5:1 normal text / 3:1 large text) and prominence relative to competing elements on the screen.
— _Evidence: established research (contrast > hue). Severity: minor as stated, but worth checking properly._

**Fix now (evidence: opinion, pending page render):** check the current CTA's contrast ratio and whether it's visually the loudest element above the fold. If it already passes contrast and stands out, changing the color buys nothing. If you want to change it anyway, that's a legitimate **Test, don't guess** item — you clear the volume floor, so a real test is viable: pick two colors that both pass contrast, run it a full business cycle, judge on add-to-cart or purchase rate, no early stopping.

## 4. Cutting nearly all body copy for "8-second attention spans"

**The premise is broken.** The 8-second/goldfish attention span has an untraceable citation chain (the BBC's own 2017 investigation couldn't source it) — refuse it outright. What's actually verified: visual first impressions form in ~50ms (that's about visual appeal, not "decide to buy in 50ms"), and ~57% of viewing time still lands above the fold — meaning people _do_ scroll, so "shorten to nothing" and "the fold is dead" are both wrong, not just one of them.
— _Evidence: established research (Lindgaard 2006, NN/g 2018) vs. folklore with a debunked citation. Severity: major if shipped — you'd be cutting proof and objection-handling copy on the theory nobody reads past line one._

**Fix now:** front-load the message (put the outcome/promise in the first sentence, benefit-led not feature-led) rather than deleting the copy that follows it. Length should match offer complexity and traffic temperature — cold paid-social traffic for a skincare product usually still needs the problem named before the product, which needs _some_ copy. Cut redundant lines, don't cut the objection-handling ones.

## 5. Expected percentage lift for the deck

**I can't give you one, and no honest audit will.** Most tested changes don't win at all — 10–33% of experiments improve their target metric (Kohavi's Microsoft/Google data; Optimizely's 127,000-experiment corpus lands at 12%) — and the ones that do "win" typically overstate their true effect on replication (winner's curse). A number in the deck would be a causal claim with zero experiment behind it; that's the one thing this process is built never to produce.

What actually belongs in the deck instead:

- A **per-fix prediction with direction**, not magnitude: "we expect the land→engage rate to move up" — logged now, checked against the real funnel after it ships.
- Unbounce's benchmark median (paid social ≈12% CVR, vendor dataset, self-selected pages) as **context for where you sit today (2.05%)**, explicitly labeled as industry context, not a projected lift.
- A re-check date, one full business cycle out, where the actual movement — not a promise — becomes the number you report back.

## RULED OUT

- Countdown timer (resets per visitor) — fabricated urgency, FTC/platform-policy exposure.
- In-house-drafted testimonials as posted — fake-review rule violation.
- Wholesale body-copy removal — based on a folklore citation with no traceable source.
- A stated percentage lift for the deck — no experiment exists to back it.

## TEST, DON'T GUESS

- CTA color change (once contrast/prominence is confirmed as the actual gap) — judged on add-to-cart or purchase rate, full business cycle, no early stopping. You clear the volume floor for this.

## COULD NOT CHECK

- Message match (verbal/visual/offer/geo) — no ad creative or page URL supplied.
- Above-the-fold layout, mobile viewport, current CTA contrast, current testimonial placement, form/checkout friction, speed (Core Web Vitals), accessibility — no page to render.
- Whether the 2.05% CVR reflects a real page problem vs. an upstream (creative fatigue, tracking, targeting) issue — no funnel-by-device data or CTR/frequency trend supplied.

Send the live URL (or desktop + mobile screenshots) plus the actual ad creative and I can run the full click-path and heuristic checks (A–J) against the real page rather than against the plan alone.

## RE-CHECK

- Once shipped: message-match/CTA/copy changes → land→engage rate; genuine urgency or proof additions → engage→purchase rate. Re-check one full business cycle after launch, same attribution window as this baseline.
