## Match rate diagnosis — Fenwright Home, Meta customer list (22,000 rows, 9% matched)

**Short answer: no, don't buy enrichment yet.** Your 9% isn't a data-scarcity problem — it's three free, reversible hygiene bugs stacked on top of each other, one of which is almost certainly fatal on its own. Fix those first, re-upload, remeasure. Enrichment is the last rung on the ladder, not the first.

### What's actually causing 9%, ranked by likely impact

| # | Issue | Why it kills match rate |
|---|---|---|
| 1 | **Salted SHA-256 on emails before upload** | Meta hashes plaintext on ingest and compares hash-to-hash against its own index. A per-customer salt means your hash can never equal Meta's hash of the same email — not "worse," *impossible*, regardless of upload path (UI or API). This almost certainly zeroes out email as a matching identifier entirely. |
| 2 | **Phone format `+44 07911 123456`** | Has spaces, a literal `+`, and a leading `0` retained after the country code. Meta wants E.164-style digits only, no `+`, no leading zero — e.g. `447911123456`. Malformed phones don't partially match; they mostly fail to normalize at all. |
| 3 | **Mixed-case emails with trailing spaces** | Never normalized before hashing (lowercase + trim is required *before* the hash, otherwise the hash of `John@X.com ` ≠ hash of `john@x.com`). |
| 4 | **~⅓ of rows from 2021–2022** | 3–5 years old. Contact data past 12–18 months measurably degrades match rate on its own, independent of the format issues above. |

Given #1, your 9% is probably coming almost entirely from whatever fraction of the phone numbers happen to still parse despite the formatting problem — email is likely contributing close to nothing.

### Fix order (cheapest and most reversible first — this is the skill's documented efficiency order, not an arbitrary checklist)

`normalize formats > join identifiers already held > drop stale rows > buy enrichment`

1. **Stop pre-hashing for the UI path.** Upload normalized plaintext through Meta's UI — Meta hashes on ingest. If your security team's "no PII leaves the network in plaintext" policy is non-negotiable, the correct route is the **Conversions API**, hashing with Meta's exact spec: trim + lowercase, then **unsalted** SHA-256. Reframe this for security: a salt isn't a stronger control here, it's a broken mechanism for a matching use case — TLS in transit + unsalted normalized hashing is Meta's actual documented security model, not a compromise.
2. **Reformat phone to E.164 digits**: strip `+`, spaces, and the leading `0` after the UK country code → `447911123456`.
3. **Lowercase + trim every email** before hashing.
4. **Join any other identifier you already hold** (name, postcode) — multiple identifiers per row beats email alone, and this costs about an hour, not a vendor contract.
5. **Segment out the 2021–2022 rows** and test separately, or drop them — a stale third is dragging down your blended rate regardless of the fixes above.

Re-upload after 1–4 and remeasure before touching rung 1 (enrichment).

### Expected outcome

Meta's documented range for a clean list is **50–80% matched**; below 40% signals a poor/outdated list. Fenwright Home sounds like a genuine B2C customer file (real personal emails + mobile phones), not a B2B work-email list on a consumer platform — that's the one case where enrichment is the *only* rung that moves the needle. Nothing in what you've described points to that case. Fixing #1–#4 should land you solidly in Meta's normal range without spending on a vendor.

### When enrichment would actually be the right call

Only if, after all four fixes, you're still stuck near single digits *and* the underlying problem is identifier scarcity (e.g., only email, no phone/name at all) rather than format/hashing. That's not what's described here — don't skip to it.

### One thing to flag while you're in here

Salted or not, hashed emails are still personal data under GDPR — hashing doesn't remove the consent requirement for uploading this list to Meta (Bavarian DPA position, upheld by the Higher Administrative Court Munich, 2018). Worth a quick check with whoever owns consent for this list that lawful basis is documented before the next upload, separate from the technical fix.

### Don't grade the fix on match rate alone

Once you re-upload, match rate tells you the data got clean — it doesn't tell you the lookalike will perform. Grade the resulting audience on new-customer CPA and 90-day cohort LTV, not on the match percentage itself.