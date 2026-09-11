## Root cause: the salt is breaking almost every email match

Meta's Custom Audience matching only works if your hash is **bit-for-bit identical** to the hash Meta computes server-side from the same person's data on file. Meta's algorithm is: normalize → SHA-256, with **no salt, no pepper, nothing added**. A per-customer salt guarantees your hash never equals Meta's hash of that same email, even when the email is 100% correct and the person has a Facebook account. Email is normally the strongest match key (usually 45–65% of matches on a clean list), so salting it likely drops your email-driven matches close to zero. That's almost certainly your 9%.

⚠️ This isn't a "your data is dirty" problem primarily — it's a "the hash Meta receives cannot mathematically match anything" problem.

## Secondary issues (real, but smaller than the salt)

- **Email normalization**: Meta requires lowercase + trimmed whitespace *before* hashing. Mixed case and trailing spaces, hashed as-is, produce a different hash than Meta's normalized version — each one an independent way to fail the match, stacking with the salt problem.
- **Phone format**: `+44 07911 123456` is wrong on two counts — spaces must be stripped, and the UK trunk `0` must be dropped after the country code (Meta wants digits only, e.g. `447911123456`). Uploaded as-is, phone match rate is near 0% too.
- **Data staleness**: ~1/3 of rows from 2021–2022. People change emails/phones and Facebook accounts lapse, so match rate naturally decays with age — but this typically costs you single-digit-to-teens percentage points, not the ~90 points you're missing.

## Should you buy an enrichment service? No — not yet.

Buying enrichment now would mean paying to improve contact data that's never reaching Meta's matcher correctly in the first place. Fix the pipeline first; it's free and the fix is well-defined:

1. **Drop the per-customer salt for the Meta export path.** Compute the Meta-required hash — `SHA256(lowercase(trim(email)))`, no salt — at export time, from the same source data, and discard the plaintext immediately after. The value leaving your network is still an irreversible one-way hash, so the "no plaintext PII leaves the network" security property is preserved.
2. **Fix phone normalization**: strip all non-digits, prepend country code, drop the leading trunk `0` → `447911123456`, then SHA-256.
3. **Re-test on a small sample** (500–1,000 rows) before re-running all 22,000, to confirm match rate jumps into a normal range (typically 40–65% for reasonably fresh B2C lists with email+phone; lower end of that if a third of rows are 2–3 years stale).
4. **Add more identifier columns if you have them** — first name, last name, city, state, zip, DOB, gender. Meta does combinatorial matching across all supplied keys, and each additional correctly-normalized key raises match rate independently of email/phone.

Only revisit enrichment (appending updated emails/phones to the 2021–2022 rows) *after* the hashing fix, and only if match rate on that stale cohort specifically is still weak — at that point it's solving an actual data-recency gap, not masking a broken pipeline.

## How to frame this with your security team

Their instinct (hash PII, don't send plaintext) was correct and should stay. The fix isn't "stop hashing" — it's "hash exactly the way Meta's matcher expects for this one specific export," which is still a one-way SHA-256 hash with no reversible plaintext ever leaving the network. Frame it as: keep your salted hash for internal storage/audit as-is; add a second, unsalted, normalized SHA-256 computed just for the Meta upload, generated on the fly and not persisted. That satisfies both the security requirement and Meta's matching requirement without compromise.