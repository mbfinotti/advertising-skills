# Vessel & Vine — Audience & Exclusion Repair Plan

## Rationale block (read this before touching any platform)

Two separate failures, both diagnosed by the retargeting-funnel skill's failure-mode table:

| Your symptom | Skill's failure mode | Root mechanism |
|---|---|---|
| Ads for the exact grinder bought last week | "Dynamic ads showing bought/out-of-stock items" | No purchase-event suppression at the **catalogue/SKU level** on the dynamic ad campaign — only a broad past-purchaser exclusion exists (if any), and dynamic product ads don't inherit it automatically |
| Prospecting reach shrinking quarter over quarter with flat traffic | "Over-long converter exclusion" | The past-purchaser exclusion audience has no window sized to your business, so it accumulates every buyer indefinitely and eats a growing bite out of a finite, niche (specialty-coffee-enthusiast) prospecting universe |

**Data gap, named per skill rule:** I have no lag-distribution export (visit→purchase timing) and no traffic/funnel breakdown, so I cannot derive real stage boundaries. I'm using a **sector-typical proxy** (weakest, cheapest tier per the skill's proxy ranking) for considered specialty-retail purchases: ~65% convert within 7 days, ~85% within 21 days. **Every window below is provisional until you export a GA4/Shopify time-to-conversion report.** Your 2-month reorder cycle, by contrast, is real client data — it drives every exclusion-window number, which is why those are load-bearing and the stage windows are not.

---

## Problem 1: Dynamic ads re-showing what was just bought

**Diagnosis:** Your general "past-purchasers" exclusion (built for top-of-funnel prospecting) is not the same audience a dynamic/catalogue campaign checks. DPA/Advantage+ catalogue ads serve per-product, keyed to the catalogue feed — they need a **purchase-event-to-catalogue-ID suppression**, which the skill flags as a distinct fix from a general converter exclusion (an hour of work, but needs catalogue feed access, not just Ads Manager).

**Fix — and it must split by product type, because your two product lines behave differently:**

| Product type | Suppression window | Why |
|---|---|---|
| Durable gear (grinders, brewers, scales) | Long, ~540–730 days | Nobody rebuys a $250 grinder in the next year; there's no legitimate reason to ever re-show it |
| Consumables (beans, filters) | ~60 days (= your reorder cycle) | The item *should* reappear once the reorder cycle completes — but as a **refill/cross-sell offer**, not a "new purchase" dynamic ad |

Build two catalogue exclusion sets, not one:

- `EXCL_CATALOG_DURABLE_540` — Purchase event matched to catalogue product ID, durable product set, 540–730d.
- `EXCL_CATALOG_CONSUMABLE_60` — same mechanism, consumable product set, 60d, then the person rolls into the replenishment stage below instead of falling back into raw dynamic prospecting.

Apply both at the ad-set level on every dynamic/catalogue campaign, on every channel that runs one (Meta Advantage+ catalogue ads, and Google Shopping/dynamic remarketing off the same Merchant Center feed if you run it — audit both, it's minutes per channel).

---

## Problem 2: Shrinking prospecting reach despite flat traffic

**Diagnosis, mechanism:** A converter-exclusion audience with no window discipline only ever grows. Against a mass-market audience that barely matters; against a **niche specialty-coffee prospecting universe**, every purchaser permanently carved out of that pool is a real percentage of your addressable market gone. With a 2-month reorder cycle, a customer becomes reorder-ready long before an unbounded exclusion window lets them back into anything — so the excluded pool compounds every quarter while the pool it's excluding *from* doesn't grow to match. That's a mechanical, guaranteed reach decline, independent of anything else changing.

**Compounding factor to verify immediately:** Meta extended the retention ceiling on **purchase-event** website audiences from 180 to 730 days (effective May 2026), and existing purchase audiences were **auto-updated unless the account explicitly opted out**. If your agency's "ages ago" exclusion audience is purchase-event-based (likely), it may have silently jumped from 180 days to 730 days without anyone touching it — quadrupling the excluded population going forward on top of the underlying accumulation problem. **Check this today** in Meta Ads Manager → Audiences → the exclusion audience's retention setting.

**Fix:**

1. Rebuild the exclusion as `EXCL_PURCH_180` — 180 days (3× your 60-day reorder cycle, giving margin without choking prospecting, matching the ratio used in the skill's own worked B2C example for a comparable repurchase cycle).
2. If the audit above confirms the auto-extension, explicitly cap it back to 180 days rather than accepting Meta's 730-day default.
3. Repeat the audit on every other channel running a purchaser exclusion (Google Ads remarketing lists cap at 540 days regardless — check it isn't sitting at that ceiling either).
4. Diary this: re-audit exclusion windows every time a platform announces a retention-ceiling change, not just once.

---

## Full exclusion map (naming convention: `RTG_<depth>_<window>` include, `EXCL_<what>_<window>` exclude)

| Stage | Includes | Excludes |
|---|---|---|
| `RTG_CART_0-7` (hot) | Cart/checkout start, no purchase, 0–7d | `EXCL_PURCH_180` |
| `RTG_PRODUCT_0-14` (warm) | Product/category view, no cart, 0–14d | `RTG_CART_0-7`, `EXCL_PURCH_180` |
| `RTG_OBJECTION_8-21` | Aged S1/S2 members, no purchase, 8–21d | fresher stages, `EXCL_PURCH_180` |
| `RTG_LASTCALL_22-45` | Any above, no purchase, 22–45d | all above, `EXCL_PURCH_180`, `EXCL_REPEAT_ABANDON` (3+ abandonments/90d — don't let serial abandoners farm the discount) |
| `RTG_REPLENISH_45-75` | Consumable purchasers, 45–75d post-purchase | `EXCL_CATALOG_CONSUMABLE_60` lapses into this, not into cold prospecting |
| `RTG_WINBACK_90-180` | Any purchaser, no reorder 90–180d | current-cycle purchasers |
| Dynamic ads (all) | — | `EXCL_CATALOG_DURABLE_540`, `EXCL_CATALOG_CONSUMABLE_60` (item-level, see above) |
| **All prospecting/interest/lookalike campaigns** | — | `EXCL_PURCH_180` (resized, audited per Problem 2) |

Every stage excludes everything deeper/fresher plus converters — no user should ever occupy two stages at once. **Size-check every stage after these exclusions**, not before, against the platform floors (Meta ~1,000 practical, LinkedIn ~1,000–5,000, TikTok 1,000 — see reference table); if your niche audience is thin, collapse in this order before shipping: widen window → broaden trigger → merge adjacent stages → single combined warm pool. Don't be surprised if S3/S4 end up merged — that's a correct outcome for a small specialty retailer, not a failure.

---

## Cap sheet

Meta exposes no cap field on conversion objectives — these are cap-**proxies**, acted on manually against a 7-day rolling baseline:

| Stage | Cap-proxy | Act when |
|---|---|---|
| Hot / warm retargeting | 4–6/week | CTR −15–20%, CPM +10%, or negative feedback rising |
| Last-call (discount) | 5–7/week | Same signals, reviewed every 2–3 days (small, discount-bearing pool decays fastest) |
| Prospecting | 2–4/week | Same signals, reviewed weekly |
| Replenish/win-back | 2/week | Reviewed weekly — this is goodwill messaging to existing customers, don't burn it |

---

## Measurement plan

- Per stage: spend, reach, frequency, CTR, CPM, platform CPA, new-vs-returning share.
- Blended sanity metric: monthly revenue ÷ total marketing spend, trended — watch this specifically over the next 2 quarters to confirm the exclusion-window fix actually recovers prospecting reach/CPA rather than just reshuffling platform-reported numbers.
- **Incrementality test (schedule now, don't skip):** 15% audience holdout on `RTG_CART_0-7` and `RTG_LASTCALL_22-45` for 6 weeks — these carry the highest "would have bought anyway" risk. Decision rule: if hot-stage holdout lift is indistinguishable from zero, fold its budget into prospecting regardless of its platform ROAS.
- Track the exclusion-window fix itself as a natural before/after: prospecting reach and CPM for the 8 weeks before vs. after resizing `EXCL_PURCH_180`, isolating this one change.

---

## Design-gate check

- [x] Failure modes identified and mapped to concrete fixes.
- [x] Exclusion map complete and mutually exclusive, converters excluded on every stage with an explicit window (180d).
- [x] Discount confined to the final stage only.
- [x] Cap-proxies with detection signals defined per stage.
- [ ] **Stage boundaries are proxy-based, not derived from your lag data — provisional, flagged above.** Export a time-to-conversion report to firm these up.
- [ ] Tracking not independently verified in this pass — confirm purchase and catalogue-ID events are firing correctly before wiring the new exclusions (this is a hard prerequisite; don't build audiences on events you haven't checked).
- [ ] Creative concepts per stage not scoped here — that's copy/creative work, not audience work.

---

## What to hand off elsewhere (not audience-design work)

- Verify event tracking (purchase + catalogue-ID matching) before wiring any of this.
- Splitting budget across prospecting vs. retargeting once reach recovers — that's a spend-allocation exercise, not an audience one.
- Ongoing frequency/CTR decay monitoring after launch — a standing job, not a one-time setup.
- The actual ad copy for objection-handling and replenishment stages — separate creative work.

**This week's action order:** (1) audit the Meta purchase-audience retention setting today, (2) rebuild `EXCL_PURCH_180` at 180 days across every channel, (3) add the two catalogue-level suppressions to every dynamic/catalogue campaign. All three are minutes-to-an-hour of work each and stop the bleeding on contact; everything else in this plan can follow once you've pulled a real lag report.