# LinkedIn Thought Leader Ads — Measurement Framework

## 1. Flag the benchmark before locking anything in

The 2.68% vs 0.42% comparison is an agency deck number — treat it as directional, not a target-setting input, for three reasons:

- **Different click definitions.** LinkedIn's default CTR counts all clicks (reactions, comments, shares, profile visits, "see more"), not landing-page clicks. Thought Leader Ads (TLAs) run as social posts — a big share of that CTR is likely on-platform engagement, not people arriving at our landing page.
- **Selection bias.** Case-study decks show winning accounts, not typical ones. We don't know the industry, offer, audience size, or which exec's personal brand drove it.
- **Different objective.** If the benchmark campaign was optimized for engagement rather than website conversions, LinkedIn's algorithm itself inflates CTR at the expense of off-platform clicks.

Action: ask the agency for the **landing-page-click CTR** specifically, and the CPC, from that same case study before treating 2.68% as a reference point at all.

## 2. Replace the single-metric gate with a primary + guardrail structure

**Primary success metric: Cost per Landing-Page Click (CPLPC), not CTR.**
This is the one number directly comparable to our existing $5.80 baseline on the same audience — it's the only apples-to-apples test we have.

- Target: CPLPC materially below $5.80 (propose the VP set the exact bar — e.g. 20–30% cheaper — since "beat the incumbent channel" is the actual business question).

**Guardrail metrics** (must hold even if CPLPC target is hit):

- **Landing-page CTR** (clicks to LP ÷ impressions) — track separately from total engagement CTR. Use this as the "beat 2%" metric if the VP wants to keep it, but define it explicitly as LP CTR in the campaign doc so it can't drift to include likes/comments later.
- **LP conversion rate** vs brand campaign baseline — a cheap, high-CTR click that doesn't convert is worse than a $5.80 click that does.
- **Lead quality** (MQL rate or ICP-fit rate) from TLA traffic vs brand campaign traffic — thought leader content can attract engagement-driven followers rather than buyers.

## 3. Make the test fair before measuring it

- **Same audience** as the brand campaigns being used as the $5.80 baseline — no loosening targeting to inflate CTR.
- **Same landing page and offer** — isolates the ad format, not the offer.
- **Fix which employees post** and keep it constant for the test window — TLA performance is highly sender-dependent (existing follower count, posting cadence), so results won't isolate "format" if the roster changes mid-test.
- **Minimum sample size before judging.** Set a floor (e.g., a minimum impression count needed to produce a stable CTR estimate) so week 4 isn't a decision made on a handful of clicks. Ask the agency or calculate this from expected weekly impression volume before the test starts.

## 4. Timeline and decision gates

- **Week 1–2: monitoring only.** Report CPLPC, LP CTR, spend pacing. No go/no-go decision — data volume too thin.
- **Week 3: checkpoint.** Directional read, flag if sample size is too low to trust week 4's verdict; extend the window if so rather than force a call.
- **Week 4: decision**, evaluated on all three:
  1. CPLPC below the agreed threshold vs $5.80.
  2. LP CTR above 2% (if kept as the stated bar).
  3. LP conversion rate and lead quality within an agreed tolerance of brand campaign baseline (e.g., no more than X% below).

**Scale only if all three hold.** Hitting the CTR number alone while CPLPC or lead quality misses is not a pass — it means we bought cheap engagement, not efficient demand gen.

## 5. What to put in the campaign doc verbatim

- Primary metric: CPLPC, target vs $5.80 baseline.
- Secondary gate: LP CTR ≥ 2% (explicitly defined as landing-page clicks ÷ impressions, not total engagement).
- Guardrail: LP conversion rate and lead quality within [X]% of brand campaign baseline.
- Test controls: fixed audience, fixed offer/LP, fixed poster roster for the 4-week window.
- Minimum sample size to trust the week-4 read, set before launch.
- Decision rule: scale only if all three metrics clear their bar; if CTR clears but CPLPC or quality doesn't, treat as inconclusive and extend rather than scale.