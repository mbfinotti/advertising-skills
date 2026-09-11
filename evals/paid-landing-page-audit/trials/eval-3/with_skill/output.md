This came in as a request for the finished deliverable in one shot, so I'm skipping the normal one-question-at-a-time interview this skill runs by default — but that means most of the interview questions (ad creative, page URL/screenshots, funnel-by-device, field-level abandonment, target CPA/pipeline number, the current 8 fields' identities, deadline, who implements) went unanswered. I've pushed every one of those into "Could not check" below rather than guessing, and ranked what's left on first principles. Re-run this with those inputs for a fuller pass.

```
LANDING PAGE AUDIT — Ferrovine demo-request page, 2026-09-12
traffic        : LinkedIn paid, B2B enterprise (~$80k ACV) | model: B2B
goal           : demo request (gated form) | downstream truth: pipeline (MQL→SQL→closed-won), NOT form fills
window         : last month | volume: 2,400 sessions, 85 form fills | volume floor: cleared for directional reads,
                 but 85 conversions/month sits below the ~100/month floor for A/B-test validation
economics      : current CPA/ROAS vs target: not provided | pipeline/revenue target: not provided | fill rate: 3.5%
inputs         : ad creative: no | funnel by step/device: no | field-level form data: no | recordings/heatmaps: no
                 | page: not fetched (no URL, HTML, or screenshots supplied) | qualitative evidence: yes — SDR verbatim

VERDICT
Most of the standard page checks (message match, above-the-fold, trust, speed, accessibility, policy, post-click
path) cannot be run — no ad creative, no page content, and no funnel data were supplied. On what's actually
in hand, nothing suggests a raw-conversion emergency: both volume floors this skill uses are cleared, and a 3.5%
fill rate on a gated $80k-ACV demo form isn't on its face evidence of page friction. The one concrete decision on
the table — cut 8 fields to 3 — is a page-level change, so it is in scope, and the evidence behind it doesn't hold:
Baymard's 11.3-field average / ~8-achievable figure is B2C ecommerce checkout data, and this skill's own reference
material is explicit that it must never be used as a B2B lead-form benchmark. The "~11% per field" figure is
contested — published sources disagree on both size and shape — so it licenses only a direction (more fields cost
some conversion, non-linearly), never a number, and never a target field count. Meanwhile you already have an
observation, not an opinion, that the current funnel over-produces unqualified leads (SDR-reported: over half of
MQLs are students/consultants with no budget). Cutting to 3 fields removes filtering friction with no offsetting
quality gain, and would plausibly make that specific, already-reported problem worse. Recommendation: do not ship
the 3-field plan as specified. Separately, a chronic >50%-unqualified-MQL rate is also consistent with an upstream
LinkedIn audience-targeting problem (wrong job titles/seniority/company size in the audience) that no page-side
form change can fully fix on its own — flagging that as a parallel candidate for
`mbfinotti/advertising-skills@ad-audience-targeting`, not a substitute for the fixes below.

FIX NOW (max 7, ranked by efficiency — best step-unblocked-per-effort first)

1. Form field-count plan — the 3-field target is derived from a B2C checkout benchmark this skill's own
   sources say never to use for B2B lead forms, plus a contested per-field percentage → halt the 3-field cut;
   re-derive any field-count change from this page's own field-level and MQL-quality data (see #3), not from
   Baymard or the 11% figure.
   funnel step: form completion, and the metric that actually matters: MQL → SQL | evidence: opinion (citation-
   applicability judgment) | source: established research (correctly scoping figures the CMO's plan misapplied)
   severity: critical | effort: hours

2. Email field — nothing currently appears to stop a personal/free email (gmail, yahoo, outlook, hotmail) or a
   student-style address from completing the form, which is a plausible mechanical explanation for students and
   no-budget consultants reaching MQL → add server-side business-email-domain validation on the existing email
   field, rejecting common free/personal domains. Adds a qualification signal without adding a field or visible
   friction — compatible with the CMO's "fewer fields" goal and the SDRs' quality complaint at the same time.
   funnel step: form completion → MQL quality | evidence: opinion (mechanism plausible, not yet checked against
   this page's own lead data) | source: practitioner consensus
   severity: major | effort: hours to days (depends on the form/CRM stack — see Could Not Check)

3. Field-level instrumentation — there is no field-level start/abandon data, so any field-count decision (cut,
   keep, or add) is currently a guess in both directions → instrument per-field interaction/abandon tracking on
   the existing 8-field form before changing its length.
   funnel step: form start → completion | evidence: opinion | source: practitioner consensus
   severity: major | effort: hours (most form tools expose this natively or via tag manager)

4. Company field — a free-text field with no validation can't distinguish a real employer from "N/A" or
   "self-employed," and yields no firmographic signal for scoring → require the field (already likely required)
   and treat it as a qualification pair with the email-domain check in #2, rather than adding a separate field.
   funnel step: MQL quality | evidence: opinion | source: practitioner consensus
   severity: minor | effort: hours

RULED OUT
None. No effort ceiling or page-ownership constraint was supplied, so nothing was deleted from the list above —
this is the full set the available evidence supports.

TEST, DON'T GUESS
- A further qualifying field (e.g. a required "company size" dropdown) beyond the email-domain check — plausible
  for filtering the remaining junk further, but not evidenced against this page's own data yet. At 85 conversions/
  month you're under this skill's ~100/month floor for treating an A/B test as a validation path, so don't test it
  head-to-head — ship #2 first, then watch MQL qualification rate on a before/after basis rather than a split test.
  (Framing: a monitored bet, not a proven win — most such changes don't move the number they're aimed at.)

NOT A PROBLEM
- Sample size: 2,400 sessions and 85 fills clears both of this skill's volume floors (~1,000 sessions, ~30
  conversions), so the directional reads above aren't statistics theater, even though most page-level checks
  were blocked by missing inputs.
- Raw fill rate (3.5%) is not, by itself, evidence of a page-friction emergency — the problem you described is
  lead quality, not lead scarcity, so nothing here indicates an urgent fill-rate fix is needed.

COULD NOT CHECK
- Ad creative, copy, and the targeted audience/keyword — blocks message match (A), this skill's single
  highest-leverage check for paid traffic, entirely.
- Live URL, HTML, or screenshots of the page — blocks above-the-fold clarity (B), offer clarity (C), trust
  placement (E), speed (F), accessibility (G), policy risk (H), and the post-click path (I) in full.
- Funnel by step and device, and field-level form abandonment — blocks any segment read and any evidence-backed
  answer to "which of the 8 fields, specifically."
- Session recordings or heatmaps — no behavioral read on where in the form people hesitate or bail.
- Target CPA/ROAS or a pipeline/revenue number — blocks sizing the actual gap and fully weighting the fix list
  against it (the report above is ranked on funnel-step leverage, not on dollars, as a result).
- The current 8 fields' identities and order — without this, no specific field can be named as removable; the
  fixes above deliberately change how the existing fields qualify rather than naming which one to cut.
- Whether this page or form has been changed/tested before, device/geo split, who implements fixes, effort
  ceiling, and any hard deadline — all missing, so re-ranking against those factors (see SKILL.md) wasn't possible.

RE-CHECK
- Fix 1 (halt the 3-field plan) and Fix 2+4 (email-domain and company-field qualification): MQL qualification
  rate (share of MQLs that are budget-holding, non-student/consultant), expected up vs. today's SDR-reported
  baseline. First read 2026-10-12 (one monthly cycle); full pipeline read no earlier than 2026-12-12 given
  typical 60-180 day cycles on an $80k-ACV enterprise deal — don't judge this on fill count at either date.
- Fix 3 (instrumentation): no funnel movement predicted — it's an enabling metric. Judged by whether field-level
  data exists and is usable by 2026-10-12.
```