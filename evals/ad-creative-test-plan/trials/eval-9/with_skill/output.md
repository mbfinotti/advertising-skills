# Solent & Co — Creative Test Plan (Concept A vs. Concept B)

## Correcting the premise, up front

Two claims in your framing don't hold, and the board deck should not repeat them:

1. **"Deterministic assignment means no contamination."** Not proven. Braun & Schwartz (_Journal of Marketing_, 2025) show that even platform-native deterministic splits suffer **divergent delivery**: the ad algorithm still shows each cell a differently-optimized mix of users, which can confound the magnitude of a result — and even flip its sign. Deterministic assignment removes _audience overlap_. It does not remove _delivery bias_. Only a geo-holdout / incrementality design gets you actual causal proof, and that's a different (and much more expensive) test.
2. **"The result will be causal proof."** At $150/day this claim is not available regardless of structure — see the math below. The platform-native tool also runs a week-plus longer than manual cells and, per Meta's own guidance, frequently returns "no winner" at normal budgets. That's the wrong structure for a 12-day clock.

What you _can_ honestly tell the board: a pre-registered, bias-aware screening test with a named decision rule — which is a legitimate and common outcome, not a downgrade, as long as it's labeled correctly.

## Assumptions I'm flagging, not burying

I don't have full answers to the standard intake here, so I've made the calls below and flagged each. Confirm before launch:

- **Platform**: assumed Meta (most common for DTC eyewear paid social). Recompute stable-delivery floor and duration if it's TikTok or Google — different mechanics.
- **No existing champion cell**: assumed you're running Concept A vs. Concept B head-to-head, not against a running control. If a champion creative is live, add it as a third concurrent cell — this tightens every number below.
- **$32 CPA** treated as target/account CPA, used to size the stable-delivery floor.
- **Assets per concept**: assumed 3-4 variations per concept (skill default 3-6/cell). If you only have 1 creative per concept, say so — single-asset cells concentrate all risk in one execution.
- **Baseline purchase conversion rate / CPC**: not provided. Without it I cannot run the two-proportion significance formula in proper units — but it doesn't change the verdict below, because the stable-delivery floor fails first and independently of that math.
- **No regulated-claim issue assumed** (sunglasses/frames, not prescription-accuracy or vision-health claims). Flag me if either concept makes a vision-correction or health claim — that needs a substantiation check before launch.

## Feasibility check (the numbers that decide the structure)

**Stable-delivery floor** (Section 4.4): minimum daily budget per cell ≈ target CPA × 50 ÷ 7 = $32 × 50 ÷ 7 ≈ **$229/day/cell**.

Your budget: $150/day total ÷ 2 cells = **$75/day/cell** — about **33% of the floor**. Both cells are delivery-limited from day one; the optimization algorithm never gets enough purchase events to stabilize, so the numbers stay noisy regardless of how long you run it.

**Verdict on the purchase event: Not testable as designed** (Section 4.5) — this is a stable-delivery failure, not a sample-size failure, so it applies to _any_ structure, native split included.

**Fix applied** (Section 4, ranked levers — up-funnel > widen MDE > fewer cells > raise budget):

- _Raise budget to ~$460/day total_ would clear the floor but isn't stated as available — ask the CEO if the board would fund a temporary bump; if yes, this is the clean fix.
- _Move the read up-funnel_ (e.g., Add-to-Cart) would help, but I don't have your ATC volume/rate to confirm it clears the floor — pull that number before launch; if it's unverified, get it checked against `ad-conversion-tracking` first, since a test on a broken event measures nothing.
- Absent either, the only honest move is **widen the MDE and declare Directional** — i.e., stop trying to detect a small edge and only claim a result if the gap between concepts is large.

**What a real Powered/significant read would cost, for context**: per the sizing reference table, even a generous 10% baseline conversion rate detecting a large 50% relative lift needs ~700 sessions/cell; a more realistic 2-3% baseline needs 2,500-14,000+ sessions/cell. Lewis & Rao (2015) found informative ad experiments routinely need spend far beyond normal test budgets — this is that finding showing up in your numbers. Getting genuine statistical power here would run into four figures per day over 4-6 weeks, not $150/day over 12 days. That's a decision for the board to make with eyes open, not something to quietly promise now.

**Denney screening anchor** (adopted below): budget per test ≈ CPA × 50 = $32 × 50 = **$1,600**. At $150/day you reach ~$1,500 in 10 days — close enough to treat as met. That's why a 10-day screening window lands almost exactly on your board deadline.

## The pre-registered plan

```
CREATIVE TEST PLAN - Solent & Co eyewear, Concept A vs B, 2026-09-12
decision    : the concept with the better ranked cost-per-purchase (guardrails
              holding) gets next-quarter production budget; the other is
              retired or iterated depending on where it broke down
hypothesis  : because [YOUR creative rationale for A vs B - fill in],
              Concept [A/B] will [raise/lower] cost-per-purchase by ~[X]%
              vs Concept [other] for [target audience] by day 10
              (magnitude is a screening target, not a significance claim)
isolation   : bundled - unlearnable at element level (full concept, not a
              single element; the 12-day deadline rules out strict
              single-variable isolation - see Section 2)
structure   : 2 test cells, no separate control (no champion currently
              running - confirm); MANUAL fixed-budget cells, not the
              platform's native split test; automated creative-optimization
              (Advantage+ Creative / dynamic creative): off
              -- native split rejected: it runs 1+ week longer than this
                 deadline allows, is underpowered at this budget, and does
                 NOT remove divergent-delivery bias anyway (see above)
metrics     : gate = hook rate/CTR vs account trailing median, per placement,
              read only at >=1,000-2,000 impressions/asset - screens losers
              only, never crowns a winner
              primary = cost per purchase (decision metric)
              guardrails = frequency, CPM vs account baseline, return/refund
              rate (eyewear-specific - a concept overselling fit/style can
              spike returns), blended account CPA
cells       : C01_CONCEPT-A_HOOK-tbd_FMT-tbd_V01..0N | $75/day | 3-4 assets
              C02_CONCEPT-B_HOOK-tbd_FMT-tbd_V01..0N | $75/day | 3-4 assets
              stable-delivery floor: $229/day/cell - NOT MET at $75/day (33%)
              projected purchases: ~2.3/day/cell -> ~23/cell over 10 days
              (~47 total, vs Denney's 50-conversion screening anchor)
              VERDICT: Not testable as designed on purchase, as structured
                -> fix applied: widen MDE, declare DIRECTIONAL READ
                -> only a large relative CPA gap between concepts will be
                   visible; small/moderate differences will not resolve
              kill: asset at $64 spend (2x CPA) with zero purchases
              scale: winning concept +50-100% budget next quarter; treat
              the first scale step as its own read (regression to mean)
              iterate: concept that wins gate metric but loses CPA -> check
              landing page / offer before touching the creative again
schedule    : launch Mon 2026-09-14 | earliest evaluation day 3
              (2026-09-16, kill-only) | interim check day 7 (2026-09-20,
              may end a clearly dead cell early and reallocate) | hard stop
              day 10 (2026-09-23, 23:59) or $1,500 total spend, whichever
              first | board meeting 2026-09-24
              inconclusive -> do NOT scale either concept off this read;
              hold both at current spend, revisit with either more budget
              or 3-4 more weeks of trend data
naming      : C##_CONCEPT-<A|B>_HOOK-<type>_FMT-<format>_V##
caveats     : manual cells share the same auction/audience - some overlap
              and cost inflation expected, noted; divergent delivery means
              even this read is relative screening, not causal proof, and
              would remain so even under the native split test; ~50% of
              low-budget campaigns never stabilize - if either cell shows
              erratic delivery by day 5, that itself is diagnostic
decision-rule anchor: Dara Denney (named per Section 6) - budget-per-test
              anchor fits this timeline almost exactly; no standing
              best-ads benchmark library or weekly reviewer exists to
              justify Hott, and the hard board date rules out Faris'
              open-ended evergreen approach
```

## Board write-up

**One paragraph, if the CEO wants a single honest sentence to open with:**

> "We ran a pre-registered 10-day screening test between our two new creative concepts, spending $1,500 total. At this budget, the ad platform cannot produce a statistically significant winner — no test at this spend level can, and we said so before launch rather than after. What it _can_ produce, and did, is a directional ranking on cost-per-purchase, backed by a documented decision rule set before we saw any data, with return rate and frequency tracked as guardrails so we're not just chasing a cheap-but-risky metric."

**Slide bullets:**

- Test structure: 2 concepts, $75/day each, manual concurrent cells (chosen over the platform's native split — it would've taken longer and wasn't more valid at this budget; details in appendix).
- Result standard, declared before launch: **Directional read**, not statistical significance — this budget/timeline can't support the latter, and we're not going to claim what we can't back.
- Decision rule, pre-registered: kill at 2× CPA with zero purchases; concept with the better CPA (guardrails holding) gets next-quarter production budget.
- What it would take for a statistically airtight, causally clean result: roughly 4 figures/day over 4-6 weeks, or a dedicated incrementality/holdout study — a separate investment decision for the board, not something this test claims to deliver.
- Guardrail watch: return rate (fit/style overselling risk specific to eyewear), frequency, blended account CPA.

**If a board member pushes back with "isn't the platform's built-in A/B test the gold standard?"** — the honest answer, in one line: _"It removes audience overlap, but not delivery bias, and at our budget it would've missed the board date without buying us anything the manual test doesn't already give us — happy to walk through the math."_

## Before you launch — action items

1. Fill in the hypothesis bracket (what's actually different between Concept A and B, and why you expect a direction/magnitude).
2. Confirm platform (Meta assumed) and pull Add-to-Cart baseline rate/volume — may unlock a Powered up-funnel read.
3. Confirm no champion creative is currently running; if one is, tell me and I'll rebuild the cell matrix as 3-way.
4. Turn off Advantage+ Creative / dynamic creative inside both ad sets.
5. Confirm asset count per concept (3-4 assumed).
6. Ask whether a temporary budget bump to ~$460/day is fundable — it's the only lever that clears the stable-delivery floor outright.
