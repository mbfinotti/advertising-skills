# Lanternway Outfitters — Q4 Retargeting/Prospecting Split

## Headline finding, before the split

**50/50 is not deliverable.** The retargeting pool physically caps spend far below that — and likely below where you already are. Walking through the math changes what "draft the new split" should mean here.

**Ceiling math** (retargeting spend is bounded by pool × frequency cap × CPM, not by ambition — this is the binding constraint, not a target to negotiate):

- 8,000 reachable people × 6 impressions/week cap = 48,000 impressions/week
- 48,000 / 1,000 × $16 CPM = **$768/week**
- × 4.33 weeks = **≈$3,300/month** ≈ **$10,000/quarter**
- Against the $48,000/month total budget, that ceiling is **~7% of spend** — not 50%, and not even today's 25%.

**Current retargeting spend is $12,000/month (25% of $48k) — already ~3.6x over that ceiling.** Back-solving: $12,000/month at $16 CPM buys 750,000 impressions/month, or ~93.75 per person/month against an 8,000-person pool — **~21-22 impressions/person/week**, not the stated 6. Either the frequency cap isn't actually being held on the platform today, or the pool/CPM inputs need re-verification. Pull the platform's actual frequency metric before anything else below.

## Why this matters more than the split itself

Your symptom — **11x platform ROAS on retargeting, flat blended revenue all year** — is the named failure mode for exactly this setup ("Cannibalisation: great platform ROAS, flat blended revenue → the fix is an incrementality test, not more budget"). An audience already running at ~3.6x its intended frequency is the classic way to manufacture a high last-touch ROAS: you're re-intercepting people who were converting anyway and the platform claims the credit.

Illustrative, not a claim about your account specifically: the best available RCT evidence (Gordon, Zettelmeyer et al. 2019, 15 large-scale experiments) found observational/platform-reported lift overstates true incremental lift by roughly 7-9.5x depending on funnel position. Apply even the low end to your 11x and the *true* incremental ROAS on retargeting could be sitting close to or below prospecting's 1.9x. **You cannot know which channel is actually better until you run the holdout below.** Giving the board a bigger number for retargeting before that test would be handing them a number you don't yet believe.

## The drafted split

| | Current | Naive "board" ask | **Recommended (ceiling-bound)** |
|---|---|---|---|
| Prospecting | $36,000 (75%) | $24,000 (50%) | **≈$44,700 (~93%)** |
| Retargeting | $12,000 (25%) | $24,000 (50%) | **≈$3,300 (~7%)** |

Quarterly: retargeting **≈$10,000/quarter**, prospecting **≈$134,000/quarter**.

This moves *less* into retargeting than today, not more — the opposite direction of the board's instinct, so it needs to be delivered as a finding, not a compromise. Framing for the room: the 25%→50% conversation was based on a ROAS number that hasn't been checked for incrementality; the pool math caps retargeting near 7% regardless of what that number turns out to be; the growth lever this quarter is fixing prospecting and proving what retargeting actually contributes, not moving the split.

Don't just pour the freed ~$8,700/month into prospecting as-is — a full year of flat blended revenue under the current prospecting structure suggests it's stale too. Route the freed budget toward new prospecting audience/creative tests (`ad-audience-targeting`, `ad-creative-fatigue`) rather than scaling the existing setup 1:1.

## Retargeting stage design, within the ~$3,300/month ceiling

**Assumptions flagged as provisional** — no lag-distribution export or tracked-event list was provided. Proxy used: general apparel e-commerce recency curve (sector-typical, same shape as the worked skincare example: ~80% of converters inside ~7 days, tail to ~30-45 days). Replace with Lanternway's own time-to-conversion export before locking window edges.

With only 8,000 total reachable people, splitting into 4-5 depth tiers risks under-floor stages (Meta/Google practical floor ≈1,000 each) once exclusions are applied. Collapsing to two stages is the right call at this size (Ben Heath's single-warm-pool position, applied via the collapse rule) until volume or CRM data justifies more granularity:

| Stage | Inclusion | Window (provisional) | Message intent / offer | Concepts |
|---|---|---|---|---|
| **S1 Hot** | Cart/checkout start, no purchase | 0-7 d | Reminder — exact item, no incentive | 3 |
| **S2 Warm** | Product view, no cart + aged S1 members | 0-30 d | Social proof → objection handling; no discount yet | 3 |

Discount/incentive rung: hold in reserve for a future "last-call" stage only once volume supports a 3rd tier — don't add it to S1/S2, and don't add it at all until it's confirmed the account has a discount policy to use (unconfirmed here).

## Exclusion map

- `RTG_HOT_0-7` excludes `EXCL_PURCH_<window>`.
- `RTG_WARM_0-30` excludes `RTG_HOT_0-7` and `EXCL_PURCH_<window>`.
- Converter-exclusion window: **proxy 180 days** (apparel repurchase cycle unconfirmed — verify against actual reorder data; 180 gives margin without choking prospecting reach the way Meta's 730-day purchase-audience ceiling now can if left unaudited).

## Cap sheet

- Meta/Google conversion objectives expose no hard frequency-cap field — this is a **cap-proxy**, not a hard limit.
- Target: 6/person/week (per your stated policy). **Verify actual delivered frequency first** — the spend math above implies it's running ~3x that.
- Intervene when, against a 7-day rolling baseline: CTR down 15-20%+, CPM up 10%+, or negative feedback rising.
- Review cadence: S1 every 2-3 days, S2 weekly.

## Measurement plan — do this before touching the split further

1. **Audit actual delivered frequency and effective CPM on retargeting this week.** This resolves whether the pool/frequency/CPM inputs given are accurate.
2. **Incrementality test, starting with the Q4 rollout (~Oct 1):** 15-20% audience holdout on the retargeting pool (ghost ads are the sharper design but Meta's minimums likely exceed an 8k-person account; default to holdout, which needs no platform minimum). Run 4-6 weeks. Decision rule: if holdout-measured lift on retargeting is indistinguishable from zero, retargeting spend goes to the pool ceiling and no further — the "11x" gets retired from the board deck.
3. **Blended metric to report to the board going forward:** total revenue ÷ total marketing spend, not per-channel platform ROAS. This is the number that's been flat all year and the one that will actually tell you if the split change worked.
4. Per-stage: spend, reach, frequency, CTR, CPM, platform CPA, new-vs-returning share.

## What's still needed to firm this up

- Confirmed event tracking on cart/checkout (prerequisite before building `RTG_HOT` — verify via `ad-conversion-tracking` before this ships).
- A real time-to-conversion export to replace the sector-proxy window edges.
- Confirmation of discount policy (question 7) and repurchase cycle, to firm the 180-day exclusion window.
- Actual current delivered-frequency reading, to reconcile the $12k spend against the stated 6/week cap.

Handoffs: `ad-conversion-tracking` (tracking verification, blocking), `ad-spend-allocation` (formal account-wide budget re-cut), `ad-creative-fatigue` (post-launch frequency monitoring), `ad-audience-targeting` (where the freed prospecting dollars should actually go), `ad-copy-variants`/`ad-creative-brief` (the 3 creative concepts per stage).

## One paragraph for the board

The 11x-vs-1.9x comparison isn't apples to apples yet — it hasn't been tested for incrementality, and the math shows the retargeting pool physically can't absorb a 50% share regardless: at current pool size, frequency cap, and CPM, retargeting tops out near 7% of spend, below where it sits today. Recommend redirecting the conversation from "shift the split" to "prove the number" — run a 4-6 week holdout starting this quarter, cap retargeting at its real ceiling in the meantime, and use the freed budget to test new prospecting audiences and creative rather than scaling what's produced a flat year.