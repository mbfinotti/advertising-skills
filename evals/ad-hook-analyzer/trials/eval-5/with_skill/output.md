## Sanity-check: the Halyard Swim hook-scoring system

Both pieces of the proposed system fail, and the skill this evaluation runs on (`ad-hook-analyzer`) exists specifically to catch these two failure modes — they're named directly in its negative example and failure-mode table. Here's why, and what to do instead.

### 1. The weighted 0–100 composite score is not defensible

**What's wrong:**

- **The weights are invented.** Time-to-signal 30%, specificity 25%, sound-off 15%, qualification 10%, brand timing 10%, continuity 5%, placement 5% implies someone has measured that time-to-signal returns 6x the performance-per-unit-effort of continuity. No such measurement exists. The evidence base here is hook rate correlating **-0.19 with ROAS** (hold rate -0.10, Sweat Pants Agency, 11 brands / 3,859 ads) — slightly the _wrong_ direction. If the underlying attention metrics don't reliably predict revenue at all, a weighted blend of them doesn't either; it just launders the guess into something that looks measured.
- **A composite number is false precision.** Human hook-taxonomy and hook-quality judgment has poor inter-rater reliability — two strategists scoring the same opening will not converge on the same 74/100. A single decimal-free number invites exactly the trap in the skill's own negative example: _"Candidate B — Hook Score: 9.1/10... A: 7.4/10, C: 7.1/10"_ — flagged there as fabricated precision, point by point.
- **It will produce a specific, known bad outcome: gate overrides.** A hook can score high on the 0–100 scale by being loud, generic-curiosity, or spectacle — and _still_ fail sound-off legibility, mismatch the offer, or attract the wrong buyer. If the spreadsheet sums scores before checking gates, a gate-failing opening can out-score a gate-passing one and get funded. That's the literal mechanism behind the documented failure: _"43% hook rates and mediocre ROAS — the hook stopped the scroll but didn't qualify the right viewer or set up the offer."_ Weighting time-to-signal at 30% makes this more likely, not less, because it rewards raw stop-the-scroll power over the two dimensions (qualification, continuity) that gate against it.
- **It won't transfer.** A score built for this batch, this account, this placement will be read as comparable across batches, accounts, platforms — which the method explicitly refuses to support, because hook-rate constructions differ per platform/dashboard and nothing here validates against a denominator.

**What to do instead:** band each dimension **strong / adequate / weak** using the anchors in `scoring-rubric.md`, run the four **hard gates** first (sound-off, promise-payoff, qualification, real-variation) as pass/fail — a fail caps the candidate regardless of bands — then **force-rank pairwise** within the batch ("which of these two would I fund first, and why"). No sum, no percentage, no cross-batch number. If she wants a defensible single number eventually, the only legitimate path is: run batches, measure hook-rate rank agreement against predictions over a rolling window (5 batches, pass threshold = top pick lands top-half at least 3/5 times), and **re-derive weights from Halyard Swim's own actual winners** — never a generic default.

### 2. "7 of 8 hook types covered" is not evidence of diversity

This is the other named trap. The eight Motion "Hook Tools" (Contrarian, Identity Call-Out, Confession, Pain Agitation, Curiosity Gap, Loss Aversion, Unspoken Truth, Pattern Interrupt) are **vocabulary for describing a mechanism, not a validated, falsifiable classification system**. The categories overlap, mix psychological triggers with executional format, and the same ad can reasonably be tagged under two or three of them depending on who's tagging it — which is exactly why **human hook-taxonomy tagging has poor inter-rater reliability**. A different strategist tagging the same 9 openings could plausibly land on 5/8 or 8/8 without the batch itself changing at all.

So "we cover 7 of 8 types" doesn't prove the batch is diverse — it proves someone applied loose labels to 9 openings and 7 different labels came up. Real diversity is checked by the skill's actual **variation gate**: do the openings differ _visually_, not just in wording or in which psychological label gets attached after the fact? Two openings tagged "Confession" and "Unspoken Truth" respectively could share the identical shot and just swap the on-screen line — that's a wording-only sibling, and the gate merges it into one test cell regardless of how the taxonomy tags land. Conversely two openings both tagged "Pattern Interrupt" could be genuinely distinct concepts.

**What to do instead:** run the real-variation gate on all 9 — does each opening's _visual_, not just its copy, differ from every sibling and from anything already running? Count concept-distinct, gate-passing openings against the **3-opening shipping floor** (below 3, don't ship — with ~5% of creatives becoming winners at all, volume is what produces winners). Use the hook-type tags only to _name_ what a candidate is doing when writing the raise-the-rank note, never to score coverage.

### Bottom line for the rollout

Don't adopt the spreadsheet as designed. Before it goes to the team:

- Strip the weights and the 0–100 sum → replace with gates (pass/fail) + bands (strong/adequate/weak, unranked) + pairwise force-rank.
- Strip "7/8 types = diverse" as a validation claim → replace with the real-variation gate + 3-opening floor as the actual diversity check.
- Keep the seven dimensions and the eight hook-type labels — they're useful as inputs and vocabulary, just not as a formula or a coverage metric.

If you want, I can score Halyard Swim's actual 9-opening batch through the real workflow (gates → bands → pairwise rank) once I have the Interview answers — platform/placement, B2C/B2B, cold vs warm, the offer and what disqualifies a buyer, and what's already running.
