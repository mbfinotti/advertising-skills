# What ships by Friday: a platform-native prospecting lookalike, built off the pixel you already have — not the purchaser export

**Verdict up front:** don't wait on the CRM export. Build the Meta lookalike off checkout/add-to-cart events and video engagement, both of which the pixel has been capturing for a year. This can go live in Ads Manager in under an hour, with zero dependency on the data engineer and zero new privacy exposure. The purchaser-based seed becomes v2, running in parallel over the next few weeks — it does not block Friday, and it shouldn't.

## Why the consultant's advice is a trap here, specifically

"Purchasers are always strongest" is true on exactly one axis: **value**. It ignores the other two axes that decide what's actually buildable this week:

- **Effort**: purchasers need a unified export across three systems — a data-engineering project, not a query, and your engineer is five weeks out.
- **Compliance cost**: any list of real customers uploaded to Meta triggers a full consent gate (documented lawful basis, opt-out propagation, platform terms acceptance) _before_ a single row moves. Platform-native audiences built from pixel events never leave the ad account and trigger none of that.

Read all three axes together, purchasers lose this round — not on merit, on timeline. Building the export first and launching later is the wrong sequencing when the board date is fixed and the constraint is a person's calendar, not data quality. Ship the native audience now; run the export as background work so purchasers become the seed for v2 without ever blocking v1.

## What I'm assuming (flag before you publish)

I don't have your real numbers — confirm these before Friday, none of it needs the data engineer:

- ⚠️ **Primary market/country** — Meta lookalikes are country-scoped by construction. If Marlowe Threads sells to multiple countries, this needs one seed-and-lookalike pair per country; for Friday, ship the largest market first.
- ⚠️ **Qualifying event volume** — check Events Manager for unique users on `InitiateCheckout`, `AddToCart`, and `Purchase` over the trailing 180 days, and `ThruPlay`/75%+ video views over the same window. This is a five-minute look, not an engineering task.
- ⚠️ **Consent banner coverage** — since the pixel has fired live for a year, your CMP presumably already gates it correctly; just confirm the advertising-cookie category is active and EEA/UK traffic isn't being silently dropped, if you sell there.
- ❌ **Baseline CPA/LTV** — not given, so this seed can't be graded against history yet. Treat the first cohort as the baseline-building run.

## Seed Specification A (primary, ship Friday)

```
SEED SPECIFICATION - checkout-atc-native v1, 2026-09-18
platform        : Meta (Website Custom Audience, pixel-native) | audience type: lookalike (Advantage+ Audience)
definition      : unique users firing InitiateCheckout or AddToCart, last 180 days
value column    : none (standard, not value-based - no value column available without CRM data)
row count       : n/a - not an uploaded list; qualifying pixel events become the audience directly
identifiers/row : n/a (cookie/device-matched by Meta, no PII leaves the site)
expected match  : n/a - platform-native, no upload match-rate step applies
effective seed  : qualifying unique users vs floor 100 (target 1,000-5,000) -> CONFIRM in Events Manager before publish
fallback used   : none needed if checkout+ATC volume clears the recommended band; else stack rung 3
                  (add ViewContent on product pages) - same homogeneity, same effort, still zero gate
exclusions      : none available (no order-level data to strip refunders/discount-only/employees -
                  accepted gap for v1, closed when the purchaser seed lands in v2)
consent basis   : n/a for upload gate - nothing leaves the platform; confirm CMP still permits the
                  Meta pixel's advertising-cookie category (existing consent, not new exposure)
refresh         : automatic (Meta refreshes pixel-sourced audiences ~every 3-7 days) | owner: none needed
measurement     : baseline-building run - no prior CPA/LTV to grade against; log new-customer CPA and
                  90-day cohort LTV for this seed version
re-check        : 2026-10-16 (respect learning phase ~2-4 weeks, then read at 90-day cohort maturity for LTV)
```

## Seed Specification B (parallel, for the split test)

```
SEED SPECIFICATION - video-viewers-75-native v1, 2026-09-18
platform        : Meta (video engagement custom audience) | audience type: lookalike (Advantage+ Audience)
definition      : users at 75%+ completion on product videos, last 180 days
value column    : none
row count       : n/a - platform-native
expected match  : n/a
effective seed  : qualifying unique viewers vs floor 100 (target 1,000-5,000) -> CONFIRM volume; this is
                  the volume backstop for Seed A if checkout+ATC undershoots the recommended band
fallback used   : none
exclusions      : same gap as Seed A - accepted for v1
consent basis   : same as Seed A - no new exposure
refresh         : automatic
measurement     : run as a user-level split test against Seed A, not a naive ad-set comparison -
                  Meta supports this natively; this is the valid way to read which seed is stronger
re-check        : 2026-10-16, same checkpoint as Seed A
```

## Suppression (build this too — five more minutes)

Build a third pixel-native audience on `Purchase` events (lifetime or max lookback) and use it purely as an **exclusion** on both ad sets. This keeps the prospecting campaign from spending against people who already bought, without needing any customer list — same zero-gate mechanism as the seeds above.

## What happens after Friday

Kick off a lighter purchaser export than the consultant's framing assumes: check whether your storefront platform alone (Shopify or equivalent) can export an orders/customers CSV directly from its admin — that's usually a marketer-doable task, not an engineering one, and doesn't require reconciling all three systems. If so:

1. Run the negative-selection pass (refunders, discount-only, employees, wholesale) and RFM Champions+Loyal selection per the standard workflow.
2. Clear the full consent gate before any upload — this takes real time (legal sign-off), so start it now in parallel, don't wait for the engineer.
3. Launch it as v2, retire v1 once it clears the floor and starts beating v1's CPA/LTV at cohort maturity.

This gets the founder a live, defensible prospecting lookalike for Friday's board meeting, and a credible path to the "real" purchaser-based asset without making the board date hostage to a five-week queue.
