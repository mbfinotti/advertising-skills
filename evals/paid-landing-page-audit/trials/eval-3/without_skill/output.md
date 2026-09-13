# Ferrovine demo-request form audit — recommendation

## Verdict

Don't cut to 3 fields. The Baymard stat your CMO is citing measures the wrong thing for your problem, and applying it here will make the SDR complaint worse, not better. The actual leak isn't field count — it's that your LinkedIn campaign is pulling in traffic (students, consultants) that was never going to buy an $80k governance platform, and the form is the only thing currently filtering any of it out.

## Why the Baymard number doesn't transfer

Baymard's 11.3-field figure is checkout research: someone who already decided to buy is being asked for shipping/billing data with zero informational value to you as the seller. Every field there is pure friction — cutting it is free conversion.

Your form is doing a different job. It's the only qualification signal you get _before_ an SDR spends 20 minutes on a call. Job title, company size, and use-case fields aren't friction in this context — they're the mechanism that currently keeps at least _some_ students and consultants out. The "-11% per field" rule is real, but it's a rule about _fills_, not about _qualified pipeline_. Those are not the same curve, and for a $80k ACV enterprise deal, pipeline is the only number that matters.

## The math nobody's modeling

Current state: 2,400 sessions → 85 fills = **3.5% CVR**. SDR says >50% are unqualified, so call it ~40 qualified MQLs/month, ~45 junk.

If you cut to 3 fields (name, email, company):

- Fills likely rise — plausibly 40-70%+, in line with field-reduction benchmarks. Say fills go to ~130-140.
- But you just removed the two fields (title, company size — assuming they're in your current 8) that do the qualifying. Junk rate on LinkedIn traffic doesn't go down because the form got shorter; it goes down because of _targeting_, not form length. If anything, a frictionless 3-field form makes it easier for curious non-buyers to fill it out too.
- Net result: more fills, same or _worse_ qualified-lead count, SDRs now triage more noise for the same yield. You'll hit a "fills" number the CMO can show in a slide, and pipeline stays flat or drops because SDR time (a fixed resource) gets diluted across more junk.

That's the trap: fills is a vanity metric here. The KPI that should be driving this decision is **qualified pipeline $ per session**, not form-fill rate.

## What's actually driving the >50% junk rate

Before touching the form, this needs to be checked (I don't have access to your LinkedIn campaign manager, so confirm these):

- **Audience targeting**: are you excluding "Student," "Education," job seekers, and non-decision-maker seniority levels in LinkedIn Campaign Manager? Enterprise data-governance buyers are Director+ in IT/Security/Compliance/Data at companies with real data estates — if seniority/function/company-size filters aren't tight, this is your #1 leak, not the form.
- **Creative/offer mismatch**: if the ad copy or lead-magnet framing reads as generic/educational ("data governance 101") rather than buyer-specific, it self-selects for learners over buyers.
- **LinkedIn Lead Gen Forms vs. landing page**: if any spend is running native LinkedIn Lead Gen Forms (autofilled from profile, one click, no real intent), that's a known junk-lead source — autofill makes it trivially easy for anyone to convert regardless of buying intent.

## Recommended form (not 3, not 8 — targeted 5)

Keep it short, but keep the two fields that do qualification work:

1. Name
2. Work email — **validate against a free/personal-email blocklist** (gmail/yahoo/outlook.com/student .edu domains) at the field level. This alone kills a meaningful share of students/consultants before they ever hit an SDR queue, and it's a validation rule, not an extra field.
3. Company (auto-enrich company size/industry via Clearbit/ZoomInfo/similar on email domain instead of asking — this gets you the CMO's "fewer visible fields" win _and_ keeps the qualification data)
4. Job title — free text or seniority dropdown; single biggest SDR-triage signal for a $80k enterprise sale
5. Company size — dropdown, single click, not typed

This gets you visually and functionally close to a short form (5 fields, one of which is a one-click dropdown) while preserving the two signals your SDR team is currently relying on, plus adds an automatic filter (email domain) that today's 8-field form apparently isn't even doing.

## What I need from you to actually size "hit our pipeline number"

You said "hit our pipeline number" but didn't give me the target — I can't model whether any of this closes the gap without:

- Target pipeline $ (or # of qualified opps) for the period
- Current MQL → SQL and SQL → Opp conversion rates
- Average deal size and sales cycle length (you gave ACV ~$80k — confirm that's the number to use)

With those, the model is: `Pipeline $ = Sessions × Qualified-Fill Rate × MQL→SQL × SQL→Opp × ACV`. Field count only touches the second term, and cutting fields blindly can shrink it while growing the fill-rate term — that's exactly the failure mode described above. Send me those four numbers and I'll build the actual scenario comparison (current form vs. CMO's 3-field cut vs. the 5-field/domain-validation version) in $.

## Test plan before committing either direction

Don't ship the 3-field version fleet-wide. A/B test it against the 5-field version above for 2-3 weeks, but score both on **SQL rate and pipeline $ per session**, not fill rate — otherwise you'll declare victory on a metric that doesn't pay rent. In parallel, fix LinkedIn audience targeting immediately (no A/B needed, it's clearly leaking) — that's the higher-leverage, zero-tradeoff move and should happen this week regardless of what the form test shows.
