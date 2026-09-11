# Lexon Legal Software — Negative Keyword Pass (Google Ads, first cleanup)

**Two things to confirm before you apply this** (affects 2 of the 8 rows below — everything else is ready to apply as-is):
1. Do you ever deliberately bid CaseHawk's brand (conquesting), or is that unintentional?
2. Can you confirm edit access at account level and shared negative lists, not just campaign/ad group?

I assumed no deliberate competitor bidding and full edit access. Adjust the two flagged rows if either assumption is wrong.

## 1. Summary

- Spend analyzed: $14,200 (30 days, non-brand)
- Click gate tightened to **10 clicks** (avg CPC ~$7 is well above the $3 trigger for tightening)
- Cost gate: **$375–$500** zero-conversion spend (1.5–2x target CPA of $250), regardless of clicks
- Wasted spend confirmed for negation: **$956** (6.7% of analyzed spend)
- Additional $259 held pending your answer to Q1 (CaseHawk) — not counted above
- $14,200/month non-brand puts this account above the $10k/month line → recommend **weekly** cadence going forward, not this 30-day one-off

6.7% confirmed waste is low for a *first-ever* pass (your typical first cleanup runs 10–15%). That's a good sign the account isn't badly managed, but Google only shows ~40% of actual search terms — real waste may be sitting in the hidden 60%. Worth a token-mining pass (see Next steps) before concluding this account is clean.

## 2. Additions — apply now

| Term | Match type | Level | Evidence | Category | Variants to add |
|---|---|---|---|---|---|
| legal software jobs | Phrase | Account | 34 clicks, $238, 0 conv (0 last 90d) | Job seeker | legal software job, legal software careers, legal software hiring, legal case management jobs |
| free legal case template | Phrase | Shared list "DIY-free" | 26 clicks, $182, 0 conv (0 last 90d) | DIY/free | free legal case templates, free case management template, legal case template free, free legal case management template |
| what is case management software | Phrase | Shared list "informational" | 18 clicks, $126, 0 conv (0 last 90d) | Informational | what's case management software, what is legal case management software, case management software meaning |
| law firm consulting services | Phrase | Campaign (the non-brand campaign it appeared in) | 9 clicks, $410, 0 conv (0 last 90d) — crosses the **cost** gate, not the click gate | Off-target service (not software intent) | law firm consulting service, legal consulting services, law firm consultancy services |

Job-seeker went to **account** level as a universal disqualifier — no non-brand campaign here should ever want it. The two recurring themes (DIY/free, informational) went to **shared lists** so every future campaign inherits them automatically. "Law firm consulting services" stayed at **campaign** level: it's a single non-recurring term, no evidence yet it's an account-wide pattern — if it resurfaces in another campaign next pass, promote it to account level.

Reminder: Google Ads pre-selects **exact** match when you add from the search terms UI. Switch each of these to phrase before saving, or the block does almost nothing.

## 3. Do-not-negate

- **legal case management pricing** — 11 clicks, $77, 0 conversions this window, but **4 conversions in the last 90 days**. Fails the overblocking review — this term converts, it just didn't convert in this 30-day slice. Leave it running.

## 4. Held pending your confirmation (strategy calls, not automatic junk)

- **casehawk pricing** — 16 clicks, $112, 0 conv both windows. Competitor terms are never auto-negated — some accounts bid them deliberately for conquesting.
  - If unintentional → negate as **phrase, account level**; add variants: casehawk cost, casehawk demo, casehawk vs lexon.
  - If deliberate → keep it and treat the $112 as a CPA problem, not a targeting problem (better landing page/ad copy calling out your differentiation vs. CaseHawk).
- **best legal software** — 21 clicks, $147, 0 conv both windows. "Best/vs/comparison" queries are often early-funnel research, not junk. Zero conversions in both windows is a mild signal it's not working, but one pass isn't enough — check assisted-conversion/view-through data if you have it before negating. Recommend holding to watchlist rather than cutting on this pass.

## 5. Watchlist

- **legal case tracker excel** — 8 clicks, $56, 0 conv (0 last 90d). Below both gates (needs 2 more clicks to trip the click gate; cost is nowhere near the $375 cost gate). Likely DIY intent once it has enough data — recheck next pass.

## 6. Next review

Weekly cadence, 14-day lookback — **next pass by 2026-09-19**. This account's non-brand spend (~$14k/30 days) clears the $10k/month bar the skill uses to recommend weekly over monthly/bi-weekly passes.

## Next steps beyond this pass

- **Conflict check**: before applying, run these four confirmed terms against your active keyword list — none of them should overlap (they're all longer/different phrases than a plausible "case management software" core keyword), but verify in-account since I don't have your keyword list.
- **N-gram/token mining**: ~40% of search term spend is hidden from the report since September 2020. A quick tokenizer pass (or manual spreadsheet pivot if you can't script it) over the visible terms would surface junk tokens the report itself doesn't show as full queries — worth doing given how low this pass's confirmed waste came in.
- **Quarterly conflict sweep**: schedule one ~90 days out to catch any negative silently zeroing an active keyword, and to review whether the account-level job-seeker negative is over-blocking anything.