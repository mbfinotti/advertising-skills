# Landing Page Audit — Marrowfield Goods, /copper-set

A quick note before the report: this skill normally runs a structured interview before opening anything. You've supplied enough to audit the click path, the offer match, and the checkout friction point directly, but several inputs the skill asks for (funnel-step analytics, page render/screenshots, prior test history, deadline, who implements fixes, effort ceiling, page ownership) weren't provided. I've built the report on what you gave me and listed every gap under **Could Not Check** rather than guessing — treat those as open questions before you commit build time.

```
LANDING PAGE AUDIT - marrowfieldgoods.com/copper-set, 2026-09-12
traffic        : Meta, cold prospecting | model: B2C
goal           : purchase | downstream truth: revenue
window         : last 28 days | volume: 46,000 sessions, 380 purchases | volume floor: cleared
economics      : CPA $58 vs target $35 - gap: 1.66x
inputs         : ad creative: yes | analytics: aggregate only (no funnel-step breakdown) |
                 recordings/heatmaps: none set up | page: described, not fetched/rendered
```

## VERDICT

The page is very likely the problem, and the break is severe enough to act on even though two upstream checks this skill normally clears first couldn't be run: I have no CTR/frequency trend to rule out creative fatigue, and no confirmation that the purchase event fires once and reconciles with orders. Get those two checked in parallel (`ad-creative-fatigue`, `ad-conversion-tracking`) — but don't wait on them to ship what's below.

The reason I'm not waiting: the ad promises a specific product, a specific price, and a specific discount, in a chef-searing-steak visual. The landing page confirms none of it. Headline, hero, and CTA all break message match at once, and the price the ad leads with is hidden behind an extra click. A 1.66x CPA gap is exactly the size of gap this pattern produces (see the skill's own worked reference case: a 1.6x gap from an identically-shaped verbal+visual message-match break). I'm not promoting offer clarity to the top of the list for this — the gap is a margin, not a multiple-of-target scale, and there's no funnel data showing visitors leaving before any interaction — the standard efficiency ranking below already puts the highest-leverage fix first.

## FIX NOW (max 7, ranked by efficiency — best step-unblocked-per-effort first; policy-risk items lead regardless of ratio)

**1. Offer, price and CTA vanish between ad and page — bait-and-switch policy risk**
The ad leads with "5-piece copper set — 35% off this week" and CTA "Shop the set." The page shows no price, no set count, no discount anywhere before a click-through, and its CTA ("Explore our collections") routes to browsing rather than the promised set. This is a policy-risk finding (Meta reviews ad and destination together; a price/offer that shifts between click and page reads as bait-and-switch), which is why it leads the list ahead of pure efficiency ranking. → Point the primary CTA directly at the copper-set product (button copy: "Shop the copper set"), and surface the price and "35% off" on the landing page itself rather than one click deeper.
`funnel step: land → product page click-through | evidence: opinion | source: consensus (message match) + platform-policy | severity: critical | effort: hours`

**2. Hero headline breaks verbal match**
"Cookware, reimagined" confirms nothing the ad promised — no product, no price, no urgency. A clicker who came for "35% off the copper set" lands on a brand-positioning line. → Rewrite the headline to state the ad's specific promise in close to its own words.
`funnel step: land → engage | evidence: opinion | source: consensus | severity: critical | effort: hours`

**3. Hero visual breaks visual match**
The ad is concretely product-led — a chef searing steak in the copper pan. The page hero is an abstract texture moodboard with no product visible at all. Clickers recognise a page by sight before they read it; this hero reads as a wrong turn. → Replace or supplement the hero with a product shot or a still frame from the ad itself (near-zero-cost asset reuse).
`funnel step: land → engage | evidence: opinion | source: consensus | severity: critical | effort: hours`

**4. Shipping cost withheld until the payment step**
Extra costs revealed late is the single most-cited reason for checkout abandonment in Baymard's B2C survey data. Here it's revealed at the last possible moment — payment. → State shipping cost (or a flat-rate/free-shipping threshold) on the product page or landing page, before checkout starts.
`funnel step: add-to-cart → purchase | evidence: opinion (no step-level checkout data to upgrade this to observation) | source: research (Baymard) | severity: major | effort: days`

## RULED OUT

None removed. Effort ceiling, dev-team access, and who owns this page weren't part of what you sent — nothing above was deleted on those grounds. If any of fixes 1–3 sit outside a copywriter/marketer's access (e.g., the hero is templated by a design system only engineering can touch), say so and I'll re-rank; that would push fix 4 up and could delete none of them, since none require a rebuild, only a CMS/copy change and a re-pointed link.

## TEST, DON'T GUESS

- **How much price to show on the landing page itself vs. one click away on the product page.** Fix 1 recommends surfacing price directly, but some DTC pages hold price for the product page successfully when the CTA is unambiguous and exactly one click from it. Volume here (380 purchases/28 days) clears both this skill's volume floors, so a real A/B test is viable — judge it on land → purchase rate, full business cycle, no early stopping.
- **Whether the moodboard hero has any role below the fold** (texture/brand storytelling) worth keeping once a product-led hero leads. Judge on scroll depth if you get scroll tracking installed (see Could Not Check).

(Framing: a portfolio of bets — most CRO tests don't move their target metric when tested; ship fixes 1–4 regardless of these.)

## NOT A PROBLEM

- **Volume floor:** 46,000 sessions and 380 purchases in 28 days clears both this skill's floors (1,000 sessions/30 conversions, and the ~100/month floor for recommending A/B tests) — the numbers above support a real comparison, and a test is a legitimate validation path here, not a false promise.
- **CTA hierarchy:** one primary CTA button is described, no competing secondary CTA — the multiplicity is fine; its wording and destination are the problem (fix 1), not its prominence.

## COULD NOT CHECK

- **Upstream ad-account signals** — no CTR/frequency trend supplied, so creative fatigue can't be ruled out per this skill's own workflow step 2. Get `ad-creative-fatigue` run in parallel.
- **Conversion tracking integrity** — no confirmation the purchase event fires once and reconciles with order data. Every CPA number above should be treated as provisional until `ad-conversion-tracking` confirms it.
- **Analytics funnel by step** (land → engage → product-page click → add-to-cart → checkout → purchase) — only aggregate sessions/purchases were supplied. Without it, every finding above stays at "opinion" rather than upgrading to "observation," and I can't tell you which step is actually leaking the most.
- **Session recordings / heatmaps** — confirmed not set up. No rage-click, dead-click, or scroll-depth evidence exists to back the hero/CTA calls with behavioral data.
- **Rendered page** — no URL, HTML, or screenshots were provided, only described elements. Everything about speed (Core Web Vitals), accessibility (contrast, tap targets, keyboard focus), exact form/checkout field count, and layout stability on the 81%-mobile traffic is unchecked.
- **Geo/language mix, post-purchase path, prior tests on this page, deadline, implementation owner, effort ceiling** — none supplied; all would re-rank or prune the list above once known.

## RE-CHECK

- Fixes 1–3: land → product-page click-through rate on mobile paid social, expected up, judged 2026-10-10 (one business cycle from this audit, matched attribution-lag maturity).
- Fix 4: add-to-cart → purchase rate, expected up, same date.
- Track whether fixes shipped despite the tracking-integrity and funnel-step gaps above under "Could Not Check" miss their prediction more often than the rest — if so, that's the argument for getting analytics wired before the next audit.