# Brightfell — Q4 Paid Acquisition Plan (Personas + Audience Targeting)

**Assumptions stated upfront** (no customer research exists, so these are working hypotheses to validate, not facts):

- Product = class-booking + membership management for independent gyms/studios (not big-box chains).
- Primary market = English-speaking (US/Canada default — confirm against your 22 gyms' locations before launch).
- Typical customer = 1 location, boutique format (CrossFit, yoga, pilates, boxing/MMA, HIIT, personal-training studios) rather than a 24-hour commercial gym — boutique formats have tighter class-capacity/scheduling pain, which is Brightfell's wedge.
- ACV unknown — plan assumes $79–$249/mo tiers, typical of this SaaS category. Swap in real numbers once you have them; they change the CAC targets in §5 directly.

---

## 1. Buyer personas (sketched from product logic, not research)

Three personas cover who actually clicks "buy" at an independent gym. Validate against your 22 gyms within 60 days — see §6.

**Persona A — The Owner-Operator (primary, ~60% of spend)**

- 1 location, 50–250 active members, staff of 2–8.
- Does sales, scheduling, coaching, and bookkeeping personally. No dedicated admin.
- Current tool: spreadsheets, WhatsApp/group texts, paper waivers, or a legacy tool they've outgrown (Mindbody, Glofox, Zen Planner, Vagaro, WellnessLiving, Pike13).
- Trigger to buy: a no-show/overbooking incident, a late-night hour lost to manual scheduling, or a missed payment they had to chase down.
- Buys on: time saved, "runs itself," low setup effort, price.

**Persona B — The Studio Ops Lead (~25% of spend)**

- Multi-instructor boutique studio, manages waitlists, instructor payroll/commission, capacity per class type.
- Not the owner — evaluates and shortlists, owner approves.
- Buys on: instructor scheduling logic, waitlist automation, reporting for the owner.

**Persona C — The Growth-Minded Multi-Location Owner (~15% of spend)**

- 2–5 locations, already software-literate, currently on a legacy platform they're unhappy with (pricing, support, or feature bloat).
- Buys on: migration ease, multi-location reporting, integrations (payments, marketing).
- Longer sales cycle, higher LTV — worth testing but don't over-invest until Persona A is proven.

---

## 2. Positioning per persona

| Persona              | Core message                                               | Proof point to feature                        |
| -------------------- | ---------------------------------------------------------- | --------------------------------------------- |
| Owner-Operator       | "Stop running your gym from a group chat."                 | Time-to-first-booking, price vs. legacy tools |
| Studio Ops Lead      | "Waitlists and instructor schedules that fill themselves." | Waitlist automation, instructor view          |
| Multi-Location Owner | "One dashboard for every location."                        | Migration support, cross-location reporting   |

---

## 3. Channel & budget allocation — $4,500/mo

Two channels, concentrated, not spread thin. $4,500/mo is below the threshold where a third channel (LinkedIn) gets enough volume per audience segment to leave the learning phase — add it in Phase 2 (see §7) once spend doubles.

| Channel                   | Monthly budget | Role                                            |
| ------------------------- | -------------- | ----------------------------------------------- |
| Google Search (non-brand) | $2,300 (51%)   | Capture existing intent — highest-quality leads |
| Meta prospecting (FB/IG)  | $1,400 (31%)   | Build demand among owners not yet searching     |
| Meta retargeting          | $500 (11%)     | Convert site visitors, video viewers            |
| Testing reserve           | $300 (7%)      | New keyword themes / creative rotation          |

---

## 4. Google Search targeting

**Keyword themes (phrase + exact match only — broad match burns budget at this spend level):**

- Category: "gym management software," "class booking software," "gym scheduling software," "membership management software," "boutique studio software"
- Vertical-specific: "CrossFit gym software," "yoga studio software," "boxing gym management software," "pilates studio software," "martial arts studio software"
- Competitor-displacement: "[Mindbody / Glofox / Zen Planner / Vagaro / WellnessLiving / Pike13] alternative," "[competitor] pricing"
- Pain-point: "reduce gym no-shows," "gym payment processing software," "automate class waitlist"

**Negative keywords (block immediately, category is noisy):** free, jobs, career, salary, personal trainer certification, workout plan, home gym, gym equipment, nutrition, franchise for sale, app for members [without "management"/"software"]

**Landing pages:** one per theme cluster — a competitor-alternative page (comparison table + migration CTA) converts far better than sending all search traffic to the homepage.

**Geo:** start narrow — the states/provinces/countries your 22 gyms are actually in. Expand only after 4–6 weeks of CAC data.

---

## 5. Meta targeting

**Audience 1 — Seed lookalike (highest priority despite "no analysis" of the 22 gyms):**
Upload the 22 gyms' owner/manager contacts as a Custom Audience, build a 1–3% lookalike. You don't need deep segmentation to use this — it's a different lever than persona-building, and 22 is a usable (if small) seed. Widen to 3–5% if 1% underdelivers on frequency.

**Audience 2 — Interest/behavior stack (persona A/B):**

- Interests: CrossFit, yoga studio, Pilates, boxing, martial arts, personal training, small business ownership, gym management
- Behavior: Page admins of Business/Local pages in the Health & Fitness category
- Job title (where available): gym owner, studio owner, fitness director, general manager

**Audience 3 — Retargeting:**

- Website visitors (30/60/90-day windows), video viewers (75%+), engaged Instagram/FB page visitors
- Exclude converted leads

**Placements:** Instagram feed + Stories, Facebook feed. Exclude Audience Network and Messenger placements — low-quality traffic for a considered B2B purchase.

**Creative, one angle per persona** (per §2 positioning): a short owner-testimonial/day-in-the-life video performs best as the top-of-funnel hook; a feature-comparison carousel as the retargeting close.

---

## 6. Validate the personas against your 22 gyms (do this in parallel, not before launch)

Since personas above are inferred, not researched, run a lightweight pass now so week-4 optimization isn't guessing twice:

1. Pull location count, member count (if known internally), and current/previous tool for each of the 22.
2. Tag each against Persona A/B/C.
3. After 4 weeks of ad data, compare which persona's targeting produced the lowest CAC and highest trial→paid conversion — reweight budget toward that persona.

---

## 7. Phase 2 (once monthly spend > ~$8–10k)

- Add LinkedIn Ads (job-title + company-size targeting) for Persona C specifically — LinkedIn's CPCs need higher volume to be efficient, not viable at $4,500/mo.
- Add a competitor-conquesting layer (Google Display + Meta) targeting reviewers/complainers of legacy tools.

---

## 8. Measurement plan

- **Primary conversion:** demo booked or trial started (not "lead form filled" — too loose for this category).
- **Attribution:** GA4 + UTM on every campaign/ad-set; Meta 7-day click / 1-day view; Google last-click.
- **CAC target:** back-calculate from your real ACV once known. As a placeholder at $150/mo avg with a 24-month expected retention (~$3,600 LTV), target CAC ≤ $600–900 to stay at a healthy 4–6x LTV:CAC.
- **Weekly review cadence:** spend, CPL, trial-start rate, trial→paid rate, CAC by channel and by persona tag.
- **Kill criteria:** any ad set with >$400 spend and zero trial starts — pause and reallocate.

---

## 9. Prospect scoring rubric — for outbound/ABM layer (not paid ads spend)

This applies if you're building a target-account list for LinkedIn outbound or ABM-style Meta custom audiences later, not to the $4,500 always-on campaigns above. No actual prospect list was provided, so this is the scoring framework only — apply it once you have a list.

| Signal                                                                                              | Weight     | Source                                      |
| --------------------------------------------------------------------------------------------------- | ---------- | ------------------------------------------- |
| Public member-count/revenue proxy (Google review count, social follower count, class-schedule size) | High       | Google Business, Instagram, Yelp            |
| Current tool (legacy platform = displacement target; spreadsheets/none = green-field)               | High       | Booking page footer, app store, site source |
| Location count                                                                                      | Medium     | Website, Google Maps                        |
| Review rating (4.3+ = healthy, retained membership base)                                            | Medium     | Google/Yelp                                 |
| Recent growth signal (new location announced, hiring posts)                                         | Low-medium | Social/job boards                           |

**Tiering:** Tier A = strong signals across ≥3 rows. Tier B = mixed. Tier C = weak signals. **Tier D (bottom of list) = no public member-count or revenue signal at all** — per your instruction, missing data is scored as a red flag rather than neutral/unknown, and these prospects sort to the bottom of the primary outreach queue.

One flag worth having on record: this rule will systematically deprioritize small, digitally invisible gyms — which in this category are often the _least_ professionalized on ops and therefore the best-fit early customers, they just haven't been indexed anywhere yet. If Tier D turns out to be a large share of the list, worth a small separate low-effort outreach track for it rather than dropping it entirely — your call, flagging it so it's a deliberate choice and not a blind spot.
