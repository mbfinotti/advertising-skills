# Nestbird Personal-Loan Refinancing — Audience Targeting Plan

## Before the plan: one piece is refused, not just flagged

I won't build the "quietly exclude people whose profiles suggest they're struggling financially" layer. Two independent reasons, either one is enough:

- **Meta policy.** Financial hardship is named explicitly as a sensitive trait: it cannot be targeted on _or inferred_, even from a public signal. An exclusion list built from inferred hardship signals is the same mechanism as an inclusion list built from them, just run in reverse. Same rule, same violation.
- **Fair lending law.** This is a credit product whose whole purpose is helping over-leveraged borrowers refinance. Suppressing ad delivery to the people most likely to be in financial distress, based on inferred signals, is disparate treatment on a proxy for protected classes (income, ZIP, spending patterns all correlate with race, age, disability status). That's the exact pattern U.S. regulators pursue under ECOA/Reg B, and the exact pattern Meta itself paid to settle after a DOJ/HUD action over discriminatory delivery on housing, employment, and credit ads. "Quietly" doesn't reduce the risk, it's evidence of intent if anyone ever audits the campaign.

If the underlying worry is wasted spend on unqualified leads, that's a real problem, it just has a compliant fix: filter **after** someone applies, in underwriting, with a transparent, documented adverse-action process. That's normal lending. Filtering **before** they see the ad, based on inferred distress, is not.

Everything below is reshaped around that, and around the fact that this is a **regulated credit offer**, which changes three of your other four asks too.

## 1. ICP summary

- **Segment:** B2C, individual consumer, US personal-loan refinancing.
- **Seed evidence:** 18,000-record borrower list (first-party, owned). Good seed density for most purposes; not usable for a lookalike here (see below).
- **Category:** Credit. Meta requires declaring **Special Ad Category: Credit** for this kind of campaign — this isn't optional and isn't just a best practice, Meta enforces it algorithmically and suspends accounts that misdeclare.
- Missing to finish the numeric columns below: target CPA/ROAS, current weekly conversions, total monthly budget, hard deadline vs. open timeline. Ask before locking budget splits.

## 2. Tier table

| Tier                                                       | Defining signal                            | Status                      | Why                                                                                                                                                                                                                                                                             |
| ---------------------------------------------------------- | ------------------------------------------ | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Lookalike (1% from borrower list)                          | 18k borrowers                              | **Deleted**                 | Special Ad Category disallows lookalike-style expansion outright. Separately, even where allowed, a lookalike trained on past approvals inherits any disparity already baked into who got approved — it amplifies bias, it doesn't launder it.                                  |
| Age narrowing (28-50)                                      | requested band                             | **Deleted**                 | Special Ad Category locks age targeting to broad (18+); no custom range is available.                                                                                                                                                                                           |
| Geo narrowing (40 licensed ZIPs)                           | licensing footprint                        | **Restricted, not deleted** | Special Ad Category enforces a geographic floor (state/metro or minimum radius), it won't take an exact 40-ZIP list. Target the smallest compliant unit that covers all 40, and gate true eligibility at the application step with a licensed-states check, not at ad delivery. |
| Interest layer ("personal finance")                        | declared interest                          | **Likely deleted**          | Special Ad Category strips most detailed/interest categories for credit ads. Verify against Meta's current allowed-category list before building; assume unavailable and plan broad-plus-creative instead.                                                                      |
| Financial-hardship exclusion                               | inferred distress signals                  | **Refused**                 | See above.                                                                                                                                                                                                                                                                      |
| Cold prospecting (broad, algorithmic)                      | delivery algorithm + your conversion event | **Runs — primary tier**     | This is what Special Ad Category pushes every credit account toward: "broad-plus-creative from the start." Highest volume tier, now also your only real prospecting lever.                                                                                                      |
| First-party custom (site visitors, application-abandoners) | pixel/CAPI on your site                    | **Runs**                    | Verify Custom Audience list-upload is still permitted under current Special Ad Category rules before building — this changes without notice.                                                                                                                                    |
| Retargeting pool                                           | same visitors, graded by recency           | **Merge into first-party**  | At 18k-customer scale your retargeting pool and your site-visitor pool are close to the same audience; a split tier would sit near the size floor.                                                                                                                              |

## 3. Exclusion matrix

| Exclusion list                  | Applies to                    |
| ------------------------------- | ----------------------------- |
| Existing/current borrowers      | all prospecting tiers         |
| Employees                       | all tiers                     |
| Known fraud / chargeback list   | all tiers                     |
| ~~Inferred financial hardship~~ | not built — see refusal above |

That's the whole matrix. With lookalike and interest gone, there's no inter-tier overlap problem left to manage between funded tiers.

## 4. Test sequence

1. Stand up first-party retargeting (site visitors, application-abandoners) — fastest signal, near-zero build cost.
2. Fund broad prospecting to the learning threshold simultaneously; don't wait for retargeting to prove itself first, broad is now doing the volume job lookalike would have done.
3. Put your targeting energy into creative variants instead of audience filters — that's the standard offset when Special Ad Category removes narrowing options, and it's the one place remaining that data richness can still be spent.
4. Decision rule per tier: promote (beats target, scale ~20%/week), hold (within ±20% or still learning), kill (2× target CPA with results 50%+ worse than the other funded tier).

## 5. Compliance notes

- Declare Special Ad Category: Credit before the first impression serves.
- Route this whole plan through legal/compliance before launch — not a courtesy step, the skill and the category both require it.
- Geographic eligibility (the 40-ZIP licensing constraint) belongs in the application flow, not the ad targeting: check license status post-click, disclose clearly, don't try to solve it by narrowing who sees the ad.
- Re-verify Special Ad Category mechanics (geo floor, Custom Audience eligibility, interest-category availability) against Meta's current documentation before build — these have changed before without notice.

## 6. Open items before this is launch-ready

- Target CPA/ROAS and monthly budget (needed to size the two remaining tiers and set daily floors).
- Current weekly conversion volume (sets whether broad clears the learning threshold on its own).
- Confirm with legal whether the underwriting-stage filtering approach (suggested above as the compliant substitute for the hardship exclusion) is already how declines are handled, or needs to be built.
