# Verdict: this isn't fatigue

Your own data rules it out. Fatigue's signature is a decaying **top-of-funnel**: rising frequency → falling hook rate → falling CTR, because the same eyeballs have seen the ad enough times to recognize and skip it. Your hook rate hasn't moved and CTR is flat at 1.4%. That means the exact same quality and volume of interested person is landing on your site today as ten days ago. The leak is happening **after the click** — something changed between "arrives on site" and "completes purchase."

Two things changed on exactly that timeline: a checkout flow shipped Sept 2, and a 20%-off code expired "around then." Either one — or both together — is the far more likely explanation than a seven-week-old ad suddenly wearing out. "Minor release" from a dev team is not evidence against this; checkout is exactly where small changes (a broken discount field, an extra step, a mobile layout regression, a payment-method glitch) produce large, invisible-to-QA conversion drops, especially since Meta traffic skews mobile and mobile checkout is the most fragile part of most stacks.

# Diagnose before you touch creative

Run these before spending budget on new creative — they take an afternoon and will tell you definitively where the leak is:

1. **Check CVR site-wide, not just this ad.** Pull CVR for organic, email, and other paid channels over the same 10 days. If it dropped everywhere starting ~Sept 2, that's conclusive: it's checkout or the missing promo, not this ad. This single check is the highest-value thing you can do right now.
2. **Break the funnel into steps.** Landing page → add-to-cart → reached checkout → entered payment → completed. Find which step's completion rate cratered. That tells the dev team exactly where to look, "minor" release or not.
3. **Segment by device.** If the drop is concentrated on mobile, the checkout release is the prime suspect.
4. **Check for a promo-code dependency.** Did the old ad's landing page, past retargeting, or customer expectation still reference the 20%-off code? Pull up checkout abandonment reasons or support tickets mentioning "discount," "code," or "coupon" since expiry. Price-elasticity alone can produce exactly this kind of cliff, independent of any bug.
5. **Look at the shape of the drop, not just the number.** Fatigue decays gradually over days/weeks. A checkout regression or promo expiry produces a step change on a specific date. Plot daily CVR — if there's a cliff right around Sept 2, that's your answer.

**Decision tree:** site-wide CVR also fell → fix checkout/promo, ad is fine, don't touch creative yet. Site-wide CVR held and only this ad's CVR fell → then something ad-specific to this creative-to-landing-page pairing is off, and creative refresh is the right lever.

# Use "fresh creative" as a diagnostic, not just a hail-mary

Since you want a new angle anyway, launch it as a **controlled test**, not a replacement: same landing page and checkout, new ad, running alongside the original. If the new ad's CVR is _also_ stuck around 1.1%, that's independent confirmation the problem is downstream, not creative. If it recovers to ~3%, you've learned something real about this specific creative-to-page match. Either outcome is useful, and you don't burn your still-functioning original ad in the meantime.

# Three fresh angles to test

Your current winner is presumably transformation/results-driven (that's the default for supplement UGC). Diversify rather than copy it — these hit different psychological levers and also hedge against real fatigue setting in over the next few weeks.

**1. "The Label Audit" — proof over promise**
Use this one first if checkout/promo turns out to be the real issue: removing a 20%-off code raises price-scrutiny, and this angle directly rebuilds value perception at full price.

- Hook A: "I read every ingredient on my [pre-workout] out loud. Here's what I found."
- Hook B: "We sent our own product to an independent lab. This is the certificate."
- Body: name the industry problem (proprietary blends hiding real dosages), show your label next to a competitor's, cite third-party testing.
- CTA: "See the full panel" → product page.

**2. "The Plateau Callout" — problem-agitate**
Targets a pain point your results-focused ad likely doesn't lead with.

- Hook A: "If your last rep always feels like your worst rep, it's not your training."
- Hook B: "Spike, then crash. That's not energy, that's a sugar rush."
- Body: name the specific frustration (crash, jitters, bloat, plateau), reframe the cause, position the product as the mechanism-level fix.
- CTA: "Fix your stack."

**3. "Why We Built This" — founder/insider authenticity**
Useful if trust took a hit alongside the price change; a person, not a product shot, rebuilds credibility fast.

- Hook A: "I got tired of supplement brands lying about dosages, so I built the label I wished existed."
- Body: founder-to-camera or UGC, the mission, direct contrast with "bro-science" competitors.
- CTA: direct, no discount-dependent language.

**Test structure:** new campaign, same landing page as the control ad, even budget split, let it run 5–7 days minimum (CVR is a low-volume event — don't call it early). Don't pause the original ad while this runs; you need it as the baseline.

# Bottom line

Don't rebuild the ad yet — run the site-wide CVR and funnel-step checks first (a few hours of work). If they confirm checkout or the promo expiry, that's the fix, and it'll likely recover your 3.2% CVR without any new creative. Launch the new angle in parallel regardless, as both a hedge and a clean diagnostic — its result will tell you definitively whether creative was ever the problem.
