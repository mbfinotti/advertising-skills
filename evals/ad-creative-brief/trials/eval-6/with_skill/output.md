## Art Direction (Section 6) Review — Pattern & Pine Meta Brief

Checked against the failure-modes table and Art Direction Rules in `ad-creative-brief`. Four issues, in fix-first order (each costs the same few minutes before this goes to the designer, so ranked by what's actually broken, not by severity theater):

---

### 1. Style descriptors have no reference ads — this is the #1 documented failure mode

> "Premium, aspirational, authentic" decodes differently per reader. That's not a stylistic nitpick — it's the specific trap named in the skill's failure table: *"Vague adjectives instead of reference ads → Premium and authentic decode differently per reader → Fix: 2-3 in-category references, one note each."*

**Change required:** Pull 2-3 in-category reference ads (Meta Ad Library, filtered by longevity — an ad still running after months, not one that's merely recent) and attach one line each on what to take: *"take the natural light," "take the lived-in staging, not showroom," "take the caption tone."* Without this, the freelancer fills "premium/authentic" with their own defaults, and you'll spend the revision cap correcting taste, not direction.

**Action needed from you:** send 2-3 links.

---

### 2. Hardcoded safe-zone pixels — delete the numbers, keep the discipline

> 250px top / 310px bottom for 9:16 is a specific, confident-looking rule built on a number that will be wrong. Meta's published safe-zone guidance has changed and disagreed with itself by tens of pixels across placements and over time — a hardcoded figure is a defect whether or not it happens to match today's spec.

**Corrected line:**
> *Safe zone: text and logo clear of the top and bottom UI overlay zones on 9:16 (Stories/Reels). Preview every export in-placement (Meta's placement preview tool) before it ships — do not trust a fixed pixel number.*

This is a stronger instruction to the designer than a pixel count, not a weaker one: it survives the next time Meta moves the overlay.

---

### 3. The 20% text rule — this is dead, and stating it as live creates a false constraint

> Meta retired the 20% text rule in **2020**. There is no hard limit and no auction/delivery penalty tied to text coverage today. The claim that Meta "throttles delivery" over text density is exactly the kind of vendor-post folklore the skill flags explicitly: *"Claims of a persistent hidden delivery penalty circulate in vendor posts and are unverified — say so rather than encoding folklore as a rule."*

**Corrected line:**
> *Text density: no hard limit, no delivery penalty (the 20% rule was retired in 2020). Treat as a performance preference, not a constraint — heavy text still reads as low-effort/spammy to users and can hurt CTR and engagement on its own merits. Keep primary claims legible as on-screen text regardless (captions are non-optional for sound-off viewing).*

Don't hand the designer a fake technical ceiling — hand them the real reason to keep text light (user perception, not an algorithm penalty).

---

### 4. Do's/don'ts: 9 + 7 = 16 items nobody reads

> The brief template caps this at **max 2 each**. A 16-item list at handoff doesn't get read — it gets skimmed once and ignored by round two, and the freelancer defaults back to their own judgment anyway, which defeats the point of having brand rules at all.

**Action needed from you:** pick the 2 do's and 2 don'ts that would actually sink the ad if violated (e.g., a specific prop/material ban, a specific staging or model-diversity requirement) — not the ones that are merely nice-to-have. Send those 4 and I'll fold them in. The rest belongs in a separate brand-book link the designer can consult, not in the brief body.

---

### 5. The Midjourney plates are not "nobody's business" — this is a required brief field, not a footnote

> This is the one item I'd stop and flag hardest. The brief template has a dedicated **AI-disclosure** field for exactly this case: *"content generated outside the platform's own tools generally must be declared in the ads manager… undisclosed AI content is a commonly reported rejection reason."* Meta's own ad policies require disclosure of AI-generated/altered content in certain cases (and increasingly default to auto-detecting it) — this isn't a matter of preference, and getting it wrong risks the ad being rejected or a page-level policy strike, not just an awkward compliance conversation.

Separately: the freelance designer needs to know the backgrounds are AI-generated plates, not licensed photography or in-house shoots — that changes what they're legally cleared to composite, resize, and reuse, and whether *their* output inherits a disclosure obligation.

**Added field (was missing, not just wrong):**
> *AI disclosure: 2 background plates generated via Midjourney, used as [composite background / base layer — confirm which]. Will be declared under Meta's AI-content disclosure in Ads Manager. Designer note: treat as AI-originated assets for compositing purposes; do not represent as photography in any claim or caption.*

**Action needed from you:** confirm exactly how the plates are used (full background vs. element within a composited photo) — that determines whether disclosure is required under Meta's current policy or just good practice, and I don't want to guess on a compliance-adjacent claim.

---

### What else is missing from the specs section entirely (not just wrong — absent)

The template requires these fields alongside style/safe-zone/do's-don'ts, and none were in the draft:

- **Sound-off + accessibility**: captions non-optional, 4.5:1 contrast minimum, alt text, ≤3 flashes/sec.
- **Enhancements on/off**: Meta's auto-enhancements (brightness/crop/music auto-add) are default-on per placement — an unset toggle is an uncontrolled variable if you're running this as a test.
- **Compliance mandatories**: any substantiation-required claims or forbidden phrasings (DTC furniture is low-regulation, but if there's a "handmade," "sustainable," or "lifetime warranty" claim anywhere in the creative, it needs a substantiation note here).

---

### Bottom line before this ships to the freelancer

Send: (1) 2-3 reference ad links, (2) the 4 highest-stakes do's/don'ts, (3) confirmation on how the Midjourney plates are composited. I'll drop in the corrected safe-zone/text-density language and the AI-disclosure field as written above — those don't need more input from you, they're just fixes.