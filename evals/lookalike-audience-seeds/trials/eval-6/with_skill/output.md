# Nordvik Living — Lookalike Seed Plan (Meta)

## Stop: the plan can't upload yet

Workflow step 2 (privacy/consent gate) is a hard stop, and it fails on what you've described:

- **No documented lawful basis/consent confirmed** for uploading this list to Meta as a customer audience. Hashing (SHA-256, which Meta does on ingest) does not remove this requirement — it's still personal data under GDPR/UK GDPR.
- **"Opt-outs get processed inside each ad platform separately when someone complains"** is exactly the anti-pattern the skill calls out: suppression/opt-outs/deletions must be enforced **once, in your customer database, before any export** — not reactively per platform after a complaint. Right now, a customer who opted out on Klaviyo/your CRM but never happened to complain to Meta stays live in every future re-upload.
- Four of your five markets (DE, FR, NL, SE) are EEA; the UK runs the UK GDPR equivalent. All five need this fixed, not just the EU four.

**Before any list goes up:** maintain a single opt-out/do-not-contact flag in your customer database, filter it out at export time, and confirm you have a lawful basis (consent captured at checkout/account creation, most likely) for ad-platform matching specifically. Everything below assumes this gets fixed — I haven't sized anything against an unconsented list.

## Fix the shape of the plan: one global list is the wrong ask

Meta lookalikes are country-scoped by construction — there's no such thing as a single lookalike that targets five countries at once. One combined list doesn't produce one weaker lookalike, it produces one seed feeding **five separate audience builds you'll create anyway**, just without you having chosen the per-country composition. So the real unit of work is **one seed + one lookalike per country**, not one combined upload.

## Sweden can't support a customer-list lookalike — don't try

120 total customers, before any RFM narrowing or negative-selection stripping (refunders, employees, trade/wholesale). Run the arithmetic honestly:

- Best case: keep all 120 (no RFM tier cut, since narrowing further only shrinks it more), strip a handful for refunds/employees/trade accounts → ~100–115 rows.
- Meta's good-list match rate is 50–80% → **~55–90 matched**.
- Floor is 100 matched. **This fails even in the optimistic case**, and it fails the 1,000–5,000 recommended range badly.

Fallback ladder, walked in order:
- **Rung 1 (enrich):** delete it — a vendor contract and DPA for 120 customers in one market isn't proportionate, and you're a solo operator with no procurement bandwidth.
- **Rung 2 (widen recency):** empty — 120 is already your entire Swedish customer base, there's no older cohort to add.
- **Rung 3 (stack adjacent segment):** the one real lever — don't split Sweden by product line at all, keep furniture+lighting combined for SE only. It still likely lands under 100 matched, so it delays the failure, doesn't fix it.
- **Rung 4 (switch source), the actual fix:** build Sweden's audience from a **pixel/conversion-based seed** (SE site purchasers or add-to-cart events), not a customer-list upload. Meta's floor for a conversion-based lookalike source is 100 unique conversions — a rolling, growing number from live traffic, not capped at today's 120 historical customers. Bonus: no CSV, no customer-list consent gate, lower compliance cost.

**Recommendation:** exclude Sweden from the customer-list workflow entirely. Build it later as a pixel-sourced lookalike once you're seeing meaningful SE checkout volume; until then, run interest/Advantage+ targeting there instead.

## Splits: cap it to what one person can actually maintain

The skill's own guidance: "two splits is fine, six is a part-time job nobody was assigned," and refresh here is manual ("whenever I remember") — no automated sync, no second person. Reconciling that against your ask:

| Split | Recommendation | Why |
|---|---|---|
| Country | **Do it — mandatory** | Not optional; lookalikes are country-scoped |
| Product line (furniture/lighting) | **Phase 2, not launch** | Real signal value, but doubles your audience count (4 countries × 2 = 8) and doubles refresh load on day one |
| High-AOV | **A one-time split test, not a standing audience** | Run it once the country seeds are live and stable, keep whichever wins, don't run both permanently |
| Language | **Drop it** | Your five markets already map ~1:1 to language; it duplicates the country split for no new signal |

**Staged rollout:**
1. **Now:** 4 country lookalikes (DE, FR, NL, UK) from combined furniture+lighting seeds, Sweden excluded per above. This is the "one splits" tier — sustainable manually.
2. **Once refresh is reliably happening on schedule:** add the product-line split (8 audiences total). Don't add it before the cadence is proven, or you'll be maintaining 8 stale lists instead of 4 fresh ones.
3. **Separately, once the country seeds have a cohort's worth of data:** run the high-AOV split as a test against the full-country seed for one market, not all four at once. If it's a real change (a different model, a retired seed version), it's expensive enough to consider a geo holdout rather than a same-platform split test.

If/when product line ships, exclude the full-country audience and the high-AOV audience from running simultaneously in the same market — they'd overlap by construction (one is a subset of the other), which is the cannibalization case the skill flags, not a genuine A/B.

## What I still need from you before I can fill in real numbers

I won't invent a per-country breakdown, identifier density, or value-column provenance — here's exactly what's missing:

1. **Per-country customer counts** for DE, FR, NL, UK (you gave the ~18,000 total and the ~120 SE figure, not the other four).
2. **Identifiers per row** — email only, or also phone/postal? (Multiple identifiers materially lift Meta match rate.)
3. **Is there an AOV/value field**, and if so is it order revenue, margin, or a modeled LTV? This decides whether "high-AOV split" is a simple threshold segment (no extra Meta setup) or a true value-based audience (needs a separate Meta ToS acceptance, margin/LTV only, positive values, no identical values, whale-capping).
4. **Recency**: what share of the ~18,000 purchased in the last 90 / 180 days? Furniture and lighting are low-frequency, high-ticket categories — a "2+ orders" pattern filter will likely strip most legitimate one-time buyers, so I'd lean toward a top-20–25%-by-ticket-value cut over a frequency-based one. Confirm that's true of your base before I commit to it.
5. **Baseline numbers to grade against**: current new-customer CPA, and current 90-day cohort LTV of acquired customers. Without these the seed can't be graded — first cohort becomes the baseline-setting run.
6. Any **trade/interior-designer/wholesale accounts** mixed into the consumer list? Common in furniture — these need stripping in the negative-selection pass alongside refunders, chargebacks, discount-only buyers, and staff.

## Seed specification (4 country audiences — DE / FR / NL / UK identical shape, numbers pending your answers above)

```
SEED SPECIFICATION - <country>-combined v1, 2026-09-12
platform        : Meta | audience type: lookalike (standard, unless AOV test later promotes value-based)
definition      : identity-resolved <country> customers, top 20-25% by ticket value OR RFM Champions+Loyal
                  (pending recency data), last purchase <= 180 days
value column     : none at launch (segment split, not value-weighted) - revisit once value-column provenance confirmed
row count        : TBD - need per-country customer count
identifiers/row  : TBD - confirm email/phone/postal
expected match   : 50-80% (Meta good-list band) - refine once identifier density known
effective seed   : TBD = row count x match rate, vs floor 100, target 1,000-5,000
fallback used    : n/a until effective seed computed
exclusions       : refunders, chargebacks, serial returners, discount-only buyers, employees, trade/wholesale
                  accounts stripped from seed; all-customers suppression audience excluded at delivery
consent basis    : BLOCKED - lawful basis not confirmed; opt-outs currently per-platform, not warehouse-enforced
refresh          : proposed monthly manual export | owner: <you> | bridge until volume justifies automated sync
measurement      : new-customer CPA target TBD (no baseline given); cohort LTV at 90/180/365d by seed version
re-check         : one cohort window after launch (set once live date is known)
```

```
SEED SPECIFICATION - sweden-pixel v1 (deferred)
platform        : Meta | audience type: lookalike, conversion-based (not customer-list)
definition      : SE site purchasers (pixel/CAPI), rolling window, not the 120-row historical customer list
row count        : n/a - sourced from live events, no upload
expected match   : n/a - native platform signal
effective seed   : needs 100 unique conversions in-window to clear the conversion-based floor; track and revisit
                    once SE traffic/checkout volume supports it
fallback used    : ladder rung 4 (switched from customer-list to platform-native source) - the 120-customer
                    list cannot clear any floor even in the best case
consent basis    : n/a - no personal data leaves the platform
status           : BUILD LATER, once SE conversion volume is tracked and meaningful
```

Once you answer the six questions above and the consent gate is closed, I'll drop real numbers into the four country blocks and confirm each clears its floor before you upload anything.