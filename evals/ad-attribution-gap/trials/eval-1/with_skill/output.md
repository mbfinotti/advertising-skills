# March Attribution Reconciliation — Maren & Oak

## Answer to the actual question first

No — Meta, your analytics tool, and Shopify will never show the same figure, and getting them to match would mean one of the three numbers was faked. That's not a caveat, it's how these systems work: they're counting different things by design (an ad platform counts *claims* on a conversion, an analytics tool counts *observed* browser/session events, an order system counts *money received*). A report that ties out perfectly is a report where someone forced an adjustment to hit zero.

**What actually answers your CEO's ask:** anchor the one board-facing number on Shopify, because it's the only one of the three that reflects money that actually moved. Report:

> **March: 1,351 paid orders, $296,000 in net revenue (pre-refund-adjustment figure to confirm — see below), Meta and analytics are directional/in-platform signals only, not the number of record.**

Below is the full reconciliation: what explains the gap, what's still open, and what to pull next. Two inputs are missing that I can't fabricate — flagged explicitly rather than guessed at.

---

## 1. Headline

Anchor: Shopify (order/billing system) — **1,351 paid orders**, **$296,000 revenue** (basis needs one confirmation, see §2).

| Pair | Verdict |
|---|---|
| Meta vs Shopify (conversions) | Definitional causes plausible and expected in direction, but **not yet quantified** — pending two Meta Ads Manager pulls (§3) |
| Meta vs Shopify (revenue) | Partially explained (refunds); majority still open pending one Shopify pull (§3) |
| Analytics vs Shopify (conversions) | Provisionally **normal** — gap size and direction match the expected consent/cross-device pattern |

## 2. Normalization basis

- **Grain:** calendar month, March.
- **Date basis:** unconfirmed whether the Meta pull is interaction-dated (click/view) or event-dated, and whether it's lag-mature. Meta backdates conversions to the click/view date — if this pull was run in early April, late-March clicks converting in the first days of April are still landing and will keep changing the 1,912 figure. **Re-pull after the attribution window fully closes** (Meta's default window is commonly 7-day click / 1-day view, but confirm in Ads Manager → Attribution Settings — don't assume).
- **Conversion definition:** Meta "purchases" vs Shopify "paid orders" — need to confirm Meta's counting rule is set to "one conversion per click/person" and not "every." Also confirm whether Meta's 1,912 includes offline/CAPI-only events not tied to a Pixel session.
- **Revenue basis — the wrinkle you flagged, and it's the single biggest lever here:**
  - Meta's $412k is confirmed gross: includes tax and shipping, and (like every platform) does **not** reverse for refunds after the fact.
  - Shopify's $296k is *assumed* net of tax and shipping ("I think" isn't enough to build a $116k bridge on). **This needs one confirmation: pull Shopify's "Total Sales" for March alongside "Net Sales."** Total Sales = gross sales − discounts − returns + shipping + tax. Net Sales = gross sales − discounts − returns (excludes shipping/tax). If $296k is Net Sales, the gap to Meta's gross figure is expected and largely definitional. If $296k is actually Total Sales, the "excludes tax/shipping" assumption is wrong and the whole revenue gap needs re-deriving.
  - **Refund treatment nuance:** Shopify's Net Sales report attributes returns to the *original order's* date, not the refund's processing date. If any of the ~$18k in March refunds were against January/February orders, they won't show up as a reduction in March's $296k at all — they'd have reduced an earlier month's net sales instead (invisibly, unless that month's report is re-pulled). Confirm how much of the $18k is refunds-of-March-orders vs refunds-of-earlier-orders before treating it as a same-month bridge item.
- **Refunds vs Meta:** Meta's $412k has no refund reversal mechanism — the $18k (or whatever share is March-order refunds) sits in Meta's number regardless of what happened after purchase.
- **Order count vs refunds:** a refunded order typically stays counted in Shopify's "paid orders" (status becomes "refunded/partially refunded," not un-paid) — so refunds are a **revenue-only** bridge item, not a conversion-count one. Don't double-subtract them from the order count.

## 3. Variance table

| Source pair | Metric | Amount | % of gross gap | Bucket | Cause | Direction check | Evidence needed | Owner | Status |
|---|---|---|---|---|---|---|---|---|---|
| Meta (1,912) vs Shopify (1,351) | conversions | +561 | 100% | Unclassified | View-through + modeled (ATT-blocked/iOS) conversions likely included in Meta's count | platform high — passes | Ads Manager breakdown: click-through vs view-through, observed vs modeled | Media buyer | **Pull needed** |
| same pair | conversions | (subset of above) | — | Definitional (suspected) | "Every" vs "one" counting-rule setting unconfirmed | platform high if "every" — passes | Ads Manager attribution/counting settings | Media buyer | **Pull needed** |
| same pair | conversions | (subset of above) | — | Residual (suspected, top priority) | Pixel + Conversions API double-firing without shared event ID (order ID) — the standard Shopify+Meta CAPI dedup failure mode | platform high — passes | Events Manager dedup/match-rate report; confirm `event_id` = Shopify order ID on both browser and server events | Analytics eng. | **Investigate — top suspect given size of gap** |
| Meta ($412k) vs Shopify ($296k) | revenue | +$18,000 (floor) | 15.5% of gap | Definitional | Refunds recorded in Shopify, never reversed in Meta | platform high — passes | Shopify refund export for March, dated | Finance | Confirmed as a floor, pending the order-date-vs-refund-date question above |
| same pair | revenue | remainder, ~$98k | ~84.5% of gap | Definitional (expected) | Gross (Meta, incl. tax+shipping) vs assumed-net (Shopify) revenue basis | gross high — passes | Shopify "Total Sales" for March, to isolate tax+shipping precisely | Analyst | **Pull needed — see §2** |
| Analytics (1,104) vs Shopify (1,351) | conversions | −247 | 100% | Definitional/expected (Bucket 3 mechanism, stable pattern) | Consent-mode loss, ad-blockers, cross-device journeys the analytics tool can't stitch | analytics low — passes | Consent-rate and cross-device new-user-rate data, if available | Analyst | Provisionally normal — confirm stable vs prior months |

I'm not putting a number on the tax/shipping split — furniture shipping in particular varies too much by carrier model (free-shipping-absorbed-in-price vs itemized freight) to guess, and inventing a percentage here would be exactly the fabrication this process exists to avoid. The Total Sales pull resolves it in one query.

## 4. Residual statement

- **Revenue, Meta vs Shopify:** gross gap $116,000. Currently *quantified*: $18,000 (15.5%) as a confirmed floor. Everything else is *expected but not yet measured* — this isn't a residual in the Bucket 3 sense (no evidence it's a defect), it's an open normalization step. Once the Total Sales pull lands, expect explained share to jump well past 80%, because gross-vs-net is a mechanical, fully-explainable difference, not a tracking defect.
- **Conversions, Meta vs Shopify:** gross gap 561 (41.5% of anchor). **0% quantified today** — every candidate cause (view-through, modeled, counting rule, dedup) is plausible but unconfirmed. This is under the skill's 1.5x double-counting heuristic (1,912/1,351 = 1.41x), so it doesn't auto-flag as a defect, but 41.5% is large enough that I'm not calling it "normal" until the Events Manager dedup check comes back clean. **Don't report this pair as reconciled either way until that check runs.**
- **Conversions, Analytics vs Shopify:** gross gap −247 (18.3%). This sits inside the commonly-cited "under ~25% is normal" band for analytics-vs-order-backend, and the direction (analytics undercounting the money system) is the textbook pattern, not a flip. Passing provisionally — worth one check that this ratio is stable month over month before fully closing it.

Being direct about where this stands against the skill's own 80%-explained bar: **the revenue pair is at 15.5% explained today, the Meta-conversions pair at 0%** — both fail the threshold right now, not because there's a hidden defect, but because two specific reports haven't been pulled yet. That's a materially different message to the CEO than "we don't know why the numbers don't match" — the mechanism is understood, the number just isn't measured yet.

## 5. Defects and handoffs

| # | Item | Revenue/volume at stake | Fix effort | Position |
|---|---|---|---|---|
| 1 | Confirm Meta Pixel + CAPI event-ID dedup (order ID) | up to 561 orders / ~$116k of the gap if this is live double-counting | Under an hour to check in Events Manager; if broken, a config fix, not a rebuild | **Check first** — cheapest pull, largest potential single explanation, and the one mechanism that would actually make this a tracking defect rather than a definitional gap |
| 2 | Pull Shopify Total Sales for March | resolves ~$98k of the $116k revenue gap | Minutes — one report export | **Check first**, same batch |
| 3 | Confirm Meta attribution-window and counting-rule settings | affects how much of the 561-order gap is structural vs timing | Minutes to read Ads Manager settings | Do alongside #1 |

If #1 comes back clean (dedup is correctly configured, match rate is high), the 561-order gap is not a tracking defect — it's the normal shape of view-through + modeled conversions on an iOS-heavy Meta account, and it becomes a documented, non-closing delta like every other line here. If #1 comes back with a low match rate, hand off the fix to your tracking-implementation workflow — that's execution work, not reconciliation work.

## 6. Known deltas to carry forward (once the two pulls above land, re-derive each month rather than treating as a fixed offset)

- Meta over-reports orders vs Shopify by roughly 30–45%, driven by view-through/modeled inclusion — expect this band to hold, not vanish.
- Meta revenue runs gross; Shopify anchor should be read net. The tax+shipping load is furniture-shipping-specific and needs Shopify's own Total Sales figure each period, not a fixed percentage.
- Refunds are never reflected in Meta's revenue. At ~$18k/month scale, that's a recurring, not one-time, bridge item.
- Analytics undercounts orders by ~18% vs Shopify — expected consent/cross-device loss, not a defect, as long as it stays stable.

---

**For your CEO conversation:** report the Shopify number. Frame Meta's 1,912/$412k as "in-platform bid-optimization signal, gross and pre-refund by design" — not wrong, just not the same measurement. Once the two pulls above come back (same day, no engineering needed), I can tighten this to a fully quantified bridge with an explained share you can put a percentage on instead of "trust me."