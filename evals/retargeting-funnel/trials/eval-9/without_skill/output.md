Several things are wrong, and they compound each other. Ranked by impact:

**1. Meta's 365-day audience won't actually be 365 days.**
Meta caps website Custom Audience retention at **180 days**, not 365 — the setting will silently truncate. Your p80 close time (150 days) just barely fits inside that; anything beyond it falls out of the audience before the deal closes.

**2. Safari/iOS breaks the "365-day" premise entirely for 55% of your traffic.**
Safari's ITP caps JS-set first-party cookies at 7 days and blocks third-party cookies outright. So for the majority of your visitors, the pixel-based membership window is realistically ~7 days, not 180 or 365, regardless of what you configure. You're planning around a number that doesn't apply to over half your audience.

- Fix: stop relying on cookie-based retargeting alone for this segment. Use **Meta Conversions API** and **Google Enhanced Conversions / server-side tagging** with first-party identifiers (hashed email, login state). Capture emails earlier in the funnel (gated case study, calculator, newsletter) so you can build **Customer Match (Google)** and **Customer List Custom Audiences (Meta)** — these don't decay with ITP and are the only reliable way to cover a 95–150 day cycle for Safari users.

**3. One audience + one ad = ignoring the funnel.**
A day-2 visitor and a day-340 visitor get the same "book a demo" ask. For a 95-day median cycle, hitting cold traffic with a hard CTA wastes spend and trains people to tune you out. Split into at least three tiers:

- All visitors (recent, low-intent) → educational/proof content, not demo.
- Engaged (pricing, product, case study pages) → comparison/ROI content.
- High-intent (demo page viewed but not booked, repeat visits, pricing calculator used) → the actual demo CTA.

**4. No exclusions.**
Nothing suppresses people who already booked a demo, are in active sales conversations, or are existing customers. Sync CRM stage into both platforms and exclude closed-won, closed-lost-recent, and open-opportunity contacts — otherwise you're paying to annoy people your sales team is already talking to.

**5. Creative fatigue risk, amplified by your audience.**
Same ad, same pool, for up to a year → frequency burnout. Design agencies are an aesthetically unforgiving audience; stale creative reads as neglect, not just gets ignored. Set frequency caps and a creative refresh cadence (4–6 weeks) per tier.

**Bottom line:** "simple and wide" isn't actually simple — it's simple in configuration but wasteful in spend, because the tracking mechanics (Meta's 180-day hard cap, Safari's 7-day ITP cap) don't match the 365-day number you set, and a single CTA across a 95–150 day cycle mismatches buyer readiness. Minimum fix: (a) build first-party identity capture now so Safari/iOS isn't functionally unretargetable, (b) split into 3 intent tiers with staged offers, (c) add CRM-based exclusions.
