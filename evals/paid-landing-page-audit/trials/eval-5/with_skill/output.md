# Landing Page Audit — Grainhollow paid search LP

```
traffic        : paid search | model: B2C (assumed — a "double your salary" hero claim reads consumer-facing; flag if Grainhollow actually sells to employers)
goal           : signup (14-field form) | downstream truth: enrollment/revenue, not raw fills
window         : not supplied | volume: not supplied | volume floor: NOT cleared
economics      : CPA/ROAS/target not supplied | device: mobile = 74% of spend
inputs         : ad creative: no | analytics: no | recordings: no | page: not fetched — working from your issue list only
```

**Volume floor not cleared.** No sessions/conversions were given, so this ranks by first-principles and established research, not statistics — no A/B-test validation path either at this stage.

## Verdict

Working from the seven issues you already identified, not a fresh render. Nothing here points upstream (no creative-fatigue or tracking signal was given, but I couldn't check for one either — see _Could not check_). Proceeding as a page-side prioritization.

**On "cheapest quick wins first":** the skill this audit follows ranks by _efficiency_ (funnel-step-unblocked per unit of effort), not raw cost — cheapest-first and efficiency-first are different orderings, and it flags that distinction rather than silently substituting one for the other. In your case they land in almost the same order anyway: your constraint (CMS copy/image edits only, no dev, no agency) makes every _eligible_ fix cost roughly the same — an hour or two — so effort stops discriminating between them and the ranking below is driven by leak size, not price. The two exceptions that would jump any ranking regardless (compliance exposure) also happen to be your two cheapest edits, so "cheapest first" and "priority first" agree here almost by coincidence, not by design.

## Fix now (ranked, max 7)

**1. Delete the resetting countdown timer**
Failure: a timer that resets every page load is fabricated urgency — not a design opinion, a documented failure mode (fake-scarcity urgency is treated as a finding _against_ a page, never a fix for it, in every practitioner source this audit trusts). "It's been there a year and converts well" is an anecdote from one person watching one uncontrolled period — not evidence, and irrelevant to the compliance exposure, which accrues daily regardless of conversion rate.
→ Remove it. Don't replace it with another synthetic urgency device.
funnel step: trust at first impression, and standing platform/FTC exposure | evidence: opinion | source: established (FTC fake-scarcity enforcement + ad-platform claims policy)
severity: critical | effort: hours (delete a CMS block)

**2. Rewrite the "guaranteed to double your salary" claim**
Failure: an unqualified outcome guarantee is exactly the claim class ad platforms disapprove destinations for (unrealistic-results promises) and the kind of income claim regulators scrutinize hardest. It's also a "too good to be true" trigger that erodes trust the moment a skeptical clicker reads it.
→ Replace with a claim you can substantiate (a specific, attributable outcome — "graduates who did X" — or drop the guarantee framing entirely).
funnel step: land → engage (credibility), plus standing platform/legal exposure | evidence: opinion | source: established (ad-platform claims policy, FTC substantiation requirements)
severity: critical | effort: hours (copy rewrite)

**3. Fix the headline to name the course the ad promotes**
Failure: this is a verbal message-match break — the single highest-leverage check for paid traffic, and partly enforced by the platforms themselves (Google Quality Score weighs landing-page experience). A clicker who searched or clicked on a specific course lands on a headline that doesn't confirm the promise; information scent resets to zero on the first screen.
→ Pull the exact course name/promise from the ad copy into the H1, ideally in the ad's own words.
funnel step: land → engage (top-of-funnel drop-off) | evidence: opinion | source: consensus + documented platform mechanic (Quality Score)
severity: major | effort: hours (copy edit)

**4. Move testimonials out of the footer to the point of friction**
Failure: proof placed where nobody scrolls to doesn't counter the objection it exists to answer. The content already exists — this is a placement problem, not a content problem, which is why it's cheap.
→ Move 1–2 attributable testimonials (real name, role, specific result) near the signup CTA or wherever the "is this for someone like me / worth it" doubt actually arises on the page.
funnel step: engage → convert (objection handling at the friction point) | evidence: opinion | source: consensus
severity: major | effort: hours (assumes your CMS supports reordering sections without a dev — confirm; see _Could not check_)

**5. Kill autoplay-with-sound on the hero video**
Failure: unexpected audio on a video that autoplays is a well-documented way to lose exactly the mobile audience your paid spend is buying (74% of spend is mobile, where unmuted autoplay is most jarring and most often triggers an immediate bounce or mute-and-leave). This is filed as an accessibility/conversion check, not a nice-to-have.
→ Either mute-by-default (if your video embed exposes that as a CMS/player setting) or swap the autoplaying video for a static hero image using the ad's own key visual. The latter is squarely inside "copy and images."
funnel step: land → engage (first 5 seconds) | evidence: opinion | source: consensus + WCAG-adjacent accessibility guidance
severity: major | effort: hours

## Ruled out

- **Mobile LCP 5.2s (field data, "good" threshold is ≤2.5s).** This would normally jump straight to the top of the list — failing Core Web Vitals on the device carrying 74% of spend is an established-research trigger strong enough to override the usual ranking. It's ruled out here anyway, not demoted, because you have no route to engineering at all — not a slow queue, no queue. Naming it so it doesn't silently disappear: this is very likely your single biggest leak, and swapping the autoplay video for a static image (fix #5) may help LCP as a side effect, but that's not something this audit can promise or verify without a dev able to measure it. If a dev or agency ever becomes available even briefly, this is where to spend that time first.
- **14-field signup form.** Every field costs conversion (non-linearly — no trustworthy percentage exists to quote you). Ruled out because the form lives in a form stack you can't touch, not because it's a small leak.

## Test, don't guess

Nothing to add here. Below the volume floor, with no dev/build capacity to run a real experiment anyway, the honest move is to ship the well-evidenced removals and edits above and monitor — not to frame anything as a formal test you can't properly power or validate.

## Not a problem

None verified. This wasn't a full page-checks pass (no URL, screenshots, or HTML were supplied) — it's a prioritization of a pre-identified issue list, so I have no basis to certify anything else on the page as fine. Saying that plainly rather than padding this section.

## Could not check

- The page itself (not fetched — no URL, HTML, or screenshots), so visual and offer/geo message-match axes, CTA count, price visibility, risk reversal, form field types/labels, and policy basics (business identifiability, privacy policy, consent banner) are all unverified.
- The ad creative, so visual match and offer match against the hero can't be confirmed beyond the headline mismatch you already flagged.
- Sessions, conversions, CPA/ROAS vs. target — volume floor not cleared, no segment reads possible.
- Whether creative fatigue or a tracking break is contributing upstream of the page (CTR/frequency trend, conversion-event firing) — not ruled out, just unchecked.
- Whether your CMS supports reordering the testimonials section without a dev (fix #4 assumes yes).
- B2B vs. B2C — assumed B2C from the salary-claim framing; if Grainhollow sells to employers, the downstream metric of truth changes from enrollments to pipeline, and the 14-field form might legitimately be a qualification asset rather than pure friction (moot here since it's ruled out either way, but relevant if the form stack ever opens up).

## Re-check

- Fixes 1–2 (compliance removals): monitor for any change in ad disapprovals/account flags — should trend to zero, ongoing, no fixed date.
- Fix 3 (headline): land → engage rate on paid search, expected up.
- Fix 4 (testimonials): engage → convert rate, expected up.
- Fix 5 (hero video): land → engage rate on mobile specifically (74% of spend), expected up.
- Judge all four at matched attribution-lag maturity, one full business cycle after they ship — from today (2026-09-12), that's roughly the week of 2026-10-10 if shipped promptly. Working target: at least 3 of 5 predictions should move in the predicted direction, or the next pass should demand real analytics before ranking anything.
