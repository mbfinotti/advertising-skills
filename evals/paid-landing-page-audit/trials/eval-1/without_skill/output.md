## Diagnosis before the fix list

The pattern you're describing — CTR 1.7%→0.8%, frequency 2.2→5.9, nothing touched since March — is the textbook signature of **audience/creative fatigue**, not a landing page problem. Meta keeps re-serving the same ad to a shrinking pool of unique users; CTR craters as the novel audience is exhausted, and the auction raises your CPMs/CPCs to maintain delivery. That alone can double CPA with a page that hasn't changed at all.

**Before spending eng/design time on the page, pull one number: landing-page CVR (demo bookings ÷ landing page views) week-by-week over the five weeks.**
- If CVR held flat → the problem is 100% upstream (creative/audience), and page work won't move CPA. Refresh creative and expand/rotate audience instead.
- If CVR also declined → traffic composition has likely shifted (you're now reaching colder, lower-intent people as the core audience saturates), and the page fixes below matter.

Given you asked for the page audit specifically, here it is — ranked by expected CVR impact, assuming CVR did decay:

## Ranked page fixes

1. **Cut the form from 5 fields to 2–3 (name, work email, company).** This is the highest-leverage single change. Cold Meta traffic has near-zero intent commitment; every extra field compounds drop-off, and it compounds harder now that frequency is high (you're asking increasingly fatigued/skeptical repeat viewers for more information, not less).

2. **Add a real trust signal beyond 3 logos.** Logos alone don't close skeptical cold traffic. Add one proof point with a number attached (e.g., "cuts no-shows by 30%", a review-star widget, or a one-line customer quote with name/title). This matters more as frequency climbs — you're now converting on the 4th–6th exposure, not the 1st, so the page needs to do more trust-building work per visit.

3. **Rewrite the headline for specificity.** "Scheduling that runs itself" is a vague category claim — it doesn't say who it's for or what pain it removes. Tie it to a concrete outcome (e.g., "Stop chasing no-shows — scheduling that runs itself") and make sure it mirrors whatever hook is in the current ad creative; message-match mismatches get worse as Meta broadens delivery beyond your original audience.

4. **Check mobile rendering and load time specifically.** Meta demo traffic is majority mobile. A 5-field form and single CTA that look fine on desktop often have real friction on mobile (small tap targets, form fields below the fold). This is cheap to check and easy to miss.

5. **Add a lower-commitment secondary action alongside "Book a demo."** A single hard CTA is a big ask for someone on their 5th ad exposure who still hasn't converted. A soft option (60-second product video, "See how it works") captures people not ready to book a call and can recover some of the fatigue-driven bounce.

6. **Re-examine the subhead's claim.** "Calendar sync" is table stakes in scheduling SaaS, not a differentiator — it may not be answering the actual objection a prospect has at this point in the funnel. Replace or supplement with a specific differentiator or objection-handler (security/compliance badge, "no credit card required," integration count).

7. **Make the CTA outcome-specific, not generic.** "Book a demo" tells the visitor what happens, not what they get. Test copy like "See your calendar automate itself" — small lift, easy to ship, low risk.

**Bottom line:** page fixes 1–3 are worth shipping regardless. But if you skip pulling the isolated CVR number first, you risk burning a sprint on the page while the actual problem — audience fatigue at frequency 5.9 — keeps eating your CPA untouched.