# Ferrostat — Q4 Paid Spend Allocation

**Process note:** I did not run the full interview (single-pass request). I'm proceeding on directional proxies only — the numbers you gave support that rung — but I'm flagging every input I don't have. Treat this plan as **provisional** until those gaps close (see Open Questions).

---

## Gates

| Gate | Status | Detail |
|---|---|---|
| Affordability (payback) | ⚠️ Partial | Break-even CPL = ACV × lead-to-close = $32,000 × 11% = **$3,520**. No current CPL by channel was given, so I can't confirm any line clears it. Get this before next cycle. |
| Measurement maturity | ❌ Not scored | Score the 5 areas (blended dashboard, per-channel dashboard, conversion tracking, web analytics, attribution) before the next resplit. Until then, every estimate below stays at proxy grade. |
| Funding floor | ✅ Clears | LinkedIn at $21.6K/quarter = $7.2K/month, above the $3–5K B2B-network floor. Search at $44K/quarter clears the ~$50/day automated-search floor easily. |
| Data basis | ✅/⚠️ Mixed | Pipeline-share and closed-won figures read as CRM-level (business outcomes) — usable. LinkedIn reach/penetration and search impression-share are platform-reported, but both are used here only as *headroom* signals, not return claims, which is the sanctioned use. |

---

## Challenge the biggest proposed move, before accepting it

Your rationale for cutting LinkedIn — "zero deals sourced from LinkedIn last month" — is the wrong signal at a 105-day cycle. Deals closing *this* month were sourced 3–4 months ago, before this quarter's spend even ran. That number indicts LinkedIn spend from roughly a quarter ago, not the LinkedIn budget you're deciding on now. Judging a 105-day-cycle channel on last month's closed-won is a named failure mode, not a metric.

That said, **the conclusion still holds — on different evidence:**
- LinkedIn's 30-day penetration is 12,400 / 38,000 = **32.6%**, squarely in the *hold* band (25–35%). More budget there mostly re-reaches the same 38K people, not new ones. That's a real ceiling, independent of the deals report.
- Search + review sourced 63% of pipeline on 45% of budget — pipeline share exceeds budget share, the clearest under-funded signal in the account. Search additionally has 38% impression share lost to budget, meaning real, budget-responsive headroom (comparable to the 35–41% figures that triggered increases in similar accounts).

So: cut LinkedIn, grow search/review — but for penetration-ceiling and pipeline-share-gap reasons, not the last-month deal count. And the "6 deals from webinars and search last month" figure doesn't tell us the webinar/search split — I can't scale webinar on it. **I don't have LinkedIn's own pipeline/SQL share**, so I can't independently confirm how weak its current marginal contribution actually is — I'm relying on the penetration ceiling alone.

A 60% single-cycle cut is also 3x this framework's "never move 30%+ per line" default. I'm implementing it anyway as your explicit, approver-directed call — logging it as operator policy below, not as something the marginal evidence alone derives — and routing it through the governance tier that size of move requires.

---

## The Split

```
SPEND ALLOCATION — Q4, total $120,000 (fixed)
Approach          : Incremental reweighting (default rung) + one owner-directed override (LinkedIn)
Evidence rung     : Directional proxies only — no incrementality test or MMM in place
```

| Line | Current | Proposed | Δ |
|---|---|---|---|
| Search (demand capture) | $34,000 | **$44,000** | +$10,000 (+29%) |
| Review-site listings | $20,000 | **$25,000** | +$5,000 (+25%) |
| Webinar promotion | $12,000 | **$12,000** | flat |
| LinkedIn | $54,000 | **$21,600** | −$32,400 (−60%) |
| Contingency (defined use, below) | $0 | **$17,400** | new |
| **Total** | **$120,000** | **$120,000** | sums exact |

### Per-line change packets

**Search — $34,000 → $44,000**
- Rationale: pipeline share (63%, combined w/ review) > budget share (45%); 38% impression share lost to budget = quantified, budget-responsive headroom. Strongest evidence of any line, hence the largest single increase.
- Expected effect: cost per SQL holds flat-to-improving; lost impression share drops as spend absorbs it.
- Uncertainty: medium — proxy only, and the 63% pipeline figure isn't split between search and review individually.
- Owner: *(assumed)* Demand Gen lead — confirm.
- Rollback threshold: cost/SQL > 1.3x trailing baseline for 2 consecutive weeks after day 30.
- Verify: Day 45 (leading indicators), Day 90 (quarter close).

**Review-site listings — $20,000 → $25,000**
- Rationale: same pipeline-share signal as search; no channel-specific headroom proxy exists for this line (unlike search's impression share), so it gets a smaller step.
- Expected effect: cost per SQL holds; category floor still clears.
- Uncertainty: medium-high — no independent proxy beyond the combined pipeline figure.
- Owner: *(assumed)* Demand Gen lead — confirm.
- Rollback threshold: cost/SQL > 1.3x baseline.
- Verify: Day 45, Day 90.

**Webinar promotion — $12,000 (flat)**
- Rationale: appeared in last month's closed-won, but its share of that "6 deals from webinars and search" figure is unknown, and closed-won reflects spend from ~3 quarters back at this cycle length anyway. Not enough to scale up or down — held flat pending attribution fix.
- Expected effect: none targeted this cycle; this is a data-quality hold, not an efficiency call.
- Uncertainty: high — genuinely unmeasured.
- Owner: *(assumed)* Field/Campaigns lead — confirm.
- Rollback threshold: n/a (flat line).
- Verify: attribution split reported by Day 30, feeds next cycle's split.

**LinkedIn — $54,000 → $21,600**
- Rationale: 32.6% 30-day penetration = hold band, a real ceiling independent of the deals report; CEO-directed 60% cut, logged here as operator policy exceeding the standard 15–20% step guideline. Clears the funding floor at $7.2K/month.
- Expected effect: reach drops proportionally; whether pipeline drops proportionally is unknown — no LinkedIn-specific pipeline/SQL share was provided.
- Uncertainty: high, and the size of the move means a misread here is expensive — this is the line most in need of its own leading-indicator read, not the closed-won report.
- Owner: *(assumed)* Demand Gen lead — confirm.
- Rollback threshold: if Day-45 leading indicators show LinkedIn-sourced SQLs/pipeline were materially higher than assumed, revisit magnitude next cycle rather than mid-cycle reversal (105-day lag makes a mid-cycle reversal unreadable).
- Verify: Day 45 (pipeline created, once tracked distinctly), Day 90.

**Contingency — $17,400**
- Defined use (required — never an idle hold):
  1. **Day-45 top-up trigger**: if search/review leading indicators (cost/SQL, pipeline-created share) confirm the signal, release up to $10,000 more into search — the account's now-largest single bet.
  2. **Search incrementality test**: reserve ~$7,400 to commission a holdout/geo-lift test on search this quarter. It just became the biggest line in the portfolio on proxy evidence alone; that's exactly the trigger this framework uses to promote incrementality testing above its default rank, and it buys a reusable curve for the next resplit instead of re-guessing again.

---

## Constraints checked

- **Creative supply (search):** proven-ad inventory ≈ monthly budget ÷ $5,000 (folklore ratio, calibrate against your own history) → $44K/quarter ≈ $14.7K/month needs roughly 3 proven ad variants running. Confirm you have that inventory before the increase goes live, or phase it.
- **Audience/inventory:** none block the review-site or webinar lines at these levels.
- **Contract/policy:** none flagged — none were mentioned as in place.

## Revisit

- **Cadence:** quarterly resplit (matches the 105-day cycle); Day-45 leading-indicator check is a read, not a resplit.
- **Governance:** LinkedIn's −60% move is well above the 25% joint-signoff threshold this framework defaults to — route it through Finance alongside Marketing before execution, even though you're the requester.
- **Seasonal:** none flagged — none were mentioned.

## Open questions (name before this plan stops being provisional)

- Contribution margin / current CPL by channel — needed to actually clear the affordability gate, not just the B2B breakeven shortcut.
- LinkedIn's own pipeline/SQL share — right now its cut rests on the penetration ceiling alone, not a marginal-return read.
- Split of "6 deals from webinars and search" between the two channels.
- Measurement-maturity score (5 areas) — unscored, caps every number here at proxy grade.
- Confirmed line owners (assumed above, not stated).