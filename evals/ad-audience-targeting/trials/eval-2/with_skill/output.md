# Lumewick paid social — audience restructure

**Bottom line: not an all‑broad flip on Monday.** What launches Monday is a funded parallel test of broad against your current structure, plus an overdue cleanup of the interest ad sets that has nothing to do with the broad debate. Below is the full plan.

## Why not the wholesale switch

Ben Heath's and Demand Curve's "broad wins on mature accounts" claim is real and it actually fits Lumewick's profile: dense conversion data (380 purchases/week is well past the ~50 events/ad set/week learning threshold), a mature account, and blended CPA already beating target. That's exactly the condition that should move an account off the default "explicit layers" posture.

What doesn't fit is skipping straight to a full switch on the strength of three videos. That's general advice, not account-specific evidence, and even Heath's own position rejects killing everything else — he calls "kill retargeting entirely" the extreme view. The only honest way to move an account up a rung is a parallel test: duplicate the strongest performer into a broad version, run it alongside the current structure, and let Lumewick's own numbers decide. A wholesale rip-and-replace burns the control you'd need to know it worked, and if it underperforms you've lost the read on why.

Two things I'm flagging rather than assuming: (1) $95k/month against 380 purchases/week at $24 CPA doesn't reconcile — that spend and volume imply closer to $57/purchase, or a weekly spend nearer $9k, not $95k. Confirm which number is right before locking exact dollar floors below; I've used $95k/month as the funding base since that's what's stated as current spend. (2) Geography/universe size and current per-ad-set budget split weren't given — sizing below is directional, not exact.

## What's already wrong, independent of broad vs. layered

Five _interest-stacked_ ad sets is the named failure mode here regardless of what you do about broad: stacking interests shrinks the audience and raises cost without touching the actual lever, and major platforms treat interest inputs as soft suggestions, not hard constraints — they're the weakest tier on intent quality even when they work. Audit overlap across the five before anything else; if any pair overlaps >50%, merge; 30-50%, exclude. Consolidate down to one interest ad set kept alive as a research instrument, not a volume driver.

## Target tier structure

Re-ranked from the default order: this account already has a proven lookalike and retargeting pool, so the open question is entirely on the cold-prospecting side, which is why broad leads the table.

| Tier                                 | Defining signal                                        | Est. size                                     | Exclusions                                             | Test budget/day                                                     | Success criterion                                                               |
| ------------------------------------ | ------------------------------------------------------ | --------------------------------------------- | ------------------------------------------------------ | ------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Broad/algorithmic (new)              | None — delivery model runs on the purchase event       | Large (confirm geo/universe)                  | past buyers, retargeting pool, lookalike audience      | ~$350 (clears the ~50/wk floor with room to read)                   | ≤$28 CPA at volume comparable to current interest tiers                         |
| Lookalike (existing)                 | Resemblance to seed, unchanged for now                 | Millions                                      | past buyers, retargeting pool                          | current run rate                                                    | within 15% of broad's CPA, else fold into broad                                 |
| Interest — consolidated (was 5 sets) | Best-surviving interest cluster(s) after overlap audit | Post-merge, smaller                           | past buyers, retargeting pool, lookalike               | reduced vs. current combined 5-set spend, kept above $200/day floor | not judged on CPA alone — reports which segment responds, for creative planning |
| Retargeting (existing)               | Site visitors + cart abandoners                        | Not provided — confirm against platform floor | past buyers                                            | 15-25% of total spend                                               | watch for inflated ROAS; not proof of incrementality                            |
| Past-buyer suppression               | Customer list                                          | Not provided                                  | applied everywhere except any future win-back campaign | n/a (suppression only)                                              | n/a                                                                             |

Retargeting above ~40% of spend is a red flag, not evidence retargeting "works" — check current allocation against that before scaling anything.

## Exclusion matrix

| List               | Applies to                                                     |
| ------------------ | -------------------------------------------------------------- |
| Past buyers        | All tiers (this is already running — keep it)                  |
| Retargeting pool   | Broad, lookalike, interest                                     |
| Lookalike audience | Broad                                                          |
| Interest audience  | Broad, lookalike (so consolidated interest keeps its own read) |

## What launches Monday vs. what waits

1. **Monday:** launch the broad duplicate (same creative/offer as your best interest ad set, open targeting, exclusions above, funded at ~$350/day). In parallel, run the overlap audit on the five interest ad sets and consolidate to one.
2. **Weeks 1-4:** fixed budget per tier, no algorithmic budget pooling — pooling during a test starves the exact tiers you're trying to read. One variable isolated: audience.
3. **Week 4 decision**, per tier: **promote** (beats $28, scale ≤20%/week), **hold** (within ±20% of target or still learning), **kill** (2× target CPA spent at 50%+ worse than the best funded tier, or stalled below floor).
4. **If broad wins convincingly:** shift the bulk of prospecting budget into it over subsequent weeks — but keep the consolidated interest set and lookalike funded as a standing research instrument and a hedge, and keep retargeting exactly where the skill puts it (a floor, never the growth lever). Broad hides who the buyer is; losing every manually-defined tier means losing your only read on that.
5. **If broad doesn't clear the bar:** revert the freed budget to the consolidated interest set and lookalike, keep a small broad line running as an ongoing calibration check rather than killing it outright — mature accounts are worth re-testing broad periodically as data density keeps growing.

## Compliance

None triggered. Candles aren't a regulated targeting category; no restricted-targeting mode applies.

## Review cadence

- Overlap audit before the broad ad set launches and again before any tier is folded into another.
- CPA and floor check weekly through the 4-week test.
- Lookalike seed refresh every 30-60 days.
- Past-buyer exclusion list refresh on whatever cadence it's currently synced.
- Full structure review at the week-4 decision point, then quarterly.
