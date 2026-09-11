# Spend Health Check — Tessellate Prints (target-setting question)

## Headline

- **ROAS/MER target: insufficient evidence for a full health check** (no current spend, revenue, or trailing-history numbers were given) — but the one number this skill *can* compute from what you gave me is solid: **break-even ROAS/MER = 1.82x**, from your 55% contribution margin. That's the floor, not the target. Everything above it is a policy call — see Handoffs.

## Definitions record

Model: B2C/ecommerce · Contribution margin: **55%** (post-COGS, shipping, payment fees — you didn't say if it nets fulfillment/returns too, worth confirming) · Window / spend / revenue / history: **not provided** · Variant of "ROAS" each source used: **not confirmed** (agency and podcast didn't specify; blog's figure below is identifiable).

I'm answering the target-setting question with what's computable (rung 1) rather than blocking, but a real "are we healthy" verdict needs your actual ROAS/MER, spend split, and 4-8 trailing periods.

## Metric table

| Metric | Variant | Value | Window | Source |
|---|---|---|---|---|
| Contribution-margin rate | CM after COGS, shipping, payment fees | 55% | — | you |
| Break-even ROAS (= break-even MER) | 1 ÷ margin | **1.82x** | — | derived from your own margin |
| Profit per ad $ at 1.82x | — | $0.00 | — | derived |
| Profit per ad $ at 2.04x | — | $0.12 | — | derived |
| Profit per ad $ at 4x | — | $1.20 | — | derived |
| Profit per ad $ at 5x | — | $1.75 | — | derived |
| Profit per ad $ at 8x | — | $3.40 | — | derived |

## Comparison ladder

1. **Break-even — 1.82x.** Non-negotiable. Below it you lose money by arithmetic regardless of what any benchmark says. Note this is *low* only because your margin is unusually good — the same math at a 25% margin gives break-even 4.0x, which is exactly where the "4x" folk number below actually comes from.
2. **Own trailing history — not available.** Direction and volatility of your last 4-8 periods matter more than any external level. This is the rung you're missing and the one I'd get before locking a number.
3. **External, with provenance:**
   - Median ecommerce ROAS **2.04** — Triple Whale 2025, 18,000+ brands, platform-instrumented, measures **blended ROAS** (revenue ÷ paid spend). This is a real, well-sourced figure — but at your margin, 2.04x leaves only **$0.12 profit per ad dollar**. "Above median" is not the same as "healthy for you"; the blog's "anything above that is fine" is the exact benchmark-only failure mode this method warns against.
   - **4x minimum** — no traceable author; per the skill's folklore record, this is just break-even at a 25% margin, retroactively turned into a rule of thumb. At your 55% margin it's not a "minimum," it's a very comfortable target ($1.20 profit/$1).
   - **MER > 4, rising to 5-8x at scale** — Taylor Holiday / Common Thread Collective, a stated heuristic, never measured across a sample. Directionally reasonable as a *stretch* range once you have room to be picky about spend, but it's an opinion, not evidence, and it wasn't calibrated to your margin either.

## Verdict and evidence gate

Gate: variant established — no (three different unlabelled "ROAS" claims) · margin known — yes (55%) · current performance / history — no.
**Verdict: insufficient evidence for a health verdict on current spend.** For the specific question asked ("what should we aim for"), the defensible part is the break-even floor: **1.82x**. Fixing the actual target above that floor is a policy decision, not an arithmetic one — see Handoffs.

## Folklore appendix

| Quoted rule | Origin | Against Tessellate's own break-even |
|---|---|---|
| Agency: 4x minimum | No traceable author, often misattributed to Nielsen; = break-even at 25% margin | You're at 1.82x break-even — 4x is ~2.2x your floor, i.e. a healthy buffer, not a bare minimum |
| Podcast: MER > 4, 5-8x at scale | Taylor Holiday (CTC), stated heuristic, never measured | Same buffer logic; "5-8x at scale" describes CTC's client experience, not your economics |
| Blog: median ~2.04, anything above is fine | Triple Whale 2025, real data — but blended ROAS, and "fine" ignores your margin entirely | 2.04x is barely above your floor: ~$0.12 profit per ad dollar. Technically above break-even, thin in practice |

## The actual answer

Ignore all three as targets — they're either unattributed folklore or a real benchmark misapplied to your specific margin. Your own break-even is **1.82x**, well below what all three sources assumed (they're implicitly reasoning from thinner-margin businesses). That means:

- **Never operate at or below 1.82x** — that's arithmetic, not opinion.
- A reasonable **working target sits meaningfully above that floor** — something like **3-4x blended ROAS / MER** gives you $0.65-$1.20 profit per ad dollar, real headroom for seasonality and CAC volatility, and doesn't require hitting the agency's or podcast's numbers to be genuinely profitable. That's a recommendation, not a computed answer — the specific number, and how much buffer above break-even you want, is a guardrail/policy decision (`mbfinotti/advertising-skills@ad-spend-guardrails`), not something this skill can derive from margin alone.
- Before locking any number: confirm which ROAS variant you'll actually track (blended vs MER vs POAS — they're not interchangeable), and pull 4-8 trailing periods so the target can be checked against your own trend, not just floated in the abstract.

## Handoffs

- Turning "aim above 1.82x, with buffer" into an actual target/floor/kill-switch number → `mbfinotti/advertising-skills@ad-spend-guardrails`
- Once you have current spend/revenue/history, a real healthy/watch/unhealthy verdict → re-run this skill (`cac-roas-benchmark`) with that data
- If you later find spend efficient but growth still weak, budget reallocation across channels → `mbfinotti/advertising-skills@ad-spend-allocation`