# Pellonia Home — Pre-Launch Check

**Verdict: 🔴 NOT ready to launch as planned.** One blocker (untested pixel) touches all three campaigns. Fix that first.

## 🔴 Blocker #1 — Untested pixel (blocks all 3 campaigns)

- Installed last week, never verified. Do not trust it.
- A "fully-automated multi-surface shopping campaign" bids on conversion signal. With zero verified signal, the algorithm optimizes against noise or nothing — the entire $40/day learning budget burns with no usable data.
- Same risk applies to the LinkedIn side if any website conversion (not just the native form) feeds optimization.
- **Do before spending another dollar:**
  1. Fire test events on every page in the funnel (product, cart, checkout, thank-you).
  2. Confirm Purchase/Lead events carry correct value + currency, not just "fired."
  3. Check for duplicate firing (double-counted conversions inflate reported ROAS and mislead bidding).
  4. Verify the conversion action inside the ad account is mapped to that pixel/event, not a stale or duplicate one.
  5. Place one real test order end-to-end and confirm it lands in the ads platform within the expected attribution window.
- **Until verified:** run the shopping campaign on a traffic/clicks objective or manual bidding, not full auto-bidding. Switch to auto-bidding only after a clean test conversion is confirmed.

## 🟠 Campaign 1 — Fully-automated shopping campaign ($40/day, 8 products, 6 creatives)

- ⚠️ Thin inputs. 8 SKUs and 6 creative assets are below the volume this campaign type wants to diversify against; expect a longer, noisier learning phase.
- ⚠️ Brand-new account + brand-new pixel + zero purchase history = no signal to set a target ROAS/CPA against. Don't let the freelancer set one on day one — start uncapped (maximize conversions, no target) for 2–4 weeks minimum.
- ✅ Check product feed status in Merchant Center — all 8 products must show "approved," not "pending" or "disapproved." A single disapproved SKU with a small catalog meaningfully shrinks the pool the algorithm has to work with.
- ✅ Confirm billing method is active — new accounts sometimes have a hold on the payment method that silently caps delivery.
- ℹ️ $40/day is low for a "fully-automated" format designed for volume. Set expectations: this will look slow for the first 1–2 weeks regardless of tracking quality — don't let anyone read "no conversions" in week 1 as a targeting problem before the pixel is even confirmed.

## 🟠 Campaign 2 — Retail-media display, 970×250, barely spending

- ❌ Don't raise bids yet. "Approved" is a creative content check, not a delivery signal — raising bids blind treats the wrong lever.
- **Diagnose before touching bids:**
  - Delivery/eligibility status — look for "limited by budget," "limited by bid," "in review," or "pending activation" flags.
  - Flight dates — confirm the campaign's actual start date has passed, not just upload date.
  - Audience/placement size — 970×250 (billboard) has less available inventory than standard IAB sizes; a narrow audience combined with a large-format-only banner can genuinely starve delivery independent of bid.
  - Budget pacing type (even vs. accelerated) and daily cap — an even-pace setting on a low daily cap looks like "barely spending" by design.
  - Payment method status — a declined card halts delivery silently on most retail media platforms.
- ✅ Only raise bids after confirming none of the above explain the low spend. If eligibility/budget/payment are all clean and it's still under-delivering, bid is the correct lever — raise incrementally (10–20%), not a large jump.

## 🔴 Campaign 3 — LinkedIn lead form, 14 qualifying fields

- ❌ 14 fields will collapse completion rate. LinkedIn's own guidance and industry data both show completion drops sharply past 3–5 fields.
- **Fix before publishing:**
  - Cut to 3–5 fields. Lean on LinkedIn's native auto-fill (name, email, company, job title, company size) — these cost the user zero typing.
  - Push deep qualification (the other ~10 fields) to a post-submit step: SDR follow-up call, progressive profiling in the CRM, or a gated second-step form. Don't ask for it upfront.
  - Every extra custom field is a point of abandonment on a platform where the whole value proposition is a low-friction native form.
- ✅ Test the lead → CRM handoff end-to-end, not just the form itself. Lead Gen Forms commonly fail silently at the sync step (broken webhook/Zapier/native integration) — submit one test lead and confirm it actually lands in the CRM before launch.
- ✅ Confirm the LinkedIn Insight Tag is installed and firing on any pages this campaign links to outside the native form (if applicable).

## Cross-cutting items (all 3 campaigns)

- 🔐 Since the brand is based in France/targets EU traffic: confirm a consent banner is live and Google Consent Mode (or platform equivalent) is configured before the pixel starts collecting data. An untested pixel launched without consent handling is a compliance risk on top of a tracking risk.
- ℹ️ Keep UTM parameters consistent across all three campaigns so GA4/analytics attribution isn't fragmented once traffic starts.
- ✅ New ad accounts get extra scrutiny — keep initial ad copy/creative conservative to avoid day-1 disapprovals eating into the learning window.

## Go / No-Go summary

| Campaign                 | Status               | Action                                                               |
| ------------------------ | -------------------- | -------------------------------------------------------------------- |
| Shopping (multi-surface) | 🔴 Hold auto-bidding | Verify pixel end-to-end first; launch on traffic objective meanwhile |
| Retail-media display     | 🟠 Hold bid increase | Run delivery diagnostics before touching bids                        |
| LinkedIn lead form       | 🔴 Hold publish      | Cut to 3–5 fields; test CRM handoff                                  |

**Next step:** verify the pixel today. Everything else — bidding strategy, bid increases, form field count — is downstream of trusting that data.
