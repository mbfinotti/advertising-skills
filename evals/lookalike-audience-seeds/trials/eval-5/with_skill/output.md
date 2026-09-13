## Short answer: No — don't pad the seed with the newsletter list or email openers.

### What's actually happening with the numbers

You're solving for the wrong constraint. Meta's **matched-floor** is 100, not 1,000–5,000 — that range is Meta's _recommended_ sweet spot, not a hard minimum. Run the real math on your 850 buyers first:

- 850 buyers × 50–80% (Meta's documented match range for a good list) = **~425–680 matched**
- Even at a pessimistic 40% (Meta's own "below this = stale list" threshold) = **~340 matched**

That clears the 100 floor on its own. You're not blocked — you're short of the _recommended_ band, which is a different problem, and it doesn't justify what you're proposing to fix it.

### Why the newsletter + openers plan backfires

1. **It's the named failure mode in this skill's own trap table**: _"Padding the seed with everyone to 'hit the minimum' — dilutes the signal cluster; homogeneity outweighs size."_ Meta's own guidance, and the practitioner consensus cited in this skill (Stackmatix, Grow With Sakib), says a few hundred high-value buyers outperforms thousands of undifferentiated subscribers — in the literal wording used: _"500 paying customers beating 5,000 newsletter subscribers in every meaningful test."_ You'd be diluting an 850-person buyer cluster with ~24,000+ people who have never bought anything. The model stops learning "premium dog gear buyer" and starts learning "person who signed up for a newsletter."
2. **"Opened" is the wrong signal, explicitly.** The skill's rule is _"email clickers, never openers"_ — Apple Mail Privacy Protection (2021) auto-pre-fetches images, so "opens" are mostly noise, not engagement. If you want an email-based fallback source at all, it has to be clickers.
3. **Consent exposure you likely haven't checked.** Anything uploaded to Meta as a customer list re-enters the full privacy gate — and newsletter/ESP opt-in consent rarely covers ad-platform matching specifically. That's a separate lawful-basis question from "they gave us their email for a newsletter." Before uploading _any_ non-buyer list, confirm that basis exists — don't assume it.

### What to do instead (fallback ladder, in order — never loosen selection quality first)

You said no data vendors, so **rung 1 (identity enrichment) is deleted outright**, not just deprioritized — no DPA, no vendor, it's not on the menu. Go straight to rungs 2–4:

- **Rung 2 — widen the recency window.** You're at 90 days. Move to 180 (still inside Meta's own website-custom-audience lookback and the "pixel/CAPI-tracked buyer" allowance). This is a query edit, minutes, fully reversible, and it's still _buyers_ — homogeneity intact. Recompute the effective seed at 180 days before doing anything else.
- **Rung 3 — stack an adjacent segment of the same homogeneity.** If you have RFM data, add "Loyal" to "Champions," or repeat buyers beyond 90 days who aren't yet captured by rung 2. Same customer type, just a wider net — not a different audience.
- **Rung 4 — if still short, drop to the next-best _purchase-adjacent_ source**, in this order: checkout/add-to-cart initiators → high-intent page viewers (product/pricing pages) → email **clickers** (never openers). These are still people who showed buying intent, unlike a generic newsletter list sitting at the bottom of the value ranking. Built platform-native off your pixel, they also skip the customer-list consent gate entirely.

### Bottom line

Your 850 buyers are probably already a workable Meta seed as-is (matched count clears the floor). If you want to reach the 1,000–5,000 recommended band, widen the window and stack adjacent buyer cohorts first — don't reach for the newsletter list or openers; that's trading the one thing (homogeneity) that determines whether the lookalike actually works.

**To turn this into a real seed spec, I still need:**

- Buyer count at a 180-day window (and, if you have it, at 12 months)
- Whether you have RFM/cohort data or just raw order history
- Identifiers per row (email only, or also phone/name/postal?)
- Whether any EEA/UK customers are in the list and what consent basis covers ad-platform upload
- Whether you're running one country or multiple (Meta lookalikes are country-scoped — affects how you count "enough")
