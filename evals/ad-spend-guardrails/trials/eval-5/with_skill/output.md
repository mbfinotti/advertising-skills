# Ad Spend Guardrails — Bramwell Software: assessment before formalizing

I read `ad-spend-guardrails/SKILL.md` and its worked examples (`references/worked-guardrail-policies.md`). Before I hand you a "formal" version of the current rule, I have to flag something: **what you have isn't a policy that's been quietly working — it's the textbook negative example the skill warns against.** Formalizing it as-is would put a board-ready seal on three problems, not one.

## Why "no breach in three quarters" isn't evidence it works

Zero breaches is not proof of a healthy ceiling — it's one of the two things a working policy should trigger review on, same as constant breaching. A ceiling that's never touched for three quarters running usually means one of:

- the $310 figure was set loose enough that it was never a real constraint (sandbagged), or
- spend never got close to the marginal cost where efficiency actually degrades, or
- the number was picked from a benchmark rather than derived from your margin, so it happens to sit well above where the real economics bind.

None of those are "it works." They're all reasons to re-derive the number from your contribution margin, not to canonize it.

## The governance problem is the one to fix first

The Head of Growth **sets** the $310 ceiling and **approves her own overages**. That's not a control, it's a preference with a dollar figure attached. Separation of duties is the entire point of a spend guardrail: whoever spends the budget cannot also be the one who raises the ceiling on it. Right now there is no threshold in this business that the spender doesn't also own — which is the single highest-value fix available, ahead of any number.

## What's missing to actually derive $310 (or replace it)

The skill is explicit: never state a threshold whose derivation can't be shown, and never fill a missing input with a plausible number. I don't have any of the following from you yet, so I can't produce real numbers — only the shape of the document:

1. Contribution margin per sale (and confidence: guess / finance-reviewed / per-SKU)
2. Price/ACV bands — one blended $310 ceiling likely doesn't fit every plan or deal size equally
3. Current CAC variant (paid / blended / fully-loaded / new-customer) — which one is the $310 actually measured against?
4. Payback target and its origin
5. Cash runway and monthly burn (the cash cap is a separate, absolute ceiling — efficient and affordable are different tests)
6. Sales-cycle length (sets the minimum window a guardrail may legally read)
7. Conversion-feed reliability / any incrementality evidence
8. Who else can pause spend, and who can chair a standing weekly review (this decides whether a tiered ladder is executable or whether a single floor is the honest choice)
9. Board deadline — you said "before the next board meeting," which is exactly the condition the skill says promotes the single break-even floor as the interim artifact, with a tiered ladder to follow once margin data and a reviewer are in place

## What I'd adjust, concretely

- **Split $310 into three numbers, not one.** Right now one figure is silently doing the job of break-even floor, target floor, and kill-switch — which is why a bad week and a real structural problem would get the same (non-)response. Once I have your margin, I can show the break-even CAC arithmetic next to $310 so the board can see whether $310 is comfortably above break-even, uncomfortably close, or already under it.
- **Move override authority off the Head of Growth.** Target-floor breaches can stay with her, time-boxed and logged. Anything at or above the hard floor needs a second signer — CFO or founder — who isn't spending the budget.
- **Add a counter-metric.** A CAC ceiling with no counter-metric is met most easily by shifting spend into retargeting/branded search, which just harvests demand that was already coming. New-customer share or SQL-to-closed-won (pick per motion) closes that gap for near-zero extra effort.
- **Add an evidence gate and a restart condition to the kill-switch**, if one doesn't already exist informally — a pause with no floor on duration and no written way back tends to cost more than the overspend it prevents, especially on algorithmic platforms.
- **Put a re-baselining date on it.** Quarterly, plus triggers (pricing change, margin change, tracking change). A ceiling that's never revisited is exactly how a sandbagged $310 survives unnoticed for three quarters.
- **Treat this zero-breach streak as a review trigger for the board meeting**, not a talking point *for* it — "we haven't breached it, so it works" is the line most likely to get challenged by a board member who's seen this pattern before.

## Next step

Answer the inputs above (a few lines is enough — margin and its confidence level matter most) and I'll draft the full policy in the skill's format — Inputs / Derivation / Layers / Guardrail set / Kill rules / Governance / Exemptions / Assumptions — with $310 replaced by a number I can actually show the arithmetic for, or confirmed if the arithmetic happens to land there. If the board deadline doesn't allow time to gather all of it, I can produce a **provisional single-floor version now**, clearly labeled provisional, with every missing input named as missing rather than guessed — that's still stronger than formalizing the current version, and it's honest about what it is.