# Vantail — 5-Video Hook Test, Sep 2026

## Two corrections before this locks

**1. Hook rate can't be the deciding metric — it can only be the gate.**
A $1.47M multi-account analysis found no statistically significant correlation between hook (thumbstop) rate and revenue. A video can hold a great 3-second view rate and lose people before the CTA — that shows up as a fast, confident scale call on a creative that doesn't actually sell. Hook rate screens out obvious losers cheaply; it doesn't crown a winner. The scale call has to sit on cost per purchase.

**2. A flat 30% bar can't be applied across Reels and Feed.**
Reels is a full-screen, sound-on, thumb-stopping environment; Feed isn't — 3-second view rate runs structurally higher in Reels regardless of creative quality. Ranking all five videos on one shared hook-rate number would just crown "whichever video happened to run in Reels." Published "good" hook-rate bands also conflict 18–40% across vendors, so 30% isn't a stable external bar either way. Fix: compare hook rate only within its own placement cohort (the 2 Reels videos against each other, the 3 Feed videos against each other), and use 30% only as a rough interim sanity floor until you have your own trailing median — not as the number that decides scale.

Net effect: hook rate still does real work here — it's your fastest, cheapest read, live by day 3 — it just kills obvious duds early instead of picking the winner. The winner is picked on cost per purchase, which your own budget comfortably supports (see math below), so "purchases are slow" is actually the argument *for* this structure, not against it: it's exactly why the plan pre-registers a Directional (ranked, not significance-tested) read on CPA rather than pretending a hook-rate spike is a proven winner.

**Assumptions made to ship this now** (flag if wrong, plan adjusts):
- Platform = Meta (Instagram/Facebook), Reels + Feed placements, Purchase conversion objective — "Reels" is Meta's term, adjust if this is actually TikTok.
- No current champion/control creative was named — this is a 5-way bake-off among the new videos only. If a champion is running, add it as a 6th concurrent control cell; don't compare to its historical numbers.
- Baseline purchase rate, CPC/CPM, and monthly account purchase volume weren't given — the CPA math below runs off budget ÷ $28 target CPA only, so it's a volume/spend-threshold read, not a two-proportion significance calc. That's the direct cause of the Directional verdict.
- Each video is its own single-asset cell (not 3–6 variants per concept) — a bad edit or a weak thumbnail on one video reads as "concept lost," not "asset lost." Worth knowing before killing anything.

## Feasibility math

- 5 cells, $400/day each = $2,000/day, $14,000/week.
- Stable-delivery floor per cell ≈ target CPA × 50 ÷ 7 = $28 × 50 ÷ 7 ≈ **$200/day**. $400/day clears it 2×.
- Projected purchases/cell at $28 target CPA: $400 ÷ 28 ≈ 14.3/day ≈ **100/week/cell**.
- Over a 21-day window: ≈ 300 purchases/cell, ≈ 1,500 total across the test — healthy for a ranked/Directional read, not enough (without a known baseline rate) to promise a significance-tested winner.
- Gate metric (impressions) clears its own volume within days regardless — that's why it's the first available signal.
- 5-way ranking with no control caveat: with 5 cells compared and no correction applied, some cell wins by chance even under a true tie. Require a clear relative CPA gap (not a marginal one) before calling it, per the pre-registered scale rule below.

## CREATIVE TEST PLAN — Vantail 5-video hook test, 2026-09-14

```
decision    : the video with the best cost-per-purchase ranking, among videos
              that clear their placement's hook-rate gate, gets the scale budget
hypothesis  : because purchase volume is thin, no single video will reach a
              significance-tested CPA winner in one test window; ranking by
              cost per purchase (gated by 3-sec view rate per placement cohort)
              will surface a clear leader by day 21, or resolve to no scale
isolation   : bundled - unlearnable at element level (5 distinct finished
              videos, no shared single-variable structure; hard near-term
              launch date and no capacity to cut single-element variants both
              delete strict isolation from the menu)
structure   : 5 test cells, manual fixed-budget, $400/day each; Advantage+
              Placements off - Reels-cohort cells pinned to Reels, Feed-cohort
              cells pinned to Feed; Advantage+ Creative / dynamic creative off
metrics     : gate = 3-sec video view rate (3-sec plays / impressions), read
              only within its own placement cohort (Reels vs Reels, Feed vs
              Feed), at >=2,000 impressions/asset; 30% used only as an interim
              sanity floor until account trailing median exists - never as
              the scale bar
              primary = cost per purchase (decision metric), Directional read
              (baseline purchase rate unknown - ranked, not significance-tested)
              guardrails = frequency (<=2.5-3), CPM vs account baseline (+/-20%),
              add-to-cart rate vs account median (early proxy while purchases
              accumulate), refund/return rate post-scale
cells       : C01_PLC-reels_HOOK-<fill>_FMT-video_V01 | $400/day | 1 asset
              C02_PLC-reels_HOOK-<fill>_FMT-video_V01 | $400/day | 1 asset
              C03_PLC-feed_HOOK-<fill>_FMT-video_V01  | $400/day | 1 asset
              C04_PLC-feed_HOOK-<fill>_FMT-video_V01  | $400/day | 1 asset
              C05_PLC-feed_HOOK-<fill>_FMT-video_V01  | $400/day | 1 asset
              each cell: stable-delivery floor $200/day -> clears at $400/day
              projected ~100 purchases/wk/cell at $28 target CPA
              required for Powered CPA verdict: not computable - baseline
              purchase rate unknown -> VERDICT: Directional read on CPA
              gate (3-sec view rate) clears volume within days -> reported,
              never treated as a Powered significance claim either
              kill: asset at $56 spend (2x CPA) with zero purchases;
              cell killed at day 5-7 if clearly worst in its placement
              cohort on both gate and CPA
              scale: leading cell gets +50-100% budget, staged 2-3 times;
              first scale step treated as its own read (regression to mean)
schedule    : launch Mon 2026-09-14 | gate screen from day 3 (2026-09-17),
              once >=2,000 impressions/asset | no CPA judgment before day 14
              (2026-09-28) | hard stop day 21 (2026-10-05) or 300
              purchases/cell, whichever first | inconclusive -> no auto-scale,
              re-open with next-best-ranked video for one more window
naming      : C0#_PLC-<reels|feed>_HOOK-<type>_FMT-video_V0#
              (fill HOOK per asset's actual hook style - question, pattern
              interrupt, UGC, etc. - before launch, for roll-up reporting)
caveats     : manual cells still share auctions - cost inflation possible;
              even a pinned-placement read is a divergent-delivery-confounded
              relative screen, not causal proof; gate compared like-for-like
              by placement only, never Reels vs Feed head-to-head; no
              concurrent champion in this test - if one exists, add it as a
              6th control cell rather than comparing to its historical numbers
```

## Success criteria, stated plainly for whoever runs this

- **Kill an asset**: $56 spent (2× the $28 CPA target), zero purchases.
- **Kill a cell**: day 5–7, ranked worst in its placement cohort on both gate and CPA, no signs of recovering.
- **Gate pass**: 3-sec view rate at or above its own placement cohort's trailing median (use 30% only if no median exists yet, and only to catch an obviously weak hook — not to pick a winner).
- **Scale**: at hard stop (day 21 or 300 purchases/cell), the cell with the clearly best cost-per-purchase among gate-passing cells gets +50–100% budget, staged in 2–3 steps, each step re-read before the next.
- **No winner**: keep current spend split, don't force a scale call on a marginal CPA gap — rotate in the next-ranked video for one more window instead.
- Reported as: "video ranks best on cost per purchase among hook-gated survivors" — never as "won at 95% confidence," since that claim isn't earned here.