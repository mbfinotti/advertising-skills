# Tallgrass Analytics — Ad Audience Targeting Plan

**Window:** today (Sep 12) → board readout Oct 17 (5 weeks, hard date). **Budget:** $14k/mo. **Execution:** you, ~4h/week, zero legal/privacy review available.

## 1. ICP summary

**Attributes** (what's true) — mid-size grocery chain; buyer is a committee (supply-chain/ops lead as champion, IT/analytics as technical evaluator, finance/exec as budget sign-off — inferred from the product category and the hiring signal below, not yet verified against your CRM's actual contact roles: check this in week 1). Evidence source: your product description + CRM.

**Signals** (why now), evidence-graded per freshness:

| List                                         | Age        | Verdict                                                                                                                                                                                                                                                           |
| -------------------------------------------- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 28 chains posting supply-chain analyst roles | <3 weeks   | 🎯 **Real signal.** Inside the ~90-day window — active hiring for the exact function that buys this software is a genuine "reach first" trigger.                                                                                                                  |
| 45 chains that raised money / got acquired   | 4-6 months | ⚠️ **Stale as a signal, still valid as an attribute.** Past ~90 days it no longer tells you who to reach _first_ — it tells you who can _afford to buy_. Use it to qualify, not to prioritize. Don't message these 45 as "we saw your raise"; that window closed. |

Other assets: CRM (3,100 contacts, mixed customer/prospect), pixel traffic (25k visits/mo, solid).

## 2. Tier plan

Two answers re-ranked this from the skill's default:

- **Zero privacy review, ever** deletes any tier needing identifiable data uploaded to an ad platform. That's not a demotion, it's a removal — nobody exists to sign off on a DPA or a consent question, so those tiers aren't options for this account.
- **Hard 5-week date** promotes tiers that read fast (retargeting, evidence-backed lists) and kills anything needing a full learning cycle.

**Deleted, not demoted:**

| Tier                                                     | Why deleted                                                                                                                                                                                         | What would bring it back                                                              |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| First-party custom (CRM upload as identifiable audience) | 3,100 people's names/emails uploaded to an ad platform with nobody to review the data-handling question. This is the one place "just be careful" isn't a substitute for review.                     | Legal/privacy support, even part-time or fractional.                                  |
| Lookalike seeded from CRM customers                      | Same reason — it's built from the same identifiable list.                                                                                                                                           | Same.                                                                                 |
| Cold broad/algorithmic                                   | Addressable universe (mid-size grocery chains) is a few thousand accounts worldwide — too small to ever clear a learning threshold; the algorithm would spend your budget finding irrelevant reach. | Universe widens (e.g. you expand targeting to all grocery/retail, not just mid-size). |
| Interest & affinity                                      | Weakest tier on every axis, and your 4h/week doesn't cover testing something this unlikely to pay off in 5 weeks.                                                                                   | Extra budget/time after the raise, if you want a cheap fourth test.                   |

**Funded, in the order to build them:**

| Tier                                     | Defining signal / evidence                                                                                                                                                                                                                                        | Est. size                                                                            | Budget                             | Success criterion                                                                                                                                                    |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Retargeting pool**                     | 25k site visits/mo, graded by recency × page depth (pricing/demo pages weighted up)                                                                                                                                                                               | Several thousand visitors within ~1 week — clears any platform floor easily          | **$3,500/mo (25%)**                | Fastest CPA read; lowest cost-per-meeting. Expect this to look artificially great — flag to the board as proof-of-funnel, not proof-of-scale (see Compliance notes). |
| **Signal-list / company-list targeting** | 28 hiring-signal companies (priority), + 45 funding/M&A companies (included, deprioritized — attribute not trigger), expanded by job function (ops/supply-chain/analytics, director+) to clear platform floor. **Company names/domains only — no personal data.** | 73 core accounts, expanded to a few hundred reachable members via function targeting | **$6,300/mo (45%)**                | Highest priority spend — this is your only evidence-backed "why now" tier. Track meetings booked from the named 73 vs. everything else.                              |
| **Behavioral / in-market**               | Platform-native industry (grocery/retail) + function targeting, nothing uploaded                                                                                                                                                                                  | Broad enough to clear floor on its own                                               | **$2,800/mo (20%)**                | Refill layer — keeps the pipeline from running dry once the 73-account list saturates (it will, fast, at this budget).                                               |
| **Lookalike (from pixel pool, not CRM)** | Built off the retargeting pool once it has ~1 week of traffic — not a customer seed, so it's not deleted by the privacy rule                                                                                                                                      | Depends on platform minimum; verify before launch                                    | **$1,400/mo (10%)**, starts week 2 | Hold tier — 5 weeks is short for this to mature; fund it lightly and don't expect a verdict by the board date.                                                       |

**Structural note:** I don't have your target CPA/cost-per-meeting, so I can't compute the exact daily funding floor the skill calls for. Set that number before Monday — even a rough internal CAC target — or you can't tell "promote" from "hold" later. At $14k/mo split this way, each funded tier still clears $2,800+/mo, which comfortably clears typical B2B platform minimums; verify against current LinkedIn Campaign Manager numbers before you launch, since floors move without notice.

## 3. Exclusion matrix

- **Everywhere:** exclude existing customers. Do this at the **company-domain level only**, derived from CRM — never upload personal contact data. Build one static domain-exclusion list, apply to all three prospecting tiers.
- **Retargeting pool** (highest intent of the funded tiers) excluded from Company-List and Behavioral, so you're not bidding against yourself for the same visitor.
- **Company-List** excluded from Behavioral, once Behavioral is live — the 73 accounts should only ever be reached through the higher-intent tier.
- Check overlap % between funded tiers before adding the lookalike in week 2 (skill's thresholds: <10% ignore, 10-30% monitor, 30-50% add exclusion, >50% merge). With only 73 core accounts, watch that exclusions don't push the Company-List tier below the platform floor — merge into Behavioral rather than stack more exclusions if that happens.

## 4. Test sequence (4h/week budget)

Given the hard date, don't stagger the fast tiers over weeks — stand them up together, because standup cost is the same either way (~1 hour each) and waiting only shrinks your read window.

| Week              | Action                                                                                                                                                                                                                                                                     | Est. effort               |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| **1** (Sep 15-19) | Launch Retargeting first — it's live day one and needs the lead time to fill. Same week: build and launch Company-List (28-company hiring list gets priority framing in the ad copy/sequencing over the 45-company list). Behavioral if time allows, else slips to week 2. | ~3.5-4h — at your ceiling |
| **2** (Sep 22-26) | Launch Lookalike off the now-week-old retargeting pool. Overlap audit before it goes live. Behavioral live by now if it slipped. First weekly floor/performance check.                                                                                                     | ~1h                       |
| **3-4**           | Weekly floor/performance check only. Scale any tier beating target by ~20%, never more in one jump.                                                                                                                                                                        | ~1h/week                  |
| **5** (Oct 13-17) | Compile results: cost-per-meeting by tier, pipeline sourced, promote/hold/kill call per tier. This is the board deck.                                                                                                                                                      | ~1-2h                     |

Promote/hold/kill, decided per tier at week 5: **promote** if it beats your (still-to-be-set) target CPA — scale ~20%; **hold** if within ±20% or still learning; **kill** if it's spent 2× target with results 50%+ worse than your best tier, or stalled below floor.

## 5. Compliance notes

Not a regulated category (no housing/employment/credit/financial/health/political targeting triggered) — the offer itself doesn't force restricted-targeting mode. Given zero legal support, the guardrails that matter are procedural, not case-by-case judgment calls:

- **Never** upload the CRM's personal fields (names, emails, phones) to any ad platform, full stop — that's the one call this plan takes off your plate entirely.
- Company-domain exclusion and company-list targeting are business data, not personal data, under most privacy frameworks — lower exposure, but double-check the specific platform feature you use doesn't quietly pull in contact-level targeting options beyond company name/domain before you upload (a five-minute doc check, not a legal judgment call).
- Standard cookie-consent banner on the site for the pixel — baseline hygiene, not a privacy review.
- If any EU-based chains end up in scope, expect real signal loss on retargeting numbers from consent frameworks. Don't trust pixel-only attribution as ground truth for the board deck — cross-check against actual CRM pipeline movement (aggregate counts, not the underlying personal records).

## 6. Review cadence

- Overlap audit before the lookalike tier launches (week 2).
- Tier vs. floor check weekly — this is most of your 1h/week ongoing time budget.
- Refresh the 28-company hiring list every 2-3 weeks — postings "in the last 3 weeks" age out of freshness fast. The 45-company funding list doesn't need urgent refresh since it's serving as a qualifying attribute, not a timing trigger.
- Full plan review at week 5, alongside the funding announcement.

## What runs first, in one line

**Retargeting pool, today** — it's already live via your existing pixel, needs zero new assets, and needs the lead time to fill. Build the Company-List tier (28-company hiring signal framed first, 45-company funding list included but secondary) the same week, since it's your only evidence-backed "why now" tier and the one the board readout should lean on hardest.
