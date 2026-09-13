# Spend Health Check — Meridian Straps, Meta channel

## Headline

- **Meta (paid CAC): Watch** — rests on rung 1 (break-even). Meta CAC is still under Meridian's break-even allowable CAC, so this is not "unhealthy" by arithmetic. But the safety margin has collapsed by ~70% in two months, and the read rests on an unconfirmed CAC variant. **The CAC jump alone does not confirm saturation, and it does not support an immediate 30% reallocation.**

## Definitions record

Model: B2C ecommerce. Window: last 2 months, **two data points only** ($38 → $46) — not the 4-8 period trailing history this check normally runs on. Ecommerce conversions settle within days, so lag isn't the issue here — granularity is. Spend lines: assumed to be Meta ad spend only, platform-reported (not confirmed whether it's reconciled against order-system data or includes agency/creative costs). New-customer definition: not specified — unclear whether Meta's counted conversions exclude repeat buyers. Revenue basis: AOV $95 and contribution margin 52% taken as given; source not specified. Contribution margin: 52% — this is the one input that makes rung 1 computable, and it's solid enough to anchor the verdict.

What this gap deletes from the run: the mix-shift check (needs a real period series), fully-loaded CAC (no cost breakdown given), and reconciliation against order-system CAC. What to promote next period: pull weekly or monthly Meta CAC for the last 8-12 weeks plus order-system-confirmed new-customer counts for the same window — that turns rung 2 from two dots into an actual trend.

## Metric table

| Metric                   | Variant                                | Value                         | Window        | Source                     |
| ------------------------ | -------------------------------------- | ----------------------------- | ------------- | -------------------------- |
| Meta CAC (start)         | paid, platform-reported (assumed)      | $38                           | ~2 months ago | Meta Ads Manager (assumed) |
| Meta CAC (current)       | paid, platform-reported (assumed)      | $46                           | current       | Meta Ads Manager (assumed) |
| CAC change               | —                                      | +$8 / +21%                    | 2 months      | derived                    |
| Break-even allowable CAC | AOV × contribution margin = $95 × 0.52 | $49.40                        | —             | Meridian's own AOV/margin  |
| Break-even ROAS/MER      | 1 ÷ 0.52                               | 1.92x                         | —             | derived                    |
| Headroom (start)         | break-even − CAC                       | $11.40 (23% below break-even) | ~2 months ago | derived                    |
| Headroom (current)       | break-even − CAC                       | $3.40 (6.9% below break-even) | current       | derived                    |
| Headroom erosion         | —                                      | −70%                          | 2 months      | derived                    |
| Implied first-order ROAS | AOV ÷ CAC                              | 2.07x                         | current       | derived                    |

## Comparison ladder

1. **Break-even: $49.40 allowable CAC.** Current Meta CAC of $46 sits _under_ it — Meta is still profitable on a first-order basis, before counting any repeat-purchase revenue. Gap: $3.40 (6.9%).
2. **Own history:** only two points, $38 → $46. Direction is unambiguous (worse), but this isn't the 4-8 period read the check is built on — it's one measured jump, not yet a confirmed sustained trend, and no mix-shift check is possible without a real series.
3. **External:** Meta paid-social ROAS median runs 2.2–2.8x (Varos/Billo 2025-2026, platform-instrumented campaign samples). Meridian's implied 2.07x first-order ROAS sits just under that band. Context only — it does not set the verdict, and it isn't the same variant as a fully blended figure.

## Verdict and evidence gate

Gate: variant established — _partially_ (assumed paid/platform-reported Meta CAC, unconfirmed) · margin known — yes (52%) · window ≥ lag — yes · channels complete — n/a (single channel evaluated).

**Verdict: Watch.** Rung 1 clears, so this isn't "unhealthy." But the margin of safety fell ~70% in two months, and the read leans on an unverified CAC definition. Watch means "re-examine next period with a named question" — not "act," and specifically not "immediately move 30% of budget."

**Caveats that could flip this:**

- If $38→$46 is Meta's own attributed CAC (not reconciled to the order system), the real economic CAC is likely _higher_, not lower — platforms are documented to over-count attributed conversions (RCT evidence puts true lift overstatement at roughly 7–9x; audits show Meta and Google jointly claiming 150–200% of real revenue). Reconcile before trusting $46 at all.
- If any "new customers" Meta is crediting are actually repeat buyers, real CAC is worse still.
- 52% margin and $95 AOV are taken at face value; if either is stale or blended across SKUs with different economics, the $49.40 break-even moves.

## Handoffs

- Whether to test TikTok/Pinterest is a **marginal-CAC / reallocation decision**, not a health-check outcome — that's `mbfinotti/advertising-skills@ad-spend-allocation`. The relevant rule (Demand Curve): a rising CAC is not automatically a reason to leave a channel — test a new one once the _current_ channel's marginal CAC exceeds what the next channel could realistically deliver. Nobody has that number for TikTok or Pinterest yet; "diversify" right now is a guess dressed as a decision.
- Reconciling Meta's platform-reported CAC against order-system truth (the biggest caveat above) is `mbfinotti/advertising-skills@ad-attribution-gap` — do this _before_ any allocation decision, not after.
- If next period's CAC crosses $49.40, or the erosion trend holds for two more measured periods, escalate to `mbfinotti/advertising-skills@ad-account-diagnostic` to find the _why_ before touching budget.
- Putting a numeric ceiling/kill-switch on this going forward (so "watch" has a hard trigger next time) is `mbfinotti/advertising-skills@ad-spend-guardrails`.

---

**Direct answer:** No. A 20% CAC rise, by itself, does not confirm Meta is saturated or that diversification is warranted. By the numbers you gave, Meta CAC ($46) is still below Meridian's own break-even allowable CAC ($49.40 = $95 AOV × 52% margin) — the channel is still profitable on a first-order basis. What actually changed is the *margin of safety*: it shrank from $11.40 to $3.40, a 70% erosion, which is the real signal — not the raw CAC number. Before moving 30% of budget: (1) confirm whether $38/$46 are Meta's own attributed numbers or reconciled against your order system, since platform attribution is known to overstate conversions; (2) get more than two data points — a weekly series for the last 8-12 weeks — to see if this is a genuine trend or one bad stretch; (3) if you do want to test TikTok/Pinterest, size the move against evidence that Meta's _marginal_ CAC (cost of the next incremental dollar) is worse than what those channels could plausibly deliver, not against the fact that CAC moved. Right now "team consensus" is reacting to a headline number with a thin safety margin, not to confirmed saturation.
