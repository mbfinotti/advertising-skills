## What ships Friday

The consultant's audience-quality ranking is correct. Using it as a launch gate is not. The real choice isn't "purchasers vs. everything else" — it's "wait 5+ weeks for a hand-built CRM export vs. use the purchase signal Meta already has, for free, today."

A pixel that's fired Purchase, InitiateCheckout, and AddToCart events for a year already **is** a purchaser list — it's sitting in Meta Events Manager right now. No unified export, no CSV, no data engineer required to reach it. That data existed before the engineer's calendar became the blocker; the blocker only applies to the CRM-side export, which isn't the thing gating Friday.

### Step 1 — Check volume today (Events Manager)

- Pull trailing 180-day counts for Purchase, InitiateCheckout, AddToCart.
- Meta needs ~100 events to build a Lookalike, 1,000+ for a reliable one. This number decides everything below.

### Step 2 — Seed hierarchy, ranked by what's actually available

1. **Purchase event Custom Audience** — best seed, use if ≥1,000 events/180 days.
2. **InitiateCheckout** — fallback or blend if Purchase is thin.
3. **AddToCart** — broader intent pool, almost always has volume.
4. **Video engagers (ThruPlay / 95% viewers)** — warm, non-transactional, good supplemental seed given the decent view counts.

### Step 3 — Build Lookalikes off whichever seed clears the volume bar

- 1% and 1–3% stacked ad sets.
- Purchase-based 1% LAL as primary if volume allows; Checkout+ATC blended as primary if Purchase is thin, labeled internally as v1.

### Step 4 — Run an Advantage+ Shopping Campaign in parallel

- Skip manual-LAL guesswork; let Meta's algorithm optimize directly against Purchase using the same year of pixel data.
- At this seed size, Advantage+ campaigns typically outperform a hand-built LAL — make it the primary vehicle, keep the manual LAL as a comparison ad set.

### Step 5 — Fix match quality same day, still no engineer

- If the storefront is Shopify (or similar), flip on the native Meta Conversions API integration — one checkbox, no code.
- This recovers iOS 14.5+ signal loss and directly raises the Purchase event count from Step 1, which raises audience quality without touching the CRM problem at all.

### Timeline

- **Day 1**: pull event counts, enable CAPI if missing, build Custom Audiences.
- **Day 2**: build LALs + Advantage+ campaign, QA creative and placements, set budget.
- **Day 3 (Friday)**: live before the board meeting, delivery status screenshotted.

### What not to ship

- Don't wait on the unified CRM export to launch — that's the correct _target state_, not the Friday deliverable.
- Don't present this as the final audience. It's v1: pixel-seeded, live today. v2 is a CRM-verified, LTV-weighted purchaser seed (with refunds/fraud excluded) once the engineer is free in 5 weeks — swapped into the same campaign structure without a relaunch.

### For the board, one line

"We're live Friday on Meta with a purchase-intent lookalike built from a year of pixel data — no CRM export needed. In 5 weeks we upgrade the seed to verified, LTV-weighted purchasers once the unified export ships, without pausing the campaign."
