## Search terms audit — Lexon Legal Software (non-brand, 30-day window)

**Rule used**: cut on intent mismatch, not on "0 conversions" alone. At $7 avg CPC and $250 target CPA, one full CPA-equivalent ≈ 36 clicks. None of these terms have burned a full CPA except one — so spend-based statistical proof is weak for most; the call has to come from query intent.

### ❌ Exclude now — add as negative keywords

| Term | Match type to add | Why |
|---|---|---|
| `law firm consulting services` | Exact, campaign-level | $410 spend = **1.6× target CPA**, 0 conv this window *and* last 90 days. $45.6 CPC vs $7 account avg — check which broad-match keyword is pulling this in, it's leaking budget disproportionately. Highest priority cut. |
| `legal software jobs` | Phrase | Job-seeker intent, not buyer intent. 0 conv in 90 days too — no ambiguity. |
| `free legal case template` | Phrase | Wants a free static template, not paid case management software. |
| `legal case tracker excel` | Phrase | DIY/spreadsheet intent — actively avoiding software purchase. |

Also add a small negative list (phrase match, not single broad words — to avoid blocking things like "free demo" or "excel data migration"): `"legal software jobs"`, `"case template"`, `"tracker excel"`, `"consulting services"`.

Recovers **~$886/mo** (6.2% of the $14,200 analyzed spend) immediately.

### ⚠️ Do NOT exclude

- **`legal case management pricing`** — 0 conv this window but **4 conversions in the last 90 days**. This is a textbook false-positive trap: one flat 30-day window doesn't erase a proven converter. Killing it on this report alone would be the single costliest mistake in this list. Keep, and if anything invest here — check landing page/ad copy for this term specifically since it's clearly bottom-funnel.

### 🟠 Borderline — hold, don't cut yet

- **`casehawk pricing`** ($112, 16 clicks) — competitor-conquesting query. Whoever searches this is actively comparing vendors and is in-market; B2B case management software has a long sales cycle, so 0 conversions in 30 days on a competitor term is expected, not damning. Spend is also under half the target CPA — not enough data to judge. Recommend: don't negative it, instead build a dedicated "vs CaseHawk" ad group/landing page to convert this intent on purpose. Revisit with 60–90 days of data if it stays at zero.
- **`what is case management software`** ($126, 0/0) — informational, top-of-funnel query. Spend is under the CPA threshold so it hasn't proven itself a waste yet, but the intent ("what is") signals research, not purchase-readiness. Lower priority than the four above; if budget is tight, cut it as an exact-match negative — if not, leave it and revisit next cycle.
- **`best legal software`** ($147, 21 clicks, 0/0) — generic comparison query, could include people evaluating Lexon among others. Under one CPA-equivalent in spend. Don't cut on this single window; re-evaluate after another 30 days combined data.

### Implementation notes

1. Add the 4 confirmed negatives as a **shared negative keyword list** applied across all non-brand campaigns (not just one ad group) — these are recurring intent patterns, not one-off noise.
2. Use phrase/exact match for negatives, not broad single words (`free`, `excel`, `jobs`) — broad negatives here risk silently blocking legitimate queries like "free trial" or "Excel data import."
3. Re-pull the search terms report in 30 days for the two "borderline" terms with combined 60-day data before deciding.
4. Check the search terms report specifically filtered on `law firm consulting services` to find the triggering keyword/match type — a $45 CPC on a $7-avg account usually means a broad-match keyword is too loose.