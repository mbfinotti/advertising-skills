# Kelpwise landing page audit — CPA $210 vs $120 target

## 1. First: "mobile is the problem" doesn't hold up statistically

You have **9 total conversions** for the period. That's the number that matters more than the two percentages.

Back-solving the device split consistent with your numbers (1.1% mobile / 1.9% desktop, 640 sessions, 9 conversions total) gives roughly:

| Device  | Sessions | Conversions | CVR  |
| ------- | -------- | ----------- | ---- |
| Mobile  | ~395     | 4           | 1.1% |
| Desktop | ~245     | 5           | 1.9% |

Running a two-proportion z-test on 4/395 vs 5/245: **z ≈ 1.07, p ≈ 0.28**. Nowhere near significant (need p < 0.05). The 95% confidence intervals are roughly [0.0%–2.0%] for mobile and [0.3%–3.8%] for desktop — they overlap almost entirely. One extra conversion on either side flips which "wins."

**With 9 conversions total, you don't have enough data to declare a device winner.** That's not a nitpick — acting on it (e.g. dropping mobile bids) risks cutting a channel that's statistically indistinguishable from desktop, based on noise. ⚠️

Get real numbers from GA4 (exact sessions/conversions per device, not rounded rates) before making any device-allocation call, and don't revisit this until you have at least ~25-30 conversions per device.

## 2. What's actually plausible: the form, not the device

One structural factor that _does_ correlate with device and doesn't need a significance test: a 7-field form is disproportionately painful on mobile (small inputs, autofill friction, thumb typing "current tooling" as a free-text field). If mobile really is underperforming, form friction is a far more credible mechanism than "the headline doesn't land on phones." Worth instrumenting form-abandonment by device before assuming headline is the mobile lever.

## 3. Copy audit

**Headline — "Compliance, simplified"**
Generic, could be any compliance vendor's tagline (Vanta, Drata, Secureframe all run near-identical lines). No ICP signal, no proof, no urgency. For cold Google Ads traffic landing here for the first time, this doesn't answer "why should a mid-market fintech click 'get a demo' right now."

**Subhead — "Audit-ready in weeks, not months"**
The strongest line on the page — specific, time-bound, implies a real pain point (slow audit prep). Underused: it's doing headline-level work while sitting in the subhead slot. Missing: _which_ audit (SOC 2? ISO 27001? PCI?). Fintech buyers self-select hard on this.

**CTA — "Get a demo"**
High-commitment ask for someone who just arrived from a paid search ad and hasn't seen pricing or proof yet. This is a classic mismatch between traffic temperature and CTA weight — likely contributing more to the 1.4% overall CVR than any device split.

**Form — 7 fields (name, work email, phone, company, role, company size, current tooling)**
This is the highest-confidence lever on the page. Field-count-to-conversion is one of the best-evidenced relationships in landing page CRO — each additional field past 3-4 measurably drops completion, and "phone" + "current tooling" in particular are asks people resist before they trust you. Cut to name, work email, company — collect the rest during the demo call, not before it.

**Social proof — two anonymous quotes ("Great product!" — Customer)**
Actively counterproductive for a compliance product. Compliance buyers are trust-driven; an unattributed quote with zero specificity reads as fabricated and can suppress conversion versus no testimonial at all. Fix with named logo + role + company, or drop it in favor of your own compliance credentials (SOC 2 badge, ISO cert, customer logos) — notable that a compliance vendor isn't showing its own trust signals.

**No pricing**
Not automatically wrong for enterprise/mid-market B2B, but combined with "Get a demo" as the only CTA, it stacks friction: high-commitment ask, no proof, no price anchor. If pricing truly can't be shown, add a lower-commitment secondary CTA ("See pricing guide" / "Calculator") to capture visitors not ready for a call.

## 4. Priority order

1. **Form fields** (structural, high-confidence, cheap to ship)
2. **Headline specificity** (your test target — see below)
3. **Named social proof / trust badges**
4. Device allocation — **revisit after you have statistically meaningful per-device data**, not before

## 5. Headline A/B test

**Hypothesis:** A headline naming the specific outcome/proof point (audit type, speed, or fintech-specific framing) outperforms the generic "Compliance, simplified."

**Variant B candidates** (pick one — test one variable at a time):

- "SOC 2 Compliance for Fintechs, Audit-Ready in Weeks"
- "Stop Scrambling Before Every Audit"
- "Compliance That Doesn't Slow Down Fintech Growth"

**Setup**

- 50/50 randomized split, concurrent (not sequential — avoids seasonality/day-of-week confounds)
- Primary metric: form submission
- Leading indicator: CTA click-through (higher baseline rate, reaches a read faster — use it to spot a strong loser early, but don't call the test on it alone)
- Guardrail: bounce rate, time-on-page (catch a headline that "converts" by only appealing to a narrower, lower-quality segment)

**Honest sample-size math** — this is the part worth seeing before you commit to a timeline:

| Target lift (form-submit CVR)          | Sessions needed (both arms, 95%/80% power) | Time at current 640/mo |
| -------------------------------------- | ------------------------------------------ | ---------------------- |
| 1.4% → 2.46% (closes the full CPA gap) | ~5,350                                     | ~8 months              |
| 1.4% → 2.1% (50% relative lift)        | ~11,000                                    | ~17 months             |
| 1.4% → 1.8% (30% relative lift)        | ~28,000                                    | ~43 months             |

At 640 sessions/month, a rigorously powered test on the _form-submit_ metric alone will not conclude quickly — the baseline rate is just too low relative to your traffic. Don't schedule a "read the result in 2 weeks" checkpoint; it won't be reliable.

**What to actually do about it:**

- Use CTA-click as the interim decision metric (likely 10-20%+ baseline, needs far fewer sessions to reach significance) to kill a clear loser fast, then let the winner keep running to confirm on form submits.
- If you need the full-conversion answer faster, the lever is traffic/budget, not test design — doubling spend halves the wait.
- Given low absolute risk (a headline swap costs nothing to ship), it's reasonable to run this directionally: commit to a minimum 6-8 week window to smooth weekly seasonality, watch the CTA-click read early, and accept a wider confidence interval on the form-submit number rather than waiting 8+ months for textbook significance.

**Bottom line:** don't reallocate budget away from mobile — the data doesn't support that decision yet. Ship the form-field cut immediately (it doesn't need an A/B test to justify), and run the headline test with CTA-click as your fast read, form-submit as your slow confirmation, and a realistic multi-month timeline rather than a two-week one.
