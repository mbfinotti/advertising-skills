# Bidding Strategy Analysis — Cindercart App vs Web, and the PMax Question

## Q1: Which team is actually performing better?

**You can't tell from these two numbers as stated — they're not on the same scale, and even fixed, they're not the same kind of number.**

**Step 1 — fix the units.** Mobile UA tooling typically reports ROAS as a percentage where 100% = breakeven (revenue equals spend). Web/ecommerce platforms report ROAS as a multiplier where 1x = breakeven. Convert both to the same convention:

| Team            | Reported | Normalized |
| --------------- | -------- | ---------- |
| App (UA agency) | 160%     | 1.6x       |
| Web             | 4.2x     | 420%       |

Normalized honestly, web is still ahead — 4.2x vs 1.6x, not a 100x misread. So the web team isn't wrong that they're outperforming the app on a raw revenue-per-dollar basis. But "outperforming" isn't decided by the raw multiple — it's decided by each channel's own break-even return, which depends on contribution margin, and app and web economics are rarely the same shape:

- break_even_ROAS = 1 ÷ contribution margin rate
- 1.6x return implies the app only needs a ~63% margin to be at breakeven; most IAP/subscription apps run a much wider margin than that once App Store cut, COGS, and support are netted out — so 1.6x could sit comfortably above break-even.
- 4.2x on web implies web only needs a ~24% margin to be at breakeven — plausible for retail, but "4.2x is strong" is only true if web's actual margin is in that range. On thin-margin SKUs, 4.2x could be closer to break-even than it looks.

**What actually decides the winner: margin buffer, not raw ROAS.** Neither team has told you their contribution margin rate, so neither number can be judged yet. Pull both:

- App: net contribution per install/subscriber after store fees, refunds, and support cost.
- Web: contribution margin rate after COGS, shipping, payment fees, and returns.

Compute break-even return for each, then compare (normalized return − break-even) as the real head-to-head, not the headline number.

**Two more confounds before either number is trustworthy:**

1. **Measurement window mismatch.** App LTV/ROAS is usually measured at a fixed window (D7/D30/D90) while value keeps accruing after; an immature window structurally understates app ROAS relative to web, where a purchase is usually captured same-session. Ask the UA agency which window "160%" uses, and whether it's still climbing.
2. **Both numbers are platform-attributed, not incremental.** Neither figure has been through an incrementality test. A UA agency's install attribution and a web team's retargeting/branded-search attribution both tend to run rich — some of that "return" would have happened without the spend (organic installs the MMP still credits, branded search substituting for organic). Per the skill's own guidance: platform metrics can be healthy while a holdout shows near-zero lift. Until one geo/holdout test runs per channel, you're comparing two unverified numbers, not two performances.

**Bottom line:** normalized, web currently shows the higher return per dollar (4.2x vs 1.6x), and that's a fair correction to make to the agency's "160% is strong, app is fine" framing. But "web is winning" isn't confirmed until you have each channel's break-even return and at least a directional incrementality read — a 1.6x app channel on 70% margin can be healthier than a 4.2x web channel on 20% margin. Don't settle the team debate on the raw multiples; settle it on margin-adjusted, incrementality-checked buffer.

## Q2: Do you flip on Performance Max for most of the web budget?

**No — not as "just another campaign type," and not as a single cutover of most of the budget.** Your boss's framing is the one thing in this brief with a clean, direct answer.

PMax is a delegated bidding archetype, not a targeting option layered on top of your existing strategy. Turning it on **is** the bid-strategy decision — it hands the platform your optimization objective, targeting, creative selection, and placement jointly. There is no "flip it on and see" version of this that isn't also "hand over the wheel and see."

Before any budget moves, answer the three questions this decision actually turns on:

- **What signal does the platform get?** PMax bids on whatever conversion event and values you feed it. Given that web's own ROAS number isn't yet confirmed as incremental or margin-checked (see Q1), feeding an unverified/undifferentiated value signal into a fully automated bidder means PMax will optimize hard toward a number you don't yet trust.
- **What control does delegating give up?** Search-term visibility, placement-level attribution, and the ability to isolate what's actually driving results — all reduced. You'd be making this trade at the exact moment you're trying to prove out whether web is genuinely strong.
- **What would justify taking it back?** If you can't write this down before switching on, you don't have a policy, you have a hope.

**Sequencing that actually protects the budget:**

1. **Close the measurement gate first.** Confirm the web conversion event is the real business outcome and values are differentiated, net of refunds, and timely — same gate this skill requires before any value-based archetype. Don't hand PMax a value signal you haven't validated.
2. **Don't cut over — experiment.** Use the platform's own PMax experiment/simulation tooling to run PMax against a slice of budget alongside your current best-performing structure, with brand terms and any protected/manual campaigns excluded from the test. A split test reads the actual incremental effect; a hard cutover reads the campaign change and a full learning-period reset, confounded — you'd never know which one moved the number.
3. **Set guardrails before spend moves**: brand-term exclusion or protection, a budget cap on the test slice, and a named approver for scaling past it.
4. **Evaluate in conversion cycles, not a demo period** — one to two full cycles (click-to-conversion lag plus reporting delay) before reading the result at all.
5. **Only then consider "most of web budget."** Moving the majority of spend into a black-box archetype in one step, on a metric that hasn't cleared incrementality, is the single largest and least reversible move available here — it's the opposite of the smallest-reversible-change default. Scale into it only once the experiment shows real incremental lift over what you're already running, not a healthy blended in-platform ROAS (PMax's own reported ROAS will almost always look good, because it's now the one measuring its own homework).

**One line for your boss:** PMax isn't a campaign type you turn on, it's a decision to let Google run your bidding, targeting, and creative selection together — treat it with the same rigor as any other bid-strategy change, run it as a bounded experiment against a validated signal, and only scale it on measured incremental lift.

## What would sharpen this into a real policy

This is a business call, not a mechanical calculation — the following, unanswered, are the actual gate on locking in a recommendation:

- Contribution margin rate for app (post store-fee, post-refund) and for web (post-COGS, post-returns).
- The measurement window behind "160%" (D7/D30/D90) and whether it's still accruing.
- Whether either team has ever run a holdout/geo incrementality test — if not, that's worth doing before either number drives a budget decision.
- Who owns the PMax rollback call if the experiment underperforms, and what specific number triggers it.
