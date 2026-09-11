# Seed Specification — Vellum Coffee, Meta Lookalike

Before the spec: two of your inputs fail this skill's evidence gate, and I'm not passing them through as given. Corrected below, with the reasoning.

## Flags (read before using the spec)

**1. `ltv_score` can't be the value column — provenance is unknown.**
The skill's evidence gate is explicit: *"'we have an LTV field' is not evidence. If nobody can say whether it is revenue, margin, or a model output, the seed is not value-based until someone can."* Revenue, margin, and a model score all mean different things fed into a value-based lookalike — revenue trains the model toward high-spend/low-margin whales, margin trains it toward profit, an unvalidated model score could train it toward anything, including noise. I'm shipping this as a **standard** (non-value-based) purchaser lookalike instead. Get someone (whoever owns the BI layer, or check the dbt/SQL model definition) to confirm what `ltv_score` actually computes, then re-issue as v2 value-based once it's known.

**2. 95% match rate isn't a real number — I used a documented one instead.**
Meta's own good-list band is 50–80%; above ~80% isn't achieved on customer-list uploads regardless of list quality, and picking 95% "so the numbers look safe" would make the effective-seed math (and therefore the CPA/LTV projections built on it) fiction. Your list is fresh (120-day window) with email+phone on 80% of rows — solidly good-list territory but not top-of-band because of the 20% email-only rows. I used **65%**, labeled as an estimate per the platform range. It still clears the floor with room to spare, so the correction costs you nothing except an honest number.

**3. CPA baseline is missing.** You gave a CPA *target* ($28) and an LTV *baseline* ($54), but not the account's *current* acquired-customer CPA. The pass/fail grading in this skill compares the seed against the account's actual baseline on both metrics — a target isn't a baseline. Flagged below as an open item rather than assumed.

---

```
SEED SPECIFICATION - purchasers-120d-standard v1, 2026-09-12
platform        : Meta | audience type: standard lookalike
                  (value-based BLOCKED - ltv_score provenance unconfirmed, see flag 1)
definition      : identity-resolved purchasers, last purchase <= 120 days,
                  minus refunders, staff, and 2 wholesale accounts
value column    : none (blocked - see flag 1)
row count       : 6,200 | identifiers/row: email (100%), phone (~80%)
expected match  : 65% (basis: Meta good-list band 50-80%; fresh list, multi-identifier
                  on 80% of rows pulls it mid-band; remaining 20% email-only drags it off
                  the top - estimate, not calibrated against a prior upload; 95% rejected,
                  see flag 2)
effective seed  : 6,200 x 0.65 = ~4,030 matched vs floor 100 -> clears
                  (within Meta's 1,000-5,000 recommended band)
fallback used   : none needed - clears on first pass
exclusions      : refunders, staff, 2 wholesale accounts stripped by source query -
                  confirm "usual junk" also covered serial returners and discount-only
                  buyers, the two negative-selection items not named explicitly;
                  do-not-contact/opt-out list enforced via nightly warehouse sync;
                  existing customers kept IN the seed, suppressed from the acquisition
                  campaign via a separate delivery-level exclusion audience
consent basis   : checkout consent captured for ad-platform matching; opt-outs synced
                  to warehouse nightly, enforced before any platform sync - confirm this
                  sync specifically propagates CCPA/CPRA Global Privacy Control signals
                  (not just generic opt-outs), and confirm Meta customer-list terms are
                  accepted on this ad account before first upload
identifier prep : emails lowercased/trimmed; phone to E.164 digits, no '+', no leading 0;
                  upload plaintext via UI - do not pre-hash, Meta hashes on ingest
refresh         : recommend extending the existing nightly opt-out pipeline into a full
                  automated warehouse sync (you already run one for opt-outs, so this is
                  the cheap extension, not a new build) - cadence/owner not yet named,
                  assign before launch. Bridge option: manual CSV, refreshed bi-weekly,
                  same owner requirement.
measurement     : new-customer CPA target <$28 (stated goal - current CPA baseline not
                  supplied; grading against a target instead of a baseline is provisional,
                  see flag 3 - supply the actual current CPA or treat this run as the
                  CPA baseline-building cohort); cohort LTV at 90/180/365d by seed version
                  vs $54 account avg
re-check        : 2026-12-11 (90-day cohort checkpoint) - respect the learning phase
                  (~50 optimization events/ad set/week, or 2-4 weeks at low volume)
                  before reading anything early
```

**Splits:** US-only, single country — no country split needed. No product-line or high-AOV split unless Vellum runs genuinely distinct buyer segments (e.g., subscription vs. one-off) worth separating; not indicated by what you gave me.

**Pass threshold:** this seed version passes if 90-day acquired-customer cohort LTV meets or beats $54 at CPA equal-to-or-better than the account's real current baseline (not yet supplied) — or, failing that baseline, beats the $28 target outright. Below that: re-seed on a validated value column (once `ltv_score` is resolved), tighten recency, or split.

**To close before launch:** (1) get `ltv_score`'s definition from whoever owns the BI model; (2) supply current acquired-customer CPA; (3) confirm GPC propagation and Meta terms acceptance; (4) name a refresh owner.