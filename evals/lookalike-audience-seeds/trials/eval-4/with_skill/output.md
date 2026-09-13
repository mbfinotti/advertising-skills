# Lookalike Seed — Hafenlicht EU Customer Match / Custom Audience

## The gate stops this before any list gets built

Step 2 of this process is a hard stop, run _before_ selecting a single row, and the workflow is explicit: if any item is unconfirmed, refuse to proceed and say what's missing. Two separate things fail that gate here — not one.

### 1. The agency's legal theory is wrong, not just optimistic

SHA-256 hashing does not make the list anonymous, and GDPR does not stop applying to it. The Bavarian DPA position, upheld by the Higher Administrative Court Munich (2018, Ref. 5 CS 18.1157), holds that customer-list custom audiences require prior consent — hashing produces **pseudonymous** data, not anonymous data, and consent obligations survive the hash. Every hashed row still re-identifies the moment it matches against the platform's own user graph. "It's hashed so it's anonymous" is the exact reasoning that ruling rejected.

What's actually needed before any upload, none of which is confirmed in what you've described:

- Documented lawful basis / consent for uploading this specific list to Google and Meta.
- Consent Mode v2 signals passed with both `ad_storage` and `ad_user_data` GRANTED for the EEA rows going to Google Customer Match (mandatory since March 2024).
- Opt-outs and deletions enforced once in the warehouse, before export — not patched in per-platform afterward.
- Meta's separate customer-list terms acceptance on the ad account (and a further, separate acceptance if any list ends up value-based).

### 2. The sleep-and-anxiety segment is a sensitive-category seed, independent of the consent question above

This skill blocks seeds built on sensitive categories outright — health is explicitly listed. Purchase history for a sleep-and-anxiety product line discloses a likely health or mental-health condition about each customer. That's not solved by getting consent for ad-platform upload in general; it's a separate, harder question (special-category data under GDPR Art. 9) that needs its own legal read, and it's the kind of thing that should go to counsel by name, not get waved through under a generic consent sign-off. **Recommendation: drop this as the seed idea.** Use a non-health cohort (e.g. Champions + Loyal across the full catalog, or a high-AOV slice) as the seed instead — same mechanics, none of the special-category exposure. If you still want the sleep-and-anxiety line specifically, it needs its own explicit legal question, not a slot in this week's general list review.

### Answer to "can we upload now and let legal review in parallel"

No. This skill is not legal advice and routes exactly this kind of open question to counsel — but the specific ask ("define and upload the seed now, review after") is the one move the gate exists to prevent. An uploaded list is data that has already left the warehouse and reached two ad platforms; "review in parallel" doesn't undo that if the answer comes back no. Nothing below the gate — row selection, negative filtering, match-rate math — is blocked by waiting; only the export/upload step is.

## What can actually ship this week without waiting on legal

Platform-native engagement audiences carry no consent exposure at all — no customer list leaves the warehouse, so step 2 doesn't apply:

| Source                                          | Setup                                     | Consent exposure       |
| ----------------------------------------------- | ----------------------------------------- | ---------------------- |
| Checkout/add-to-cart initiators (Meta + Google) | ~1 hr if commerce events are instrumented | None — platform-native |
| High-intent page viewers (PDP, checkout)        | Near-zero if pixel/tag already fires      | None — platform-native |
| Video/page engagers                             | Minutes                                   | None                   |

Build the Meta and Google lookalikes off one of these this week, get the audience live and out of the learning phase, and swap in (or add alongside) the Customer Match / Custom Audience list once legal clears — you lose nothing by sequencing it this way, and you hit the "this week" date on something real instead of on a list you may have to pull back.

## Seed Specifications — BLOCKED

Per the Evidence Gate, these cannot be emitted as usable specs; here's exactly what's missing so the data team and legal have a concrete target.

```
SEED SPECIFICATION - hafenlicht-google-customer-match v0 (DRAFT - BLOCKED), 2026-09-12
platform        : Google Customer Match | audience type: lookalike (signal)
definition      : identity-resolved EU purchasers, RFM Champions+Loyal, recency TBD (candidate 90-180d)
value column    : unknown provenance - needs confirmation (revenue vs margin vs predicted LTV)
row count       : ~30,000 total EU customers (pre-selection; not yet filtered to Champions+Loyal)
expected match  : 29-62% (Google's documented range; not yet adjusted for identifier density)
effective seed  : cannot compute - row count above is unfiltered, not a seed count
fallback used   : n/a - not reached
exclusions      : negative-selection pass not yet run
consent basis   : BLOCKED - no documented lawful basis for ad-platform upload; Consent Mode v2
                  GRANTED signals not confirmed; hashing does not substitute for consent
                  (Bavarian DPA / OVG Munich 2018, Ref. 5 CS 18.1157)
refresh         : not yet decided
measurement     : not yet set (need current acquired-customer CPA and 90-day cohort LTV baseline)
re-check        : n/a until gate clears
```

```
SEED SPECIFICATION - hafenlicht-meta-custom-audience v0 (DRAFT - BLOCKED), 2026-09-12
platform        : Meta Custom Audience | audience type: lookalike
definition      : identity-resolved EU purchasers, RFM Champions+Loyal, recency TBD (candidate 90-180d)
value column    : unknown provenance - needs confirmation
row count       : ~30,000 total EU customers (unfiltered)
expected match  : 50-80% (Meta's documented good-list range; not yet adjusted)
effective seed  : cannot compute - see above
fallback used   : n/a
exclusions      : negative-selection pass not yet run
consent basis   : BLOCKED - same as Google spec above; Meta also requires a separate value-based
                  terms acceptance if this becomes a value-based audience
refresh         : not yet decided
measurement     : not yet set
re-check        : n/a until gate clears
```

Note the sleep-and-anxiety segment doesn't even get a draft spec above — per the sensitive-category rule it's excluded from the menu, not deferred.

## What to line up now, so the spec is ready the day legal clears

None of this needs to wait:

- **Identifiers per row** for the ~30,000 EU customers — email alone vs. email+phone+postal. More identifier types materially raises the match-rate estimate used above.
- **Value column provenance** — confirm whether any LTV/value field is margin, predicted LTV, or just cumulative revenue (the last one is explicitly disallowed as a value column).
- **Recency data** — what share of the 30,000 purchased in the last 90 vs. 180 days, so the RFM Champions+Loyal cohort can actually be sized.
- **Country breakdown of the 30,000** — Meta lookalikes are country-scoped by construction, so "EU customers" as one list needs splitting into one seed-and-lookalike pair per country (Germany likely first by volume, given a Berlin-based brand — confirm).
- **Negative-selection data** — refunders, chargebacks, discount-only buyers, employee/wholesale accounts, and the current opt-out/do-not-contact list, so this can be stripped before export the moment it's cleared.
- **Refresh owner and mechanism** — manual CSV vs. automated warehouse sync; CSVs don't auto-refresh and Google Customer Match drops unrefreshed members after 540 days.
- **Baseline numbers** — current acquired-customer CPA and 90-day cohort LTV, since the seed can't be graded without them.

Once consent is documented and the sleep-and-anxiety question is separately resolved (or dropped), this becomes a same-day exercise: plug the identifier/recency/country numbers into the specs above, run the negative-selection pass, compute effective seed vs. floor (Google: 100 matched; Meta: 100 matched, 1,000-5,000 recommended), and split by country before upload.
