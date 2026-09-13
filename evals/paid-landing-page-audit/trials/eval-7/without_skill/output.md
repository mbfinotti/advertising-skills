# Marrowfield Goods — /copper-set Funnel Audit

## 🎯 Bottom line

CPA is 66% over target ($58 vs $35) because the funnel has three compounding leaks, not one: a broken ad-to-page promise, two hidden-cost reveals late in the journey, and a mobile-first hero that likely isn't optimized for the 81% of traffic that's mobile. None of this can be confirmed with certainty because there's no session recording or heatmap data — that gap is itself a finding, not just a caveat.

## 📊 The numbers

- Conversion rate: 380 / 46,000 = **0.83%** (DTC cold-traffic benchmark is typically 1.5–2.5%; you're roughly half that)
- Spend: 380 × $58 = **$22,040** over 28 days
- To hit $35 CPA on that same spend, you'd need **630 purchases** — a **+66% relative lift in conversion rate**, all else equal
- 81% of sessions _and_ spend is mobile, but you have no mobile-vs-desktop performance split. **This is your first fix, not a finding** — you're flying blind on 4 in 5 dollars.

## 🔴 Critical findings

**1. Message-match failure between ad and landing page**
The ad sells a specific, tangible thing: _5-piece copper set, 35% off, this week, with a chef searing steak on camera_. The landing page delivers an abstract moodboard with no product visible and a headline ("Cookware, reimagined") that answers a question nobody asked. A user who clicked to buy a discounted copper set lands somewhere that doesn't confirm they're even in the right place. This is the single highest-leverage fix — cold Meta traffic has near-zero patience for re-orienting.

**2. CTA mismatch breaks the scent trail**
Ad CTA: "Shop the set." Page CTA: "Explore our collections." These are different intents — one is transactional, one is browsing. Every pixel of the page should reinforce what the ad promised; instead it downgrades the visitor's intent for them.

**3. Price hidden until a second click**
No price on the landing page means every visitor must click through to a PDP just to learn if the "35% off" claim is even relevant to them. Each extra click is a drop-off point you're not measuring.

**4. Shipping cost surprise at payment**
Shipping revealed only at the payment step is the #1 documented cause of cart abandonment in ecommerce (Baymard Institute puts "unexpected costs" ahead of every other abandonment reason). You're very likely paying to acquire clicks that convert into carts, then losing them for free at the worst possible moment — after the customer has already done the work of getting to checkout.

**5. No behavioral instrumentation**
Zero session recordings or heatmaps means every conclusion above is a hypothesis, not a diagnosis. You can't tell whether people are bouncing on the hero, rage-clicking the moodboard looking for the product, or abandoning specifically at the shipping reveal. Fix this before the next optimization cycle — otherwise every subsequent change is a guess.

## 🟠 Secondary findings

- **Mobile-heavy traffic + collage hero**: texture moodboards are typically large, layered images. On mobile (81% of your traffic), this is a likely Largest Contentful Paint / load-time tax, compounding the message-match problem — slow _and_ off-message.
- **No urgency carried through**: the ad's "this week" 35%-off urgency has no visible countdown, banner, or reinforcement on the landing page or PDP, weakening the offer's psychological pull once someone does click through.

## ✅ Prioritized fix list

1. **Instrument first** — add Microsoft Clarity or Hotjar this week (free/cheap, zero dev risk). You need visibility before you can validate any of the below.
2. **Rebuild the hero to match the ad** — lead with the product (the copper pan/set, ideally the same visual world as the video ad), not an abstract moodboard. Headline should reference the set and the offer, not a brand platform line.
3. **Put price and the 35% discount on the landing page itself** — don't force a click to learn if the offer applies.
4. **Surface shipping cost before payment** — a shipping estimator, a flat-rate banner, or "free shipping over $X" messaging earlier in the funnel removes the late-stage surprise.
5. **Align CTA copy to the ad** — "Shop the set" (or equivalent transactional language) on both ad and page.
6. **Split mobile vs desktop reporting** — given 81% mobile share, you're currently unable to tell if the problem is uniform or concentrated on one device class.

## ⏳ What this doesn't tell you yet

Without recordings/heatmaps, I can't confirm _where_ in the funnel the 0.83% CVR is being lost — hero, PDP, or checkout. Treat the fix list above as ranked by known conversion-research severity (message-match and hidden costs are the best-documented CVR killers), not as a confirmed root cause. Re-run this audit with real behavioral data 2–3 weeks after instrumentation goes live.
