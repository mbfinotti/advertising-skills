# Quick answers to your two direct questions

**"Submit" → "Get my box"** — ship it. It's a one-line copy change, on the paid entry path, and it fixes a real, named anti-pattern (page-checks.md, section D: *"the submit button says what happens next, not 'Submit'"*). No reason to test it first or delay it behind anything else here.

But calibrate what it can do: your CPA gap is 2.3x target ($92 vs $40) and your conversion-rate gap is 2.8x target (3.9% vs the 10.9% you've set). A button-copy tweak does not close a multiple-of-target gap — no hour-scale fix does. Ship it this week as a freebie, then move on to the items below that actually sit on the leaking steps.

**The 10.9% speed-sprint-and-target framing** — two separate pushbacks:

1. *On the 10.9% target itself*: Unbounce's own report calls this a vendor, self-selected dataset where "conversion" is defined differently per page type — the source document explicitly frames it as **context, never a target**. Setting a team OKR to a cross-industry median is very likely to under- or over-shoot what this specific page, funnel, and traffic mix can actually do. Keep 10.9% as "there's real headroom," not as the number people are held to.
2. *On the speed sprint*: your own field data says don't book it. Lighthouse 68/100 is a lab score under throttled conditions. Your CrUX field data at p75 — LCP 2.1s, INP 140ms, CLS 0.04 — clears the Core Web Vitals "good" bar on all three metrics with room to spare (thresholds: LCP ≤2.5s, INP ≤200ms, CLS ≤0.1). Per the checklist this audit runs on: *"If the page passes all three, say so in Not a problem and move on — speed work on a passing page steals priority from message and offer work."* Redirect that sprint's capacity to the items below.

Full audit follows.

---

```
LANDING PAGE AUDIT - Quartzelle paid search LP, 2026-09-12
traffic        : paid search | model: B2C (subscription meal kit)
goal           : purchase (first box / subscription start) | downstream truth: revenue
window         : not provided | volume: not provided | volume floor: NOT confirmed
economics      : CPA $92 vs target $40 - gap: 2.3x | CVR 3.9% vs stated target 10.9% - gap: 2.8x
inputs         : ad creative: no | analytics: partial (top-line CPA/CVR + device split only,
                 no segmented funnel) | recordings: no | page: pasted copy only, no live URL/HTML

VERDICT
Nothing supplied points upstream (no CTR/frequency data, no stated targeting or offer change,
no tracking-integrity confirmation) — but none of those were checked either, so upstream
causes aren't ruled out, only unindicated. Proceeding as a page audit, with tracking
integrity flagged under Could Not Check as a caveat on every number above.

On the page itself: three real leaks are visible from copy alone — a generic, unverified-
against-the-ad headline; price deliberately withheld before checkout on a low-consideration
DTC subscription (not the high-ticket/call-booked case where that's defensible); and a
generic "Submit" CTA. None of these, individually or together, plausibly close a 2.3-2.8x
gap - that gap needs message-match confirmation and offer-clarity work, not a speed sprint
and not a button label alone.

Note on the target: 10.9% (Unbounce, paid search median) is a vendor benchmark presented by
its own source as context, not a target. Treat it as "there is headroom," not as the number
this page is held to - a page-specific, funnel-step goal will track progress more honestly.

FIX NOW (ranked by efficiency: funnel step unblocked per unit of effort, not cheapest first)

1. Headline/message match - "Dinner, solved" cannot be confirmed against the actual paid
   search ads and keywords driving spend, because the ad copy wasn't supplied for this
   audit. This is the single highest-leverage check for paid traffic and it currently runs
   blind. → Pull the top 3-5 spend/keyword ad groups, confirm the H1 states the visitor's
   specific promise (offer, diet type, price claim, delivery area - whatever the ad said)
   in the visitor's own words; fix any mismatch found, including any dynamic/UTM-personalised
   variant silently falling back to the generic page.
   funnel step: land → engage | evidence: opinion | source: research (Quality Score /
   message match is a documented ranking + conversion factor)
   severity: critical | effort: hours

2. Offer clarity - price hidden until checkout. Only defensible for high-ticket, call-booked
   offers; a consumer subscription meal kit competing against HelloFresh/Blue Apron/etc. on
   a search click is not that case. → Show starting price (per-meal or per-box) and plan
   options above or alongside the benefit bullets, before the visitor has to start a signup
   flow to find out.
   funnel step: engage → form/checkout start | evidence: opinion | source: practitioner
   consensus (LIFT model - Anxiety); Baymard's late-cost-reveal finding is checkout-stage
   B2C data and directionally supports this but was not measured on this page
   severity: critical | effort: hours-days (pricing display may need product/legal sign-off)

3. CTA copy - "Submit" names no outcome. → Change to "Get my box" (the team's proposal) or
   equivalent outcome-stated copy. Already the correct call; ship as-is.
   funnel step: form start → submit | evidence: opinion | source: practitioner consensus
   severity: minor | effort: hours

4. Trust/objection placement - proof and answers currently sit in an FAQ accordion, away
   from where the price objection actually fires (the CTA/checkout moment). → Move the
   cost/value and cancellation-policy answers out of the FAQ and next to the price and CTA;
   keep the FAQ for lower-frequency questions only.
   funnel step: engage → form start | evidence: opinion | source: practitioner consensus
   (proof at the point of friction)
   severity: major | effort: hours

5. Above-the-fold specificity - "Dinner, solved" fails the "Now you can…" test: "now you can
   have dinner, solved" is vague, not a stated outcome for a stated person. → Rewrite the
   headline to name the specific outcome and audience the ad promised (depends on #1's
   findings).
   funnel step: land → engage | evidence: opinion | source: practitioner consensus
   severity: major | effort: hours

6. Device-revenue mismatch - 78% of sessions are mobile, but 70% of revenue closes on
   desktop; Core Web Vitals field data says mobile loading is fine (see Not a Problem), so
   this gap is downstream of loading - likely the mobile purchase/checkout path itself.
   → Pull a device-segmented funnel (land → engage → form start → purchase) to find which
   step mobile loses that desktop doesn't; this audit can't see it from copy alone.
   funnel step: engage → purchase, mobile specifically | evidence: observation (the split
   itself is given data) | source: n/a (diagnostic step, not a cited claim)
   severity: major | effort: hours to diagnose; days-weeks to fix once the step is known

RULED OUT
- None. The Interview's deadline, effort-ceiling and page-ownership questions weren't
  answered in this pass, so nothing was deleted from the list. Re-run prioritization once
  those are known - they may demote or delete #2 and #6 if there's no route to a dev/design
  queue this cycle.

TEST, DON'T GUESS
- Full price transparency pre-checkout (fix #2) vs. current reveal-at-checkout flow - judged
  on purchase completion rate and revenue per session, not just form starts, in case early
  price exposure changes who starts the flow as well as who finishes it. Plausible per the
  Anxiety/Distraction logic in LIFT, not evidenced on this page's own data.
- Shortened/relocated FAQ (fix #4) - judged on whether above-the-fold real estate given to
  objection-handling trades off against space currently used for other content.

NOT A PROBLEM
- Core Web Vitals, field data, mobile, p75: LCP 2.1s, INP 140ms, CLS 0.04 - all inside
  Google's "good" thresholds (≤2.5s / ≤200ms / ≤0.1) with margin. The Lighthouse 68/100 lab
  score is a diagnostic signal under throttled conditions, not evidence of a live-user leak;
  a dedicated speed sprint isn't supported by this data and would pull effort from the fixes
  above.
- CTA count: one primary CTA described, no competing calls to action in the pasted copy.

COULD NOT CHECK
- Actual ad copy, creative, and keywords - blocks fix #1, the top-ranked check in this
  methodology, until the team runs it.
- Sessions/conversions for this page's window - Volume Floor status is unconfirmed; treat
  the 3.9% and $92 figures, and any future A/B read, with that caveat until session/
  conversion counts are known.
- Conversion event firing once, deduplicated, and reconciled - not confirmed, and every
  number in this report inherits that uncertainty.
- Device-segmented funnel beyond the top-line 78% mobile session / 70% desktop revenue split
  - needed to act on fix #6.
- Session recordings, heatmaps, or support/VoC verbatims - none supplied.
- Whether this page has been changed or tested before, and what happened.
- Deadline, effort ceiling, and who implements (design/dev access) - the Interview questions
  that would re-rank and possibly delete items above weren't answered.
- Rendered page: field counts, labels, tap targets, contrast, keyboard access, checkout flow
  detail, testimonial presence, FAQ content, the three benefit bullets' actual copy - only a
  copy summary was supplied, no live URL/HTML/screenshots.
- Whether the CrUX figures given are page-level or origin-level, and whether they carry
  enough paid-search-specific mobile sample to trust at this page's traffic volume - worth
  confirming before fully retiring the speed question.
- Ad-platform policy exposure (recurring-billing/negative-option disclosure, given price is
  hidden and this is a subscription) - not evidenced as a violation here, but flagged as
  worth a direct check given the combination.

RE-CHECK (dates pending a ship date - shown as +1 full business cycle from ship, matched
attribution-lag maturity)
- Fix 1 (message match): land → engage rate on paid search, mobile + desktop segmented.
- Fix 2 (price shown): engage → form/checkout-start rate.
- Fix 3 (CTA copy): form-start → submit micro-step; not expected to move CPA alone.
- Fix 4 (trust placement): engage → form-start rate.
- Fix 5 (headline): land → engage rate / immediate-exit rate as a five-second-test proxy.
- Fix 6 (mobile funnel diagnosis): mobile-specific engage → purchase rate, once the
  blocking step is identified and fixed.
```