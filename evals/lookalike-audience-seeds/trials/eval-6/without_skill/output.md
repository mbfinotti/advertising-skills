## Recommended Meta audience architecture

**Keep the base list as one combined EU-5 pool.** Don't split by country, and especially don't isolate Sweden.

- Meta requires a minimum of ~100 people to even create a Custom Audience, and needs far more (ideally 1,000+) for a lookalike source to produce good match quality.
- Your Sweden segment (120 customers) drops to roughly 80-90 after Meta's typical hashed-match rate (~65-75%) — below the threshold for a usable audience on its own, and small enough that a country-specific slice risks re-identifying individuals (a GDPR data-minimization problem, not just an ads problem).
- Fold Sweden into the pan-EU pool for every list you build. Never create a Sweden-only export.

**Layered structure (4 lists max, to stay manageable solo):**

| List | Seed size (pre-match) | Use |
|---|---|---|
| EU-5 combined | ~18,000 | Master Custom Audience → master Lookalike |
| Furniture only | subset of 18,000 | Product-line Lookalike |
| Lighting only | subset of 18,000 | Product-line Lookalike |
| High-AOV tier | top-spend subset | Value-based Lookalike |

Each split still draws from all 5 countries — Sweden stays folded in, it's just never large enough to be its own row.

**Language versions:** don't fork the seed lists. Layer language/locale targeting or separate ad creative on top of these same audiences at the ad-set level. Forking seeds by language would fragment Sweden (and every other small segment) below usable size for no targeting benefit — Meta's ad delivery already lets you serve different creative per locale within one audience.

## GDPR compliance — the parts your current process is missing

1. **Legal basis & disclosure.** Uploading hashed customer data to Meta for targeting/lookalike modeling is profiling for direct marketing (GDPR Art. 4(4)). Legitimate interest is a workable basis for existing customers, but only if:
   - your privacy policy names Meta as a recipient/processor of hashed contact data for advertising purposes, across all 5 markets,
   - you can show a short legitimate-interest assessment (purpose, necessity, balancing test — one page is enough for a business this size),
   - the high-AOV split gets the same disclosure, since it's profiling by spend, not just contact matching.

2. **Meta's side is already covered** by their Custom Audience Terms (processor role + SCCs for the EU→US transfer) as long as you tick the "certification of compliance" box each time you create/update an audience in Business Manager — that checkbox is your attestation, not a formality.

3. **Opt-outs are your real gap.** Processing them per-platform, "whenever you remember," means someone who objects doesn't actually stop being targeted until you next happen to refresh the Meta list — that can be weeks. GDPR Art. 21 objection rights are absolute for direct marketing, and Art. 12(3) expects action without undue delay (30 days outer bound).
   - Keep **one master suppression list** (every opt-out/unsubscribe, from any channel), and check every export against it before upload — not the other way around.
   - For urgent individual requests, use Meta's "remove people from audience" feature to strip specific hashed identifiers immediately, rather than waiting for the next full list refresh.
   - Set a recurring weekly reminder to sync the suppression list into Meta. A monthly full-list refresh is realistic for one person; the suppression sync needs to be more frequent than that.

4. **Never hash or transmit raw PII yourself.** Upload through Business Manager's native Custom Audience import — it hashes (SHA-256) client-side/on-upload. Don't build a side pipeline that touches raw emails/phone numbers before sending them anywhere.

## Bottom line

- One combined EU-5 Custom Audience + Lookalike: keep as planned.
- Furniture/Lighting and High-AOV as additional Lookalikes, drawn from the same 5-country pool — fine at your volumes.
- No Sweden-specific list, ever — too small, and drop it into every split rather than isolating it.
- Language: creative/targeting layer, not a separate seed list.
- Fix the opt-out gap first: it's the one piece that's an actual compliance exposure today, not just a targeting-quality question.