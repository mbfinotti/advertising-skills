# Corvid Analytics — LinkedIn Lookalike Seed: Setup Walkthrough

## First: two assumptions in your framing are going to bite you

**"700 > 300 so we're fine" — no.** LinkedIn's 300 minimum is a **matched** count, not a row count. Every list shrinks on ingest: LinkedIn matches work-email contact lists at roughly **30–40%** (LinkedIn Help + practitioner data). Run the math:

- 700 rows × 30–40% match = **~210–280 matched people**
- Floor: **300 matched**
- **Fails, across the entire documented range** — not a marginal case.

LinkedIn's own recommendation reinforces this independently: they suggest uploading **10,000+ emails** to _reliably_ clear 300 matched. 700 is well under that even before you touch the match-rate math.

(Side note, unprompted but worth flagging: "lookalike" is the pre-Feb-2024 name. LinkedIn sunset Lookalike Audiences and replaced them with **Predictive Audiences** — same 300-matched floor, max 30 per ad account. If any deck or brief in your org still says "Lookalike," it's stale.)

**"I can throw in the 6,000 MQLs" — don't, at least not as a default move.** This skill's source ranking is explicit: **seed from closed-won, not MQLs** — an all-MQL top-up is the lowest-value, last-resort source on the entire ranked list, ranked below the seed you already have. You already did the hard part correctly (closed-won only, not funnel-wide). Diluting it with 6,000 unqualified-to-buy contacts is the classic "pad to hit the minimum" trap: it would probably numerically clear 300, but it teaches LinkedIn's model "person who filled a form," not "person who signs a $42K contract" — homogeneity is what a lookalike is actually selling, and this move destroys it. If a floor gap remains after the levers below, the correct downgrade is **SQL-only**, never raw MQL.

## Hard stop before any of this touches LinkedIn: the privacy gate

I don't have answers to these yet, and none of them are optional:

- Documented lawful basis/consent for uploading this contact list to an ad platform (hashing ≠ anonymization — SHA-256 is pseudonymous, consent obligations survive it).
- Are any of the 700 EEA/UK-based? If so, need a documented lawful basis specific to that.
- CCPA/CPRA opt-out and Global Privacy Control signals honored before export?
- Opt-outs/deletions enforced in the warehouse, once, before any platform sync?
- LinkedIn customer-list terms accepted for this specific ad account?

**Everything past this point is provisional until you confirm these.** No amount of selection quality substitutes for missing consent basis.

## Open questions I need before finalizing a spec

1. Is 700 your **entire** closed-won history, or a time-windowed export (e.g., trailing 12 months)? This decides whether "widen the recency window" is even available as a lever.
2. Per-row identifiers beyond work email — phone, name, title? (Multiple identifiers per row lift match rate; email-only is the weakest case.)
3. Does a real per-account contract value exist (varies by deal, not just the $42K average), so this could run as a **value-based** seed instead of flat?
4. Any refunders/churned/non-payment accounts, internal test accounts, or reseller/channel deals sitting inside the 700? These need stripping.
5. Manual CSV acceptable to start, or do you want this as a recurring/automated CRM→LinkedIn sync?
6. Hard launch date, and current acquired-customer CPA/CAC + cohort LTV baseline (needed to grade the seed later — if there's no baseline today, the first cohort becomes the baseline run, not a graded one).

## The fallback ladder (because the floor fails as computed)

Never loosen selection quality first — walk the ladder:

| Rung                          | Applies here?             | Why                                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1 — Enrich identifiers**    | **Likely your fix**       | Identity resolution appends personal emails/phones, and/or expands each closed-won _account_ into multiple buying-committee contacts via title/seniority/function. This is the standard B2B move precisely because you're in the pattern where the cheap rungs are structurally empty (see below). Cost: real — vendor selection, DPA, security review, a week+ of coordination before a row moves. |
| 2 — Widen recency window      | Probably empty            | Only works if #1 above says your 700 isn't already all-time. If it is (typical for "we exported closed-won"), there's nothing left to widen.                                                                                                                                                                                                                                                        |
| 3 — Stack an adjacent segment | Probably empty            | The only adjacent segments for closed-won are lost deals or MQLs — both forbidden as a first move for exactly the dilution reason above.                                                                                                                                                                                                                                                            |
| 4 — Switch source             | Last resort, not a top-up | SQL-only (never all-MQL) if 1–3 are genuinely exhausted. Lowest value on the ranking — changes what the model learns.                                                                                                                                                                                                                                                                               |

This is structurally the same shape as a documented case: a 410-contact B2B closed-won list matched ~144 people natively (fails 300), enrichment took it to ~1,240 contacts at ~70% match → ~868 matched, clears comfortably. Your 700 at $42K ACV is the same pattern at slightly larger scale — enrichment is very likely to clear 300 outright, probably without needing rungs 2–4 at all.

## Identifier prep (do this regardless of the ladder outcome)

- Lowercase + trim all emails.
- If you can join phone or name from the CRM, add them — multiple identifiers per row is the single biggest lever after enrichment itself.
- **Never pre-hash the file** — LinkedIn hashes on ingest; a salted/pre-hashed file matches nothing.
- Negative-selection pass before export: strip refunders/churned/non-payment accounts, internal/test accounts, employees, and any reseller or channel-partner deals sitting in the 700.

## Provisional Seed Specification (BLOCKED — do not upload yet)

```
SEED SPECIFICATION - corvid-closed-won-v1 (DRAFT), 2026-09-12
platform        : LinkedIn (contact list -> Predictive Audience) | audience type: predictive
definition      : closed-won CRM opportunities, work email only, [recency window: TBD - need Q1]
value column    : none yet - TBD pending Q3 (per-account contract value vs flat $42K avg)
row count       : 700 | identifiers/row: work email only (single identifier - risk flagged)
expected match  : 30-40% (LinkedIn work-email contact list band, practitioner + Help Center)
effective seed  : 700 x 0.30-0.40 = ~210-280 matched vs floor 300 -> FAILS across entire band
fallback used   : ladder rung 1 (identity enrichment + account-to-contact expansion) - projected
                  needed; exact post-enrichment count pending vendor match test
exclusions      : TBD - negative-selection pass not yet confirmed run (Q4)
consent basis   : BLOCKED - lawful basis, EEA exposure, CCPA/GPC, LinkedIn terms acceptance
                  all unconfirmed (see privacy gate above)
refresh         : TBD (Q5 - manual CSV vs automated sync)
measurement     : TBD (Q6 - no baseline CPA/CAC or cohort LTV given yet)
re-check        : cannot set - depends on launch date (Q6) and B2B sales-cycle maturity (~2 quarters
                  typical; early reads should be limited to match quality/engagement, not cohort LTV)
```

**Do not emit the final, upload-ready version of this spec until:** the consent items are confirmed, and you've told me whether 700 is all-time or windowed (decides if rung 2 is live), whether phone/name exist in the CRM, and whether you want this value-based off real per-account contract size.

**Next step:** answer Q1–Q6 above (one at a time is fine, or all at once), and separately loop in whoever owns privacy/legal on the consent-gate items — that can run in parallel with the enrichment-vendor conversation, since rung 1 needs its own DPA regardless.
