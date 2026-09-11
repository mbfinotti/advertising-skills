## Diagnosis: this is a deduplication bug, not double-firing

You already found the root cause. Meta deduplicates a Pixel event and a CAPI event as *the same conversion* only when **both** of these match exactly between the two events:

- `event_name` — case-sensitive
- `event_id` — must be identical on both sides

Your pixel sends `Purchase` (Meta's standard event name), your server sends `purchase`. Meta treats these as two different event types. No dedup happens, so every purchase gets counted twice in Events Manager — once from the browser, once from the server. That fully explains "almost exactly double."

## Don't turn off CAPI — that's fixing the symptom by deleting the better signal

Two weeks before your biggest campaign of the year is the worst time to lose CAPI:
- CAPI is what survives iOS 14.5+ ATT opt-outs, Safari ITP, and ad blockers that kill the browser pixel.
- Server-side events carry better match quality (EMQ), which directly affects how well Meta's algorithm optimizes delivery and CPA — this matters more, not less, during high-spend holiday bidding.
- Disabling CAPI purchases removes exactly the redundancy that protects your purchase signal when browser tracking fails.

Turning it off "solves" the double-count by throwing away the fix's whole point. It's a one-line change that trades a data-quality problem for a data-loss problem.

## The actual fix (do this instead)

1. **Standardize the event name.** Use Meta's exact standard event string `Purchase` (capital P) on both the pixel call and the CAPI payload. Don't let client and server code diverge on casing/spelling.
2. **Pair `event_id` across pixel and server for the same conversion.** Generate one ID per order (e.g. the Shopify order ID, or a UUID set at checkout) and send that exact same value in both the pixel's `eventID` and the CAPI event's `event_id`. This is the actual dedup key — name matching alone isn't sufficient.
3. **Check for a second CAPI source.** Before assuming it's only a naming mismatch: confirm whether Shopify's native "Facebook & Instagram" sales channel app already has its own built-in Conversions API toggle enabled. If your dev added a *separate* custom CAPI integration (code, GTM server container, etc.) without checking that, you may have two independent CAPI senders plus the pixel — worth ruling out so you're not still over-counting after the naming fix.
4. **Verify with Meta's Test Events tool before launch.** Fire a real test purchase and confirm Events Manager shows it as one deduplicated event ("Event deduplicated" / browser+server merged), not two separate rows.
5. **Sanity-check volumes for a few days post-fix** against Shopify's order count to confirm parity, with enough runway before the campaign starts to catch any remaining mismatch.

This is a same-week fix, not a same-day one, but it comfortably fits your two-week window — and it's the version of "today" that doesn't cost you tracking quality going into your highest-value season.