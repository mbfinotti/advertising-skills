# Landing Page Audit — Kelpwise Compliance Demo Page

Before the report: two things you asked for directly, answered first.

## 1. "Clearly mobile is the problem, right?"

**No — refuse this call.** Both of this skill's volume floors are breached at once:

- **Session floor**: 640 sessions is below the ~1,000-session floor.
- **Conversion floor**: 9 conversions is below the ~30-conversion floor.

Below either floor, a conversion-rate comparison can't separate a real effect from noise — and you're below _both_. Splitting an already-thin 9 conversions by device makes it thinner still. Back-solving your own numbers shows why: if mobile converts at 1.1% and desktop at 1.9%, and together they sum to 9 conversions across 640 sessions, mobile share works out to ~62% of sessions (~395 mobile, ~245 desktop) — which lands at **roughly 4 mobile conversions vs. 5 desktop conversions**. Your "clear" device gap is one converted lead. Move a single lead from desktop to mobile and the ranking flips.

Don't reallocate spend or effort by device from this data. If device prioritization matters operationally, the right question per this skill isn't "which converts higher" on 9 conversions — it's **which device carries the spend** (mobile is weighted by where the money is, not just where the sessions are). You haven't told me the spend split; get that instead of trusting these rates.

## 2. "Set up an A/B test on the headline."

**No — also refuse this, on a separate floor.** Below ~100 conversions/month, this skill does not recommend A/B testing as a validation path at all — you're at 9/month, an order of magnitude short. A headline test at this volume would run for months to reach significance, and any "win" that emerged early would very likely be a Type S/M error (wrong sign or wildly overstated magnitude per Gelman & Carlin) — Kohavi's and Optimizely's data already say only ~10–33% of tests win _at proper power_; underpowered ones are worse than a coin flip at telling you anything true.

What to do instead: ship the well-evidenced friction removals below and monitor CPA/CVR trend for a full cycle. You will not get statistical proof this way — say that plainly to whoever needs to sign off — but it's the honest path at this volume. Revisit A/B testing once you're clearing ~100 conversions/month, with a sample-size calculation run first.

---

## Full Audit

```
LANDING PAGE AUDIT - Kelpwise demo page, 2026-09-12
traffic        : Google Ads (search, presumed) | model: B2B
goal           : demo request | downstream truth: pipeline (SQL/MQL) - not measured here, only form-fills
window         : last 30 days | volume: 640 sessions, 9 conversions | volume floor: NOT cleared (both session and conversion floors)
economics      : CPA $210 vs target $120 - gap: 1.75x (75% over target)
inputs         : ad creative: NO | analytics: aggregate CVR/CPA + device split only, no funnel breakdown | recordings: no | page: pasted copy only, not fetched
```

### VERDICT

Can't fully confirm the page is the problem — CTR/frequency trend, conversion-tracking validity, and whether targeting or offer changed alongside the CPA rise are all unprovided, so an ad-account root cause isn't ruled out. That said, the page copy shows several real opinion-class issues independent of the device question: a generic, audience-less headline, unattributed testimonials, no visible trust cues from a company selling _compliance_, no risk reversal. These are worth fixing regardless of what's happening upstream. Proceeding as a page audit, with the upstream gap flagged below rather than hidden.

Note: a normal run of this skill interviews before opening anything (ad copy, funnel breakdown, prior tests, deadline, effort ceiling, spend-by-device). None of that was available here, so it's logged under "Could not check" instead, and the fix ranking below uses default ordering, unadjusted for any of those answers.

### FIX NOW (ranked by efficiency, not severity)

**1. Headline/subhead — no audience or pain named**
"Compliance, simplified" is feature-speak: run it through the "Now you can…" test and it turns vague rather than compelling. It also doesn't name the audience (mid-market fintech) or a specific compliance pain (SOC 2, AML, audit prep), so it can't yet be confirmed to match a specific ad promise.
→ Rewrite to name the audience and the specific outcome, e.g. leading with fintech-specific language once the real ad wording is known.
funnel step: land → engage | evidence: opinion | source: consensus | severity: major | effort: hours

**2. Testimonials unattributed**
Two quotes reading "Great product!" — Customer have no name, role, company, or specific result. Per Baymard/NN/g consensus, anonymous filler reads as fake and costs more than it earns — and if these aren't real attributed customers, publishing them as testimonials carries FTC fake-review-rule exposure, not just a CRO cost.
→ Replace with named, attributable proof (name, role, company, specific result), or remove.
funnel step: engage → form start | evidence: opinion | source: consensus (established: FTC disclosure rules) | severity: major | effort: hours (if real attributable quotes exist)

**3. No trust/security cues from a compliance vendor**
A compliance product asking a fintech to trust it with their audit process, with no certifications, client logos, or concrete numbers visible, leaves the "who are you, can I trust you with this?" objection uncountered at the exact point it would arise.
→ Add compliance-relevant proof (SOC 2/ISO badges, named client logos, a concrete metric) near the CTA/form.
funnel step: engage → form start | evidence: opinion | source: consensus | severity: major | effort: hours–days depending on asset availability

**4. No risk reversal or post-CTA expectation-setting**
Nothing on the page tells a visitor what happens after "Get a demo" — no guarantee, no "here's what the call covers," no timeframe.
→ Add a short risk-reversal or expectation line near the CTA.
funnel step: form start → completion | evidence: opinion | source: consensus | severity: minor | effort: hours

**5. 7-field form — untested whether it's buying quality or just losing volume**
Name, work email, phone, company, role, company size, current tooling is a long form. The B2B exception applies: if lead quality is the actual bottleneck, some of these fields (company size, current tooling) are legitimate qualifiers, not waste — but that hasn't been established here.
→ Trim to what's needed to book the demo (name, work email, company, role); move company size and current tooling to the call itself, unless lead quality is confirmed as the bottleneck.
funnel step: form start → completion | evidence: opinion | source: consensus | severity: minor–major | effort: hours (form config)

### RULED OUT

None. Effort ceiling, dev access, page ownership, deadline, and mandate (fast win vs. compounding asset) were never established — so nothing was deleted by constraint. If any of those answers would remove an item above, say so and it'll be moved to this section.

### TEST, DON'T GUESS

- **Headline rewrite**, once real ad copy is available _and_ volume clears the floor — judged on land→engage and form-start rate, ideally with an SQL-quality read given the pipeline lag. Not to be run at the current 9 conversions/month.
- **Form-field trim (item 5)** — judged on form completion rate _and_ downstream lead quality (SQL rate), because a shorter form can lift fills while lowering pipeline value — the B2B trap this skill flags explicitly.

### NOT A PROBLEM

- CTA copy: "Get a demo" is a single, clear, standard B2B verb — no competing CTAs appear in the copy supplied.
- Subhead: "Audit-ready in weeks, not months" is a concrete, outcome-stated claim, not feature-speak — keep it.
- No-pricing-shown is defensible on its own: a demo-gated, call-booked B2B offer doesn't need price on the landing page (though it should still say what determines it — folded into item 4 above).

### COULD NOT CHECK

- **The ad itself** — copy, creative, and keyword weren't supplied, so the single highest-leverage check in this skill (verbal/visual/offer/geo message match) could not run at all. Everything above about the headline is a standalone value-prop opinion, not a message-match verdict.
- **Rendered page** — no live URL or screenshots, so above-the-fold layout, CTA visibility on a phone viewport, Core Web Vitals (LCP/INP/CLS), layout shift, and accessibility contrast/keyboard-focus are all unverified.
- **Funnel breakdown** — land → engage → form start → completion wasn't provided, only the endpoints (sessions, conversions), so where the 640→9 drop actually happens is unknown.
- **Conversion-tracking validity** — no confirmation the conversion event fires once, on true completion, deduplicated. Treat every rate in this audit as provisional per the skill's measurement-sanity caveat.
- **Device spend/session split** — needed to weight device priority by money, not conversion rate; not provided.
- **Geo/language/currency**, prior tests on this page, deadline, mandate, effort ceiling/who implements, and whether lead quality or lead volume is the actual sales bottleneck — none supplied; the ranking above used defaults only.
- **CTR/frequency trend and whether targeting/offer changed with the CPA rise** — upstream (ad-account) causes couldn't be ruled out for that reason; if CTR is declining or frequency is climbing, this may partly or fully be a creative-fatigue problem rather than a page problem.

### RE-CHECK

- Fixes 1–5: expect engage→form-start and form-start→completion to move up, checked one full business cycle out (**2026-10-12**) — but at ~9 conversions/month, read this directionally only, not as a statistically resolved result. Given the B2B pipeline lag, also check SQL rate at 30–60 days out to confirm the shorter form (fix 5) didn't trade volume for quality.

```

```
