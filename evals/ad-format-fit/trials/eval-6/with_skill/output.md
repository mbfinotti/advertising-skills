# Pellonia Home — Pre-Launch Format-Fit Check

Three separate launches bundled under one ad account. Verdicts below, per campaign, then a consolidated blocker list. Platform numbers are an **August 2026 snapshot** — I had no web access this session to reverify them, so every gating number is marked `unverified-current`: confirm each in the actual ads interface before spend commits.

---

## Campaign A — Fully-automated multi-surface shopping ($40/day, 8 products, 6 creatives)

**Verdict: INELIGIBLE as configured.** This is a textbook stacked hard-gate failure, not a single flag:

| Gate | Status | Why |
|---|---|---|
| First-ever campaign on a brand-new account | **Fails** | Automated multi-surface types should never be an account's first campaign — there's no history for the algorithm to inherit. |
| $40/day budget | **Fails** | Sits under the ~$50/day floor for this campaign type. |
| Tracking state | **Fails** | Pixel installed last week, never tested = unverified/likely-zero real conversion signal. Automated bidding fed no signal optimizes on noise, not intent. |
| Catalog/creative depth (8 products / 6 creatives) | **Flag, not a block** | Well under the 30+ product / 15+ creative readiness heuristic — this alone wouldn't kill the launch, but it removes any cushion once the three hard gates above are fixed. |

**Fix:** don't launch the automated type yet. Run a standard, manually-structured Shopping/Search campaign first on this budget. Graduate to the automated multi-surface campaign once: the pixel has fired verified test conversions (browser-side *and* server-side) for at least 1–2 weeks, budget can move above ~$50/day, and the catalog/creative set has grown closer to 30+/15+.

---

## Campaign B — Retail-media display banner, 970×250, "barely spending"

**Verdict: HOLD on raising bids — diagnose first.** "Approved at upload" proves the creative passed policy review. It proves nothing about delivery. A dimension that's technically valid can still be silently excluded from the specific placements it was bought against, and that reads on the dashboard exactly like a bid problem.

**Before touching bids:**
1. Pull the placement-level delivery breakdown (minutes, no spend, already in the report you have).
2. Check whether the 970×250 creative is actually winning impressions across every placement it's eligible for, or whether delivery is near-zero on some/all of them despite "approved" status.
3. Only if impressions exist but volume is genuinely thin is raising bids the right lever. If impressions are near-zero across eligible placements, the fix is re-scoping/re-submitting the creative for the placements actually buying it — a bid increase won't move a creative that isn't being served at all.

Also unconfirmed and worth a quick check: what funnel stage is this buy targeting? Display structurally fits retargeting/cheap awareness, not cold direct conversion — if it's cold-audience display expecting direct response, "barely spending" might be a legitimately small addressable retail-media audience rather than any kind of problem.

---

## Campaign C — LinkedIn lead form, 14 qualifying fields (B2B sister brand)

**Verdict: INELIGIBLE as spec'd (hard gate) + likely structural misfit.**

1. **Hard gate — field count:** LinkedIn lead gen forms cap at **12 fields maximum** (3–4 recommended). 14 fields exceeds the platform ceiling — this form cannot be built as described; the form builder will block it. **[blocker]**
2. **Structural misfit:** "14 qualifying fields" signals this is really a high-value, sales-assisted pipeline job (demo booking, sales-qualification), not volume lead capture. In-platform lead forms are structurally wrong for that job — they remove the landing-page qualification step entirely. Cramming qualification into the form is fighting the format, not using it.

**Fix — pick one, depending on what the sister brand actually wants:**
- If the goal is booking sales meetings/demos: move to a **landing page with an embedded calendar**. A form adds friction to a calendar-booking goal regardless of field count.
- If the goal is genuine top-of-funnel volume (content/webinar registration): cut the form to **3–4 fields** and push the remaining qualification downstream into nurture/BDR follow-up, not onto the ad unit.

**Also unconfirmed, needs answers before this ships:**
- CRM field mapping for whichever fields survive the cut.
- Target audience size clears LinkedIn's 300-member campaign minimum.
- Realistic weekly qualified-lead volume — if it won't clear roughly 10-50 events/week, don't expect full automated lead-gen optimization to behave well out of the gate.

---

## Consolidated launch-blocker list (zero blockers = launch threshold — currently at 3)

| # | Blocker | Fix |
|---|---|---|
| 1 | **[blocker]** Pixel never tested (Campaign A) | Fire and confirm test conversions, browser-side and server-side, before any spend optimizes on it. |
| 2 | **[blocker]** Automated shopping campaign as first-ever launch, sub-$50/day, on unverified tracking (Campaign A) | Launch standard Shopping/Search first; hold the automated type until the three gates above clear. |
| 3 | **[blocker]** LinkedIn lead form has 14 fields vs. a 12-field platform maximum (Campaign C) | Cut fields (ideally to 3–4) or replace the form with a landing page + calendar, per the goal above. |

Campaign B isn't a launch-blocker (it's already live) — but treat the requested bid increase as blocked pending the placement-delivery check.

---

## Post-launch watch list

1. **Campaign A**, once fixed and live: watch the platform's own "asset strength" / diagnostics reading. With only 8 products / 6 creatives, a weak reading is an input problem the automated campaign type cannot optimize its way out of — don't respond to it with a bid change.
2. **Campaign B**: check for placement-breakdown divergence — spend concentrating almost entirely on one cheap surface is the documented pattern behind this exact "approved but barely spending" symptom.
3. **Campaign C**: once live, watch frequency against the ~2.0–5.0 band typical for small B2B account-based audiences. A narrow qualifying form plus a small target list can starve for volume fast — if qualified-lead volume never clears the range above, treat it as a manual-review regime, not an optimization problem.

Confirmation order for all three: start with the free placement/format breakdown on existing reporting (cheapest, use it first on Campaign B since it's live now); escalate to an isolated ad set only if a signal stays ambiguous after that.

---

## Dated-numbers appendix (all August 2026 snapshot, `unverified-current`)

| Number | Used for | Confirm before |
|---|---|---|
| Automated multi-surface shopping: poor fit <$50/day, new account, or weak tracking | Campaign A blocker | Any spend increase on Campaign A |
| Automated shopping readiness heuristic: 30+ products / 15+ creatives (soft, flag-only) | Campaign A flag | Graduating to the automated type |
| LinkedIn lead form fields: 3–4 recommended, **12 maximum** | Campaign C blocker | Building the form — this is the one load-bearing number here, verify it directly in LinkedIn Campaign Manager first |
| LinkedIn campaign audience minimum: 300 members | Campaign C open question | Campaign C launch |
| Optimized-delivery conversion-volume floor: ~50 events/ad set/7 days (≈10/week for purchase-type events) | Campaign A & C expectations | Turning on full automated optimization for either |

Keep this report as the canonical pre-launch record — no persistent memory store available in this session to hold it for you.