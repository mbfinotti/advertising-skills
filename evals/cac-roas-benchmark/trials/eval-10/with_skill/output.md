# Spend Health Check — Verdala, Trailing 6 Months

## Headline

- **Blended spend efficiency (CAC + MER): ⚠️ Insufficient evidence** — rung 1 (break-even) can't be built without contribution margin. Rung 2 (own history) is solid and shows a flat, stable trend — no deterioration, but that's not a health verdict, it's a trend read.

The honest Monday-morning line: **we don't yet know if $400 blended CAC is profitable — but it's been boringly stable for 6 months, which is itself useful information.**

## Definitions record

| Field                   | Value                                                                                                                                                                                                                                                                                                                                              |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Model                   | B2B, property-management CRM                                                                                                                                                                                                                                                                                                                       |
| Windows                 | 6 consecutive monthly periods, same "blended CAC = total marketing spend ÷ all new customers" definition throughout (your stated consistent definition — matches this skill's Blended CAC formula exactly)                                                                                                                                         |
| Spend lines             | Total marketing spend (blended) — media/agency/tooling split not broken out, but immaterial to blended CAC itself                                                                                                                                                                                                                                  |
| New-customer basis      | "All new customers" per your formula — renewals/reactivations exclusion not separately confirmed; flag for finance to verify once available                                                                                                                                                                                                        |
| Revenue basis           | Not specified (MER numerator source — gross/net, billing vs platform)                                                                                                                                                                                                                                                                              |
| **Contribution margin** | **Unknown — finance mid-audit, unavailable until next month**                                                                                                                                                                                                                                                                                      |
| History                 | 6 periods, consistent definition — inside this skill's 4–8 period recommendation                                                                                                                                                                                                                                                                   |
| Lag vs window           | Sales cycle ~5 weeks vs monthly windows — a ~1-week overhang exists (this month's blended CAC pairs some of this month's spend against next month's closes). Applied consistently across all 6 months, so it's a minor, systematic offset, not a disqualifying one — you called this "covered," and I'm accepting that with this caveat on record. |

**Deleted from this run (Friday deadline):** fully-loaded CAC, marginal CAC, contribution-margin ROAS/POAS, cohort (closed-won) CAC — all need finance or CRM-stage data that isn't available before the exec review.

**Starved by the deadline, promote next period:** cohort CAC / cost-per-closed-won at 90–180 day maturity. This skill calls it "the only honest read of a lagging B2B business" — worth the one-quarter wait once this becomes a standing monthly check rather than a one-off.

## Metric table

_Assuming left-to-right = oldest → most recent; confirm with whoever pulled the numbers, since it flips which end is "current." It doesn't change the read below either way — both directions land inside the same tight, flat band._

| Metric      | Variant                                   | M1   | M2   | M3   | M4   | M5   | M6   | Mean    | Window            | Source    |
| ----------- | ----------------------------------------- | ---- | ---- | ---- | ---- | ---- | ---- | ------- | ----------------- | --------- |
| Blended CAC | total marketing spend ÷ all new customers | $410 | $395 | $402 | $398 | $405 | $400 | $401.67 | 6 monthly periods | your data |
| MER         | total revenue ÷ total marketing spend     | 3.1  | 3.2  | 3.1  | 3.15 | 3.1  | 3.1  | 3.125   | 6 monthly periods | your data |

Both series sit in a ~3–4% band around their mean, non-monotonic (up/down/up/down), no consecutive-period deterioration or improvement in either direction. Mix-shift check couldn't be run (no channel split provided) — flat blended aggregates are a good sign against a hidden mix shift, but not proof of one's absence.

## Comparison ladder

1. **Break-even — not computable.** Needs contribution margin (or gross margin per customer). This is the single blocking gap; finance can't produce it until the audit clears next month. Gap to break-even: unknown, could be large in either direction.

2. **Own history — computable, flat.** Blended CAC: $395–$410, no trend. MER: 3.1–3.2, no trend. Direction: stable. This is real evidence, but it answers "is anything changing," not "is this profitable."

3. **External — context only, and weak here:**
   - B2B SaaS CAC $239 vs. real estate CAC $791 (First Page Sage, Jan 2022–Aug 2025 agency-client data, self-disclosed 75% organic-weighted). Two plausible vertical proxies for a property-management CRM, 3.3x apart — that spread alone shows why picking either as "the" benchmark would be arbitrary. Neither matches your spend mix or vertical closely enough to anchor a verdict.
   - CAC payback medians — 18mo (Benchmarkit 2025, n=583, self-reported), 16mo (Aleph×Benchmarkit 2026, n=198/342), 20mo (KeyBanc) — presented as a conflict, not averaged. **Can't even be compared to Verdala's own payback**, because payback needs the same missing gross-margin figure.
   - MER folklore "4–8 at scale" (Taylor Holiday/CTC) and "4:1 ROAS" — both unvalidated heuristics, both B2C/DTC in origin, and 4:1 is just break-even at a 25% margin retroactively declared universal. Verdala's real break-even could be well below or above 25% margin — we don't know, which is exactly why this can't be used to judge the 3.1–3.2 figure.

## Verdict and evidence gate

Gate: variant established ✅ · margin known ❌ (rung 1 blocked) · window ≥ lag ✅ (minor, consistent overhang, accepted) · channels complete ✅ (single blended total, nothing renormalized or zero-filled)

**Verdict: Insufficient evidence** to call spend healthy, watch, or unhealthy. Every one of those three states is defined against break-even in this skill — and break-even is unknowable without contribution margin. Six months of flat CAC/MER is real, useful, and says "nothing is trending worse" — it does not say "this spend is profitable." Treating "stable" as "healthy" here would be judging rung 3-adjacent folklore or a bare trend read as if it were a verdict, which is the exact failure this check exists to prevent.

**What unlocks a real verdict:** contribution margin (or gross margin + variable cost per customer) from finance, once the audit clears next month. That's an hour of work once it exists — this isn't a heavy ask, it's a blocked one.

## Folklore appendix

Likely to come up in the room — put it on the table now rather than after someone quotes it:

| Quoted rule           | Origin                                                                                              | Worth here                                                                                                                                                                |
| --------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MER > 4, 5–8 at scale | Taylor Holiday, CTC, 2022 — stated heuristic, never measured across a sample, DTC-ecommerce context | Verdala's 3.1–3.2 sits below it, but this rule wasn't built for a B2B SaaS CRM and has no traceable evidence base. Don't let it stand in for the missing break-even.      |
| 4:1 ROAS              | No traceable author, often misattributed to Nielsen                                                 | It's break-even at exactly a 25% contribution margin, nothing more. We don't know Verdala's margin, so this number is arithmetic about a hypothetical business, not ours. |

## Handoffs

- Contribution margin from finance (next month) → re-run this check for a real rung-1 verdict. Not a skill handoff, just the blocking dependency.
- Once margin lands and the verdict resolves to unhealthy → `mbfinotti/advertising-skills@ad-spend-guardrails` (set the policy threshold) and `@ad-spend-allocation` (act on it). Premature now — there's no verdict to act on yet.
- If this becomes a standing monthly check → build cohort/closed-won CAC (90–180 day maturity) alongside blended, per the B2B promotion note above.
- No attribution conflict raised, no diagnostic anomaly in the flat trend → `@ad-attribution-gap` and `@ad-account-diagnostic` not triggered this run.

---

**For Monday, in one sentence:** _"Spend efficiency has been flat and stable for six straight months — no warning signs in the trend — but we can't certify it as healthy or unhealthy until finance gives us contribution margin next month; anyone quoting a 4:1 or MER-of-4 target against these numbers is quoting a DTC ecommerce rule of thumb, not a fact about Verdala."_
