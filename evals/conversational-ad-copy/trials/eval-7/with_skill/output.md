# Thornquist Analytics — AI Shopping Placement: Source-Rewrite Package

## 0. Stop and fix first — the review-voucher plan as described is non-compliant

"$25 voucher for every 5-star review" conditions payment on the rating given. That's the exact pattern the US FTC's rule on fake/deceptive reviews (16 CFR Part 465), the UK CMA/ASA, and EU consumer-protection law all treat as a manipulated review — not a disclosure problem you can fix with a footnote, a ban on the mechanic itself. If this goes out as written this week, every review it generates is compromised at the source, and reviews are the one asset on this path with the highest trust weight and no edit path afterward — get this wrong now and you've poisoned the asset you most need to compound.

**Compliant version, same budget, same week:**
- Pay the $25 for a **verified review, any rating** — not for a 5-star one.
- Disclose the incentive on/with the review ("received a $25 gift card for this review") per platform rule.
- Don't filter, delay, or selectively publish based on the rating you get back — suppressing negative ones is the same rule violation from the other side.
- Route this specific mechanic to legal/compliance for sign-off before send, today — not after.

This is the one action item with a real deadline. Everything below assumes you fix the offer's wording before it ships.

## 1. Placement + control axis

**AI shopping placement, model-generated, feed-driven.** You don't author ad text here — the model synthesizes it from your product feed (and, on some vendors, reviews and site content). The feed is the entire ad. You own the feed directly, so it's the one asset you can change this quarter with zero dependency on the agency or a dev queue.

Open item: you didn't name the vendor (Google AI Mode Shopping, Amazon Sponsored Products/Brands Prompts, or OpenAI's `product_ad_template`, which made feeds mandatory for shopping results on 2026-09-04). This matters because Amazon's version also pulls from reviews and Brand posts directly into the generated copy — if that's your vendor, the review-content quality feeds the ad text, not just the star average. Confirm before the next iteration; the rewrite below is written to hold regardless of which one it is.

## 2. Source rewrite order applied to this account

Default order (feed-driven shopping placement, so feed jumps to first):

1. **Feed fields — do now, you own this.**
2. **Reviews — start now, redesigned per §0; expect nothing from it this flight, it pays into next year's.**
3. ~~Landing-page passages~~ — **deleted, not demoted.** Agency-owned, frozen quarterly release, you have no edit path this quarter. Routed: file the rewritten passage below as a request for the agency's next release window.
4. ~~Structured data~~ — **deleted, not demoted.** Zero dev availability rules it out even though your "compounding" goal would normally promote it. Routed: same request, next quarter, whoever owns the dev queue.

## 3. Feed field rewrites

### Price — fix regardless of copy quality
`$149/mo` → **`$179/mo`**. A stale price field isn't a messaging problem, it's an eligibility and trust problem on a shopping surface that quotes it directly — a wrong price is closer to a malformed field than weak copy. Set a monthly reminder to reconcile the feed against billing; this has already drifted once for three months.

### Description — before

> "Best-in-class AI-powered price intelligence for winners."

Fails on sight: no product name, an unsupported superlative sitting exactly where the model's own answer can contradict it in the same turn, "for winners" is filler with no claim in it, nothing specific enough to quote.

### Description — after (ship this)

> "Thornquist Analytics tracks competitor prices across your e-commerce catalog and flags every change in real time."

~16 words / ~112 characters.

**Trimmed alternative**, if your vendor's copy field runs tighter than the description field (e.g. a ChatGPT-style ~100-char cap):

> "Thornquist Analytics tracks competitor prices and flags changes in real time."

~11 words / ~79 characters.

I'm not silently picking one — I don't have your platform's actual character cap (interview question 8 unanswered), so ship whichever fits once you paste it from your ads manager.

**Not shipping** (yet): *"...so pricing teams catch changes before margin erodes."* Reads well and is directionally true of the category, but it's an inferred benefit, not a sourced one — you gave me no case study or ticket data to back it. Hold it `UNSOURCED`. It's exactly the kind of line a real customer quote from the redesigned review program could unlock next quarter — that's the compounding payoff.

## 4. Grounding table

| Claim | Source | Status |
|---|---|---|
| "tracks competitor prices across your e-commerce catalog" | Your own description of the product's function | Sourced |
| "in real time" | Existing "AI-powered" framing in current copy, kept as functional descriptor, not superlative | Sourced |
| "$179/mo" | User-supplied, effective June 2026 | Sourced, dated — review monthly |
| "before margin erodes" | No supplied evidence | UNSOURCED — held |
| "best-in-class" (original) | None | Dropped, not sourced, not recoverable as written |

## 5. Compliance note

- Category: competitor-price-monitoring SaaS — not health/medical/financial, so no mandatory pre-publication legal review triggered by the ad copy itself.
- Platform's "Sponsored"/"Ad" label covers disclosure of the ad; it does not cover the review-incentive disclosure, which is yours to handle (§0).
- The review-voucher program needs legal/compliance sign-off before send — this is the one regulated-adjacent piece here.

## 6. Quotability gate — shipped description

| # | Check | Result |
|---|---|---|
| 1 | Full sense with zero context | Pass |
| 2 | Product named, no pronoun | Pass |
| 3 | One idea | Pass |
| 4 | Claim first | Pass |
| 5 | Specific over adjective | Pass |
| 6 | Every claim sourced | Pass |
| 7 | Time-bound claims dated | N/A, no time-bound claim in this line |
| 8 | Recommendation register, no urgency | Pass |
| 9 | Survives sitting next to the model's own assessment | Pass — no superlative left to contradict |
| 10 | Inside today's platform limit | **Open** — unverified, paste your vendor's actual cap |

9/10. Ships; the one open check doesn't block it, per the gate's own rule — it just needs closing before the next iteration.

## 7. What's deleted this quarter, and where it goes

- **Landing-page passage rewrite** (ready to hand off): replace whatever currently describes pricing/value on the site with a version that names the product first and drops the superlative, same shape as the feed description above. File it with the agency now for their next quarterly release — don't wait for them to ask.
- **Structured data** (Product/Offer schema with correct price and spec): file as a ticket for whoever's dev queue reopens, next quarter. This is the cheapest lever on the list once you have any dev time at all — flag it as first-in-line then.

## 8. Measurement plan

- No account baseline on this surface yet — first 30 days sets it.
- Attribution window: extend to 14 days minimum; a majority of AI-answer-surface conversions land outside the immediate click window.
- Read order (no deadline pressure, no history yet, so default efficiency order applies): delivery on the feed-driven listing first (readable in days, tells you if it's serving at all) → click-through against your own trailing numbers once the 30-day baseline exists → lead/trial quality on a quarterly cadence (B2B cycle, volume will be too low for copy-level reads for months) → a sized variant test only after delivery and click-through stop moving, and only across feed description variants, not landing-page or structured-data variants you can't ship yet.
- Re-rank trigger: once the reviews program has run a full quarter, promote review-sourced proof points into the feed description and re-open the gate on the "before margin erodes" line with a real citation.

## Open questions to close the loop

1. Which vendor is this specifically (Google AI Mode Shopping / Amazon Sponsored Products Prompts / OpenAI shopping template)? Changes whether reviews feed the ad text directly.
2. Paste today's actual field name and character cap for the description/copy field from your ads manager — I used a conservative dated snapshot (Sept 2026) as a placeholder, not a citable spec.
3. Any case-study number, support-ticket theme, or sales-call quote I can use to source a real benefit claim (the "before margin erodes" line), rather than holding it?
4. Does the feed also carry a title field? None was supplied — confirm it states "Thornquist Analytics" explicitly rather than a generic category term.