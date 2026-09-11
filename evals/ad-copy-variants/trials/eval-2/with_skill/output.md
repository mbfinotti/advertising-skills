## Before the deliverable — one thing I won't do

The skill this task runs on (`ad-copy-variants`) has a hard **Grounding Rule**: never invent a claim, statistic, review, or testimonial. It's explicit that fabricated testimonials/reviews are a regulatory violation (FTC endorsement guidelines in the US, unfair commercial practices rules in the EU/France), not just a style problem — and it's right. So I'm not writing fake user counts, star ratings, "dietitian approved" badges, before/after numbers, or invented quotes, even styled to "feel real." That's the one angle family ("social proof") the skill's own angle library says to **delete, not demote**, when no cleared testimonial exists — which is your situation.

What I *can* do honestly: your landing page already carries a real, specific, substantiated claim — **"Plan your week of meals in 10 minutes."** That's a legitimate mechanism/speed angle, and it message-matches the destination page by construction. I built the set around that, plus pain (decision fatigue) and price-value ($4.99/mo), which need no fabricated proof at all.

Assumptions made (no interview run, since you asked for the finished deliverable directly) — flag any of these if wrong:
- B2C, single decision-maker, Meta/Instagram feed placement (generic "paid social" → verify char limits in your own Ads Manager before upload).
- Discrete test, default rung of 3 angles, doubled to 2 awareness-stage variants each = 6.
- No real deadline/offer exists → **urgency deleted**. No competitor named → **comparison deleted**. No RD partnership on file → **dietitian-approved endorsement deleted**.

---

## Angle bank

| Angle | Argument | Status |
|---|---|---|
| Pain | Nightly "what's for dinner" decision fatigue | **Active** |
| Mechanism (speed) | A 10-minute sit-down replaces the whole week's worth of daily decisions | **Active** — promoted; the proof asset (the 10-min claim) already exists on the landing page |
| Price-value | $4.99/mo, cheap enough to just try | **Active** |
| Social proof | "X users," star ratings, quotes | **Deleted** — no cleared testimonials, no permission on file |
| Outcome (before/after numbers) | Weight/time/money saved, quantified | **Deleted** — no measured data exists |
| Authority (dietitian approved) | Third-party credential endorsement | **Deleted** — no RD partnership or sign-off exists; using this without a named, credentialed reviewer is a false-endorsement claim |
| Comparison | Faster than [named competitor] | **Deleted** — no competitor named, no cleared comparison data |
| Urgency | Limited-time offer | **Deleted** — no real deadline supplied |

---

## Variant matrix

Destination page match: **"Plan your week of meals in 10 minutes"** (landing page headline, as supplied).

| ID | Angle | Awareness | Formula | Headline | Primary text | Description | CTA | Gate |
|---|---|---|---|---|---|---|---|---|
| `pain_pa_01_v1` | Pain | Problem-aware | PAS | Tired of "what's for dinner?" | Standing in the kitchen every night with no plan, ordering the same three takeout options again? Cartwheel plans your whole week of meals in 10 minutes — decide once, cook all week. | Meal planning, done in 10 minutes. | Sign Up | 6/6 |
| `pain_ma_01_v1` | Pain | Most-aware | 4 Us | Stop deciding dinner nightly | Plan your whole week of meals in 10 minutes, once — not five separate 6pm scrambles. Cartwheel, $4.99/month. | 10 minutes now beats 5 scrambles later. | Sign Up | 6/6 |
| `mechanism_sa_01_v1` | Mechanism (speed) | Solution-aware | Mechanism-led | Plan a week of meals in 10 min | Open Cartwheel, answer a few quick questions, and your whole week of meals is planned — done in about 10 minutes, not spread across five separate decisions. | One sitting. One week planned. | Download | 6/6 |
| `mechanism_ua_01_v1` | Mechanism (speed) | Unaware | Symptom-led | Your week, planned in 10 minutes | Most weeks, deciding what to eat eats more time than actually cooking. Cartwheel turns that into one 10-minute sit-down — then you're set for the week. | Cartwheel. A meal planning app. | Download | 6/6 |
| `value_pa_01_v1` | Price-value | Problem-aware | BAB | A week of meals for $4.99/mo | No plan = deciding dinner from scratch, every night. Cartwheel: your whole week planned in 10 minutes, for $4.99/month. | Less than one takeout order, all month. | Sign Up | 6/6 |
| `value_ma_01_v1` | Price-value | Most-aware | Offer-led | $4.99/month. Plan solved. | One small subscription, one 10-minute setup, one less thing to decide every night. Cartwheel — $4.99/month. | Try Cartwheel for $4.99/month. | Sign Up | 6/6 |

**Evidence source (all rows):** the "10 minutes" claim traces to your supplied landing page headline; the "$4.99/month" price traces to your supplied pricing. No other proof points are claimed — these are deliberately proof-free on social validation. Note `value_*` rows use "less than one takeout order" as an illustrative price anchor (not a sourced statistic) — sanity-check that framing with you before it ships, since it's a comparison even though it's not naming a competitor.

**Gate note:** all 6 pass 6/6 (generic test, one-argument-per-variant, proof traceability, surface fit *pending your Ads Manager limit check*, message match, complete labels). Verify actual Meta character limits/fold behavior in your own ads preview before launch — don't trust the ~40/~125-char figures I drafted to from memory.

---

## Handoff block

- **Tracking glossary:** mirror the ID exactly (lowercase, underscore-separated) into ad name and UTM/content parameter — e.g. `mechanism_sa_01_v1`.
- **Destination page:** "Plan your week of meals in 10 minutes" (as supplied by you).
- **Rejected angles:** social proof, outcome/before-after, authority (dietitian), comparison, urgency — all deleted above, with cause, so the next round re-tests the *constraint* (get proof) rather than re-briefing an empty bucket.
- **Next step for real proof, fast:** trigger an in-app rating prompt after a user's first completed plan (gives you a real App Store/Play badge once you clear a threshold — that's auto-updating, real, and free to run once earned); ask 3–5 beta users for a written-permission quote; if you want the dietitian angle, get an actual named RD on a light advisory basis so the claim can say "Reviewed by [Name], RD" rather than an anonymous badge.
- **Test sizing/duration/significance:** not this skill's job — hand this matrix to `ad-creative-test-plan` to size the run.