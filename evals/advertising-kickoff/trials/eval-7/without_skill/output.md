# Prioritized growth plan — Aldergate Health

Your instinct to start with negative keywords and bid tweaks is reasonable but misplaced as the *first* move. Here's why, and what to do instead.

## The core problem with "quick wins" first

Bid tweaks and negative keywords optimize toward whatever conversion event you're currently tracking. Your only tracking is the Meta pixel and Google tag — neither connected to the EHR or billing. That means:

- You don't know if a "conversion" is a real patient or a bounce that filled a form and never showed up.
- Both platforms' auto-bidding algorithms are chasing that same unverified signal, at $35k/month.
- Tightening bids and negatives now just optimizes harder toward a number that might not correlate with revenue.

Fix the measurement before you fix the spend allocation. Otherwise you're sharpening the wrong knife.

## Priority 0 — Compliance audit on pixel data, this week

Given a state AG inquiry last year, this is the actual fire, not a growth item.

- Meta pixel and Google tag on a telehealth site routinely leak PHI-adjacent signals: URL paths ("/depression-therapy/thank-you"), page titles, form field values, button text tied to condition or appointment type.
- This is exactly the fact pattern behind the BetterHelp/GoodRx/Cerebral FTC and state AG actions (Health Breach Notification Rule, unauthorized disclosure to Meta/Google).
- **Action**: get legal and someone technical to audit every pixel event and every parameter being passed, before touching bids. Pause or redact any event that could carry health condition, treatment type, or appointment specifics. Do this before any other change on this list — it's the one item where inaction compounds regulatory exposure daily.

## Priority 1 — Close the loop between ad spend and real outcomes

You're flying on pixel data alone. Fix this without needing a full EHR integration:

- Stand up server-side conversion tracking (Meta CAPI, Google Enhanced Conversions) using hashed, non-clinical identifiers only (email/phone hash) — improves match rate and survives iOS/cookie signal loss, and is *more* private than client-side pixel firing, which helps your compliance posture too.
- Get one non-PHI status flag out of your intake/scheduling system — "qualified lead" or "booked appointment" — even a manual CSV export weekly. Feed that back as an offline conversion event. You don't need billing data; a binary "did this become a real appointment" signal is enough to redirect both platforms' optimization.
- This is the single highest-leverage move on the list — it improves every dollar of the $35k, not just the next campaign tweak.

## Priority 2 — Negative keywords and bid tweaks (do these, in parallel)

Legitimate, low-risk, no legal review needed. Fine to start now alongside P0/P1, just don't treat them as the strategy — they're maintenance.

- Search term report audit for Google — cut obvious junk (jobseekers, "free," competitor brand confusion, adjacent conditions you don't treat).
- Cap or pause on Meta placements/audiences with high spend and no matching qualified-lead signal once P1 data starts flowing.

## Priority 3 — Landing page conversion rate, not ad creative

Your designer left, so protect this lane — it needs no new visual creative, and it compounds without extra spend.

- Copy, form length, trust signals (credentials, state licensing, insurance logos), page speed — all legal-reviewable text/structure changes, no design resource required.
- Every point of CVR improvement here is equivalent to a bid discount across your whole $35k, and it's the one lever unaffected by the design gap.

## Priority 4 — Creative fatigue risk, mitigate without a designer

A quarter with zero new creative on Meta specifically risks real decay (frequency-driven CTR/CPA erosion).

- Recombine existing approved assets: new crops, captions, CTAs, headline variants — copy-only changes, fast to get through legal since the underlying visual is already approved.
- Consider a short-term freelance or agency contractor for creative refresh — cheaper than the CPA drift you'll otherwise eat over 3 months.
- Flag to leadership now that this is a real cost of the designer gap, not a hypothetical.

## Priority 5 — Health-vertical ad policy check

- Confirm your Meta account isn't tripping Special Ad Category-style restrictions (health/wellness targeting limits reduce optimization and audience size on their own — this can look like "bad performance" when it's actually a policy constraint).
- Same check on Google's personalized health ads policy for RLSA/remarketing lists tied to condition-specific landing pages.

## Priority 6 — Build a lightweight legal-review lane for tracking changes

Since legal reviews everything, a fully ad hoc review cycle will throttle P1 and P0. Propose a fast-track checklist (what data fields, what's hashed, what's not PHI) so future pixel/CAPI changes don't each take weeks — this is what makes the rest of this plan sustainable past this one review cycle.

---

**Sequence**: P0 this week (compliance can't wait). P1 next, it's your biggest lever. P2 in parallel — cheap, no downside. P3 as your no-designer-needed growth lane. P4 as a stopgap for the creative gap. P5–P6 as you have bandwidth.