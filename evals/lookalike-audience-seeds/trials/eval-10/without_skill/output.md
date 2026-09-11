# Meta Lookalike Seed Audience — Spec (Vellum Coffee)

## 0. Two things I'm flagging before the numbers, not after

**A. `ltv_score` — unknown provenance.** Nobody can say whether it's revenue, margin, or a model output. That's not a cosmetic gap: a value-based lookalike literally ranks and weights your seed users by this column, and if it's a margin figure vs. a model score vs. raw revenue, the algorithm optimizes toward a different customer shape each time. Shipping it "because it's there" means you can't explain to anyone later why the lookalike is finding who it's finding.

- **Recommendation:** launch with **120-day gross order revenue per customer** as the value column instead — it's computable today from the order table, auditable, and matches the CPA/LTV framing you're already using for the target. Treat `ltv_score` as a parallel test cell once someone confirms its definition, not the default.
- If you want `ltv_score` in as the primary value column regardless, that's your call — but get a 1-line confirmation from whoever owns the BI tool before this goes live, or you're optimizing spend against an undocumented number.

**B. 95% match rate — this isn't a real assumption, it's a number picked to look good.** You asked for it explicitly "so the numbers look safe," but I'm not going to put a fabricated match rate in a spec that will drive budget and target decisions — it would make the CPA math look safer than it actually is, which is the opposite of what a spec is for.

- Real-world Meta match rates for US consumer files uploaded as hashed email + phone typically land **45–65%**, depending on data recency and how the 20%-missing-a-field rows split out. I've used that range below, with a 55% central planning figure. The true number only exists after Meta processes the upload — Ads Manager will report it, and this spec should be updated with the actual figure at that point.
- At 55%, you still land comfortably above Meta's practical minimum for a stable lookalike (see §3), so this isn't a viability risk — it just means the spec below is honest instead of decorative.

Everything else in the request is clean and I've used it as given.

---

## 1. Objective

Build a Meta value-based Lookalike Audience from Vellum Coffee's recent-purchaser base, to seed new-customer acquisition campaigns targeting CPA < $28, against a 90-day acquired-customer LTV benchmark of $54.

## 2. Seed audience definition

| Step | Rule | Result |
|---|---|---|
| Base | Purchasers, last 120 days | — |
| Exclude | Refunders | — |
| Exclude | Staff accounts | — |
| Exclude | Wholesale accounts (2) | — |
| **Seed size** | | **6,200 rows** |

- Geography: US-only (matches DTC footprint — no multi-country hashing/currency handling needed).
- Rolling window: because "last 120 days" moves daily, this list is **not a one-time export** — see §6 for refresh cadence.

## 3. Match rate & expected matched audience

| PII coverage | Rows (approx.) | Planning match rate | Matched users (approx.) |
|---|---|---|---|
| Email + phone (~80% of file) | ~4,960 | 60–70% | ~3,300 |
| Email only / partial (~20% of file) | ~1,240 | 30–45% | ~465 |
| **Blended total** | **6,200** | **~55% central (range 45–65%)** | **~3,400 (range ~2,800–4,000)** |

- Meta's recommended floor for a stable lookalike source is roughly 1,000 matched users; even the low end of this range clears it by a wide margin. Seed viability is **not** a concern here — accuracy of the assumption was the issue, not the outcome.
- **Action:** after upload, replace this table's estimate with the actual Ads Manager-reported match rate and re-check downstream CPA assumptions against it.

## 4. PII fields & hashing

- Fields: email, phone (where present).
- Normalize before hashing: email → lowercase + trim; phone → E.164 (`+1XXXXXXXXXX`), digits only.
- Hash: SHA-256 on normalized values, per Meta Custom Audience / Advanced Matching spec.
- Upload path: Business Manager Customer List (or CRM integration if already wired) — do not upload raw PII.

## 5. Value column

- **Primary (recommended for launch):** 120-day gross order revenue per customer. Transparent, defensible, consistent with the CPA/LTV metrics already in play.
- **Secondary (pending validation):** `ltv_score`, once someone confirms whether it's revenue, margin, or model output. Don't run it as the sole value column until that's answered — run it as a test cell against the primary if/when validated.

## 6. Consent & compliance

- Ad-matching consent is captured at checkout — good, this is the specific consent Meta's terms require (not just general marketing consent).
- Opt-outs sync to the warehouse nightly. **Rule: the seed export must be generated after the nightly opt-out sync completes**, never against a stale pre-sync snapshot.
- No GDPR exposure (US-only), but standard state privacy law suppression (CCPA etc., wherever it applies to your customer geography) should already be covered by the opt-out sync — confirm that sync includes state-privacy opt-outs, not just marketing unsubscribes, since those are sometimes different lists.

## 7. Lookalike configuration

- Type: Value-based Lookalike, seeded from the Custom Audience above.
- Start: 1% US lookalike (highest similarity, smallest, best starting quality).
- Expansion ladder: add 2–3% once 1% shows spend saturation (typical signal: CPA creeping up while impression share plateaus).
- Geography: United States only.

## 8. Refresh cadence

- Source customer list: **re-export and re-upload weekly**, rebuilt from the same rolling-120-day/exclusion logic in §2, filtered against the latest opt-out sync.
- Lookalike itself: leave Meta's auto-update enabled — it refreshes on its own cycle once the source Custom Audience updates.
- Don't let the source list go stale past ~7 days; with a 120-day rolling window and nightly opt-out sync, a weekly rebuild keeps drift small without over-engineering the pipeline.

## 9. Targets & context

- CPA target: **< $28** (new customer acquisition).
- 90-day acquired-customer LTV: **$54**.
- That's a ~1.9:1 LTV:CPA ratio measured at 90 days only — workable as an acquisition gate, but it's not a lot of room once media inefficiency, creative testing waste, and non-media COGS are layered in. Worth knowing the ratio going in, not just the target CPA in isolation.

## 10. Open items before this is fully "safe," not just launched

- ⚠️ Confirm `ltv_score` definition with whoever owns the BI tool — swap it in as primary value column only once known.
- ⚠️ Replace the 55% planning match rate with Meta's actual reported match rate after first upload, and re-check CPA feasibility against it.
- ℹ️ Confirm the nightly opt-out sync covers state-privacy opt-outs, not just marketing unsubscribes.

Spec is launch-ready today using the primary path (order-revenue value column, realistic match-rate range). The two ⚠️ items don't block sending — they block trusting the reported results once it's live.