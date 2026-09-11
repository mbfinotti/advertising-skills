# Channel plan — Vantabyte, 2026-09-12

## 1. Economics

- Price: $120/month self-serve · Margin: 85% → contribution/sale = $102/month.
- Break-even ROAS = 1/0.85 ≈ 1.18x — shown for completeness; payback is the real gate for a B2B SaaS.
- LTV/retention: **not provided.** Everything below uses payback-derived CAC ceilings, not LTV. Fill in real retention after the first cohorts hit 6 months and re-run this gate.
- Allowable CAC by payback target (= months × $102):

| Payback | Allowable CAC |
|---|---|
| 3 mo (aggressive) | $306 |
| 6 mo (working ceiling — used below) | **$612** |
| 9 mo | $918 |
| 12 mo (justified by "no deadline pressure") | $1,224 |

- Results due by: no date. One-off vs. compounding: compounding (year-long build). Effort ceiling: not stated — assumed lean team, no dedicated video/content function. Confirm.

## 2. Deleted channels

| Family | Gate failed | Reason |
|---|---|---|
| Paid search | Disqualifier | Zero category search volume — you invented the category. Profile: "Disqualified by: no category search volume." |
| Automated cross-surface search | Disqualifier | Same — no query volume on any surface for a term nobody knows to search. |
| Retail media | Disqualifier | Not sold on a marketplace. |
| B2B professional networks | Affordability | Profile requires ~$10–15K LTV minimum to recoup the CPC premium. At $120/mo, even 36 months' tenure ≈ $4,320 LTV — well short. (The skill's own negative example fails this same gate at $199/mo; $120/mo fails harder.) |
| Connected TV | Disqualifier + affordability | No Q9 evidence buyer is there; $5K+ programmatic/$50K+ direct floor and $1.5–15K+ production don't fit a lean self-serve budget. |
| Short-form video | Parked, not deleted | No Q9 evidence, and (assumed) no in-house video team for its 10–20-variant, days-to-fatigue burn. Confirm creative capacity if you want this reconsidered. |
| Paid review listings (G2/Capterra/TrustRadius) | Parked — price-discovery bucket | An invented category has near-zero organic comparison traffic today. Claim free listings now (zero cost); revisit paid tiers once comparison search exists. |

## 3. Candidates ranked by efficiency — survivors only

| Rank | Family | Value (presence/reach/target/measure) | Effort (burn/skill/reversibility) | Value÷Effort |
|---|---|---|---|---|
| 1 | **Podcast/audio** | 5+5+4+2 = 16 | 2+4+4 = 10 | **1.6** |
| 2 | Generic paid social (X/Reddit-style, *not* the deleted professional-network family) | 2+2+3+5 = 12 | 4+3+1 = 8 | 1.5 |

- Podcast's value-5 on audience presence and reachability is direct evidence: 200-signup survey, top answer, buyer named the exact 2–3 shows. That's the strongest Q9 evidence this framework recognizes.
- **This is the "starved family" case.** Default ordering ranks podcast near-last on raw efficiency. It's promoted to primary because all four conditions hold: (1) strong Q9 evidence, (2) no capture family reaches this buyer — category literally doesn't exist as search intent, (3) budget clears the family's floor *by concentrating on known-good shows* (math below), (4) deadline is a full year out. Here the ratio already agrees with the promotion, so there's no conflict to resolve.
- Paid social is close on paper but weak on evidence (nobody in the survey named it) and worse on effort (a standing 8–15-variant creative job with no stated team). Not funded now; it's the fallback if podcast fails, not a co-primary.
- Short-form video / paid review listings: parked, unranked, not scored — would be invented precision without evidence or a creative-capacity answer.

## 4. Primary recommendation

**Podcast/audio, 100% of the $9,000/month.** Demand-creation is structurally required (zero search volume), and the buyer survey is about as good as Q9 evidence gets. The open question isn't *whether* — you'd already decided that — it's *how not to waste it*.

## 5. Funding plan — and the structure you asked for

**Start with one show, not two or three at once.** Podcast is explicitly flagged "hard to read" in the profile — running two unproven shows simultaneously halves your signal on the channel's hardest-to-measure family, with no prior data at Vantabyte to fall back on.

- **Rank your named shows first.** Score each of the actual 2–3 shows your survey respondents named against: SRE/platform-engineer % of listenership (ask the ad-sales rep directly, not the public download count), current downloads/episode, whether they sell host-read mid-roll vs. only dynamic ad insertion, minimum flight length, and — important for a category this small — **category exclusivity** (many ad-supported shows won't run two on-call/incident tools in rotation; lock this in the contract). Flag: if "Page It to the Limit" is one of the shows named, note it's produced by PagerDuty, a direct competitor — a real conflict, not just a cost question.
- Illustrative shows worth running through that rubric if you need to widen the shortlist beyond your survey's named two or three: *Software Engineering Daily*, *The Changelog*/*Ship It!*, *The New Stack Makers*, *Screaming in the Cloud*. I can't verify current rates or sponsor availability from here (no live web access this session) — treat these as starting points, not a vetted list, and reverify before booking. **Your survey's named shows are the real answer; I don't have that data — surface it if it's sitting in the free-text responses.**
- **Book a full-quarter flight on the single best-fit show**, weekly host-read mid-roll, sized to ~$5,000–7,500/month based on typical CPM ranges ($25–50 host-read mid-roll). That's the primary spend.
- **Hold the remaining $1,500–4,000/month in reserve** — for a pre-roll add-on on the same show if it's working, or to open (not yet pay for) booking conversations with show #2, since podcast has long lead times and you'll want that relationship warm before Q2. Don't force it into a second placement just to "use" the $9K — that's the exact split-thin anti-pattern the concentration rule exists to prevent.
- Give the host real product access (a free account, a real on-call story) — host-read ads land harder when the endorsement is genuine, which matters more here than on a cold-traffic channel.

**Reality check on affordability, both directions:**

| Scenario | Downloads/ep | CPM | Cost/ep | Response→trial→paid (illustrative) | CPA |
|---|---|---|---|---|---|
| Base | 20,000 | $35 | $700 | 0.75% → 10% → 20% | ~$117–233 |
| Conservative | 30,000 | $40 | $1,200 | 0.3% → 10% → 15% | ~$889 |

Both anchor conversion assumptions I can't verify for your funnel — that spread ($117 to $889) is exactly why this is a quarter-long validation flight, not a scale-up. Base case clears the $612 (6-month) ceiling comfortably; conservative only clears the 9–12-month ceiling. This is where the "no deadline pressure" answer earns its keep — it buys you room to let the 9–12-month ceiling apply if the first read lands there, instead of killing a channel that's actually working.

## 6. Test design

- **Price discovery** here isn't a $100 spend test (podcast inventory is sold in booked slots, not bid impressions) — it's getting real quoted CPMs, avails, and minimum flight length from each show's ad-sales rep. Do this before the plan's numbers above are treated as real.
- **Real test:** one full quarter (13 weeks / ~12–13 episodes), same host-read mid-roll slot, one unique promo code + vanity URL for the show, tracked promo code → trial → paid in-app. Don't split codes across multiple script angles mid-flight — volume is too small to read a split; rotate the angle quarter to quarter, not week to week.
- **Pass:** cost per *paid* customer (promo-code attributed) ≤ $612 at a readable sample by end of quarter — loosen to $918 if retention data by then supports a 9-month payback.
- **Kill:** 2–3x target CPA spent (~$1,200–1,800) with near-zero paid conversions after a full multi-episode read → diagnose (script, landing page, offer, host delivery) before rebooking, and before concluding podcast itself doesn't work.
- The false-negative trap applies doubly here: a 4-week test would read as failure even on a working show — hold to the full quarter.

## 7. Second-show and next-channel triggers

- Add show #2 **only** once show #1's quarter completes and passes at significance — funded from the reserve, not a fresh split of the original $9K.
- If show #1 fails kill criteria: move to show #2 next (same Q9 evidence), not to paid social or a wider spread — diagnose the failure before assuming the *family* doesn't work.
- Only if **both** named shows fail: revisit the ranked table — paid social is next in line, and the parked price-discovery bucket (paid review listings, once the category has real comparison traffic) becomes worth a look.
- Budget-scale trigger (~$50K/month practitioner breakpoint) is a long way off at $9K — not the near-term lever; the near-term lever is show #1 passing.

## 8. Measurement approach

- Vanity URL + unique promo code per show → trial signup → paid conversion, tracked in-app. This is the profile's explicit requirement for podcast, not optional.
- Add "How did you hear about us?" at signup immediately — mandatory the moment a creation channel enters the mix, costs one form field.
- Never read this channel off downloads or reach alone — cost-per-*paid-customer* via the promo code is the only number that matters.
- Skip MER (not ecommerce revenue) and incrementality/geo-lift for now (single-show, $9K/month is far below the spend that justifies a holdout design) — revisit only if the mix scales to multiple shows plus other channels simultaneously.

## Open items to close before you book anything

1. **Name the actual 2–3 shows from your survey** — the whole plan's "which shows" hinges on data I don't have.
2. Confirm each show's real SRE/platform-engineer listener share and current downloads/episode directly from their ad-sales rep, not a public estimate.
3. Confirm creative/content capacity (even a lean team) — it decides whether short-form video stays parked or comes back into the ranking later.
4. Once the first cohort hits 6 months, plug real retention into the CAC ceiling and re-run step 1 — everything above is provisional on that number.