## Diagnosis: this is a deduplication defect, not a double-firing defect

"Almost exactly double" is the signature of a **dedup mismatch**, not of CAPI genuinely sending redundant events. Meta's Events Manager merges a browser (pixel) event and a server (CAPI) event into one counted conversion only when three things line up (per Meta's dedup contract):

- identical `event_id` on both sends (per-conversion, not per-page-load)
- **matching event name, exact string including case**
- timestamps within the 48-hour window

You already found the break: pixel sends `Purchase`, server sends `purchase`. That's a naming/casing mismatch — Meta treats those as two different event types, dedup never triggers, and every real purchase gets counted once by the pixel and once by CAPI. That fully explains a ~2x pattern that started the moment CAPI shipped three weeks ago.

## Tell the dev: don't turn off CAPI

Turning off CAPI purchase events is the fix that looks obvious and is backwards. It doesn't fix measurement — it deletes the more resilient of your two signal sources (the one immune to iOS/ATT loss, ad blockers, and browser cookie limits) right before a holiday campaign, which is exactly when you want the algorithm getting the *most* complete signal, not less. If you cut CAPI now, you'll under-count real purchases the moment browser tracking degrades (ad blockers, Safari ITP, etc.), and nobody will notice until spend is already misallocated.

The real fix costs less than what he's proposing:

1. **Standardize the event name.** Both sources must send the exact string `Purchase` (capital P — Meta's standard event name). Fix the CAPI payload to stop sending `purchase`. This is a one-line change, not a rebuild.
2. **Confirm both sources send the same `event_id` per conversion.** Use the Shopify order ID (or order confirmation ID) as that shared ID, sent identically by the pixel and by CAPI for the same order. Casing is the visible bug; a missing/mismatched event ID would produce the exact same symptom, so verify this too — don't assume fixing casing alone is sufficient.
3. Do **not** delete or disable the CAPI purchase event at any point in this fix.

## Verification before trusting it (don't ship on a settings screenshot)

1. Place one real, low-value test order end to end (refund it after).
2. Inspect the actual payload from both sources — Meta Pixel Helper / browser network tab for the pixel, and Events Manager's **Test Events** tool for CAPI. Confirm: event name `Purchase` on both, identical `event_id` on both, correct value and currency.
3. In Events Manager, check the **dedup rate** first (single screen, fastest signal) — target ~90%+, and confirm this one test order shows as **one** counted conversion, tagged both browser and server.
4. Retract the test conversion and refund the test order before letting real traffic accumulate — exclusion isn't retroactive.
5. Soak for 2-4 days on real orders and watch Meta's purchase count converge toward Shopify's. Don't chase an exact match — a 10-20% platform-vs-Shopify gap is normal and not a launch blocker; going from ~200% down to that band is the actual signal the fix worked.

## Timeline

Two weeks is comfortable for this: the code change is small (string fix + confirming shared event ID), payload verification takes under a day, and a 2-4 day soak still leaves a buffer before the holiday launch. Don't scale holiday budget until the dedup rate reads healthy and one test purchase confirms as a single counted conversion — launching while it's still ~2x would train the algorithm on phantom volume through your highest-spend window.

**Bottom line for the dev:** fix the string mismatch (and confirm the shared order ID), verify with one real test purchase in Events Manager's Test Events tool, don't touch the CAPI on/off switch.