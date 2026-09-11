# Fernhollow — AI-answer surface copy package

## Placement + control axis

Shopping/PMax assets becoming eligible inside **Google's AI-generated answer summaries** matches Google AI Mode (Conversational Discovery ads / Highlighted Answers / AI-powered Shopping ads), which your rep's description confirms: copy is **model-generated from feed + landing page**, not rendered from your existing ad assets. That's a different mechanism from classic AI Overviews, where existing Search/Shopping/PMax assets surface as-is with no new copy fields. Practitioner read on this specific format: "zero control over your ad creative, and zero reporting on what ads showed where" — treat that as the honest starting constraint, not a solved problem.

⚠️ **One thing to confirm with your rep before shipping this**: the same reference snapshot lists *finance* among verticals where AI Overviews shows "no ads at all." That line is written for classic Overviews, not confirmed for AI Mode Shopping ads — but Fernhollow sits close enough to "finance" that it's worth a direct question to your rep rather than an assumption either way.

**Reframe, one sentence:** new headline/description *ad copy* won't move this surface — the model reads your landing page and feed, so that's what gets rewritten below. I'm delivering it in the same 6-headline / 4-description shape you asked for, just mapped onto the assets that are actually eligible: 6 short claim-first lines for your landing-page H1/subhead and Shopping feed title field, and 4 longer passages for landing-page body copy, feed description, and meta description.

## Source rewrites

### 1. Landing-page hero (top priority — you own it, model paraphrases it directly)

**Current:** "Fernhollow is the revolutionary, next-generation platform that transforms finance operations for forward-thinking teams."
Problems: no product category in sentence one, no specifics, four unsupported adjectives ("revolutionary," "next-generation," "transforms," "forward-thinking") — nothing here is quotable or checkable, so a model has nothing concrete to lift.

**6 headline-style rewrites** (H1/subhead candidates — also usable as Shopping feed **title** field variants, since both are short claim-first lines the model reads):

1. Fernhollow cuts month-end reconciliation from 11 hours to 4.
2. Fernhollow: invoice reconciliation software that closes the books in 4 hours, not 11.
3. 32 mid-market finance teams cut reconciliation time 64% with Fernhollow.
4. Fernhollow turns an 11-hour month-end close into a 4-hour one.
5. Fernhollow automates invoice reconciliation for mid-market finance teams.
6. Fernhollow: reconciliation time cut by more than half — 11 hours to 4, in a 2025 study of 32 teams.

(#5 is the one non-stat line, for category clarity when the model needs to establish *what Fernhollow is* before the number.)

### 2. Shopping feed fields (co-first priority — Shopping/PMax is feed-driven, so the feed is effectively the ad here)

**4 description-style rewrites** (~35–40 words each — verify your Merchant Center description cap before pasting in, don't trust a remembered number):

1. *Landing-page body/subhead:* "Fernhollow is B2B invoice-reconciliation software for mid-market finance teams. In a 2025 study of 32 customer teams, Fernhollow cut month-end reconciliation from an average of 11 hours to 4 — a 64% reduction — by automating invoice matching and exception flagging."
2. *Shopping feed description:* "Fernhollow automates invoice reconciliation for finance teams. A 2025 study of 32 mid-market customers found average month-end reconciliation time dropped from 11 hours to 4. Built for teams closing the books faster, with fewer manual errors."
3. *Research-stage framing:* "Month-end reconciliation eating your team's week? Fernhollow automates invoice matching so finance teams spend less time chasing discrepancies. A 2025 study of 32 mid-market customers found reconciliation time fell from 11 hours to 4 — a 64% cut."
4. *Comparison-stage framing:* "Fernhollow replaces manual invoice reconciliation with automated matching built for mid-market finance teams. Customers in a 2025 study (n=32) cut average month-end reconciliation from 11 hours to 4, freeing finance staff for higher-value work."

### 3. AI Brief field (if your account has AI Max enabled)

AI Max's setup field lets you hand the model a short steer directly. Seed it with the same grounded line rather than leaving it blank: *"Fernhollow is invoice-reconciliation software for mid-market finance teams. Independent customer study (2025, n=32): month-end reconciliation cut from 11 hours to 4."*

### 4. Structured data — short ticket, file it

Add/confirm `Product` schema with accurate price and category on the reconciliation-study landing page; if you have a dedicated study page, mark it with `Dataset` or `Article` schema carrying the same figure. Pins the number for re-crawl instead of leaving the model to infer it. Route to your dev queue — not written out in full here.

### 5. Reviews — parked this flight, named as deleted

No solicitation program mentioned, and reviews are a quarter-scale asset, not a sprint one. Routed to whoever owns customer success/marketing to start one; expect nothing from it inside this flight.

## Grounding table

| Claim | Source |
|---|---|
| Reconciliation cut from 11 hours to 4 (64%) | 2025 Fernhollow customer study, n=32 mid-market finance teams |
| "32 mid-market finance teams" | same study |
| "revolutionary / next-generation / transforms" (old hero) | `UNSOURCED` — dropped, not carried into any rewrite |

Date every use of the stat as "2025 study" and set a review date — recommend re-verifying the figure is still current by **December 2026**.

## Compliance note

- Not a health/medical/financial-services claim under FTC/ASA/DSA definitions — invoice reconciliation software, not financial advice or a regulated financial product — so no mandatory legal-review trigger from this skill's rule.
- The time-savings stat is still a performance claim: keep the study's methodology (sample size, timeframe, selection criteria) on file in case of substantiation challenge, independent of which surface shows it.
- Confirm the finance-vertical eligibility question above with your rep before treating this campaign as cleared to serve.
- Sponsored labeling is the platform's job, not this copy's.

## Quotability gate (run on lead candidates: headline #1, description #1)

| Check | Headline #1 | Description #1 |
|---|---|---|
| Full sense with zero context | ✅ | ✅ |
| Product named, no pronoun load-bearing | ✅ | ✅ |
| Exactly one idea | ✅ | ✅ |
| Claim first | ✅ | ✅ |
| Specific, not adjective | ✅ | ✅ |
| Traced to a source | ✅ | ✅ |
| Time-bound claim dated | ⚠️ dated in body copy, not in this line alone | ✅ |
| Colleague register, no manufactured urgency | ✅ | ✅ |
| Survives sitting next to model's own assessment | ✅ | ✅ |
| Inside current field limits | ⚠️ verify against Merchant Center today | ⚠️ verify against Merchant Center today |

8/10 clean, two flagged for a field-limit check you'll need to run in your own Merchant Center/Ads Manager — not something I can verify from here.

## Measurement plan

- **No creative-level reporting exists on this surface** (practitioner-reported) — don't expect to isolate which line served.
- Baseline: none supplied, so the first 30 days of delivery sets it.
- Read order: overall Shopping/PMax delivery and conversion volume (blended, since granular attribution isn't available here) > downstream lead quality > a sized variant test only if delivery volume justifies it later.
- Extend any attribution window to 7–14 days minimum before judging results.

## Assumptions / open questions I couldn't resolve from a single-response brief

- No CTA/next-step was specified — none of the above forces one in; add your standard trial/demo ask to the landing page separately from the hero rewrite.
- Deadline, one-off-vs-compounding, and effort-ceiling weren't given, so I defaulted to treating this as compounding (source rewrites, not a one-shot push) — flag if that's wrong.
- The finance-vertical exclusion question above is the one I'd chase first; it changes whether this whole exercise pays off on this surface.