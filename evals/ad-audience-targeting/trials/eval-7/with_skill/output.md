## Duvette & Co — overlap audit response

First, don't do what the marketing lead proposed. "Merge everything that overlaps" treats every overlap number the same, but the skill's overlap discipline splits into four different responses by band, and blanket-merging would destroy the per-tier read on pairs that don't need it — including one pair (lookalike/interest, 8%) that barely overlaps at all. Only one of your four pairs actually clears the merge threshold.

### Step 0 — fix first, before touching any pair

Your account currently has **zero exclusions anywhere**. That's the named top failure mode ("no exclusion matrix: tiers silently bid against each other and against the customer base"), and the rule is explicit: exclusions run before inclusions, before any pairwise fix below.

- Upload the customer list as a suppression list and exclude it from all four funded ad sets (lookalike, interest, behavioral in-market, broad prospecting) — unless one of them is a deliberate winback/upsell campaign.
- Exclude the retargeting pool from all four ad sets. Retargeting sits above lookalike, interest, behavioral, and broad in intent, so right now each of those four is wasting spend re-competing for people the retargeting pool already owns.
- After both exclusions land, re-check each ad set's size against its platform floor. Stacking exclusions can silently push a tier below the floor and halt delivery — that's the failure mode on the other side of this fix.

This is foundational and unconditional: do it regardless of the pairwise numbers below, because it changes the composition of all four audiences before you decide what to do with the pairwise overlaps.

### Step 1 — the four pairs, by band

| Pair                                      | Overlap | Band      | Action                                                                                                                            |
| ----------------------------------------- | ------- | --------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Lookalike vs interest                     | 8%      | Under 10% | **Ignore.** No action. These are functioning as genuinely separate audiences.                                                     |
| Interest vs behavioral in-market          | 24%     | 10–30%    | **Monitor.** No action now. Track it at your next overlap audit (before any new tier launch, or the weekly check during testing). |
| Lookalike vs behavioral in-market         | 38%     | 30–50%    | **Act — exclude, don't merge.**                                                                                                   |
| Behavioral in-market vs broad prospecting | 56%     | Over 50%  | **Merge.**                                                                                                                        |

**Lookalike vs behavioral (38%):** the 30–50% band's rule is "add an exclusion > consolidate" — exclusion is an hour of reversible work, consolidation destroys the read your test budget is paying for. Lookalike outranks behavioral in the tier model's efficiency order, so exclude the lookalike audience out of the behavioral ad set (higher-intent tier excluded from the lower-intent one), not the reverse. Only escalate to a merge if, after the exclusion, either ad set's post-exclusion size falls near its platform or budget floor — check that before finalizing, don't assume it.

**Behavioral vs broad (56%):** this is the one pair that actually meets the merge bar. Over half of behavioral's reach is people broad prospecting already finds on its own — the behavioral layer isn't buying incremental delivery at that overlap level. Before you execute the merge, pull each ad set's current cost-per-result: whichever side is cheaper should be the surviving targeting logic (don't default to "broad wins" or "behavioral wins" without data). Also confirm behavioral has already had at least one full test cycle with a promote/hold/kill verdict — merging before that verdict exists destroys the attribution the test existed to produce.

### Order of execution

1. **Exclusion matrix (Step 0)** — do this first, always. It's cheap, foundational, and changes what the pairwise numbers below actually mean.
2. **Lookalike vs behavioral exclusion (38%)** — do this before the merge decision. It changes behavioral's audience composition, which can shift the behavioral-vs-broad overlap number. Re-measure behavioral vs broad _after_ this exclusion lands, before committing to the merge.
3. **Behavioral vs broad merge (56%)** — execute last, using the re-measured overlap and current cost-per-result data to pick the survivor.
4. **Interest vs behavioral (24%)** and **lookalike vs interest (8%)** — no action, no ordering priority. Just don't touch them.

### Why not merge everything

- Lookalike/interest at 8% aren't competing for the same people — merging them throws away a working, non-redundant pair for no reason.
- Interest/behavioral at 24% is a "watch it," not a "fix it" — acting on a monitor-band pair before it crosses 30% is pre-emptive and burns the per-tier read early.
- The 30–50% band exists precisely so you don't jump straight to merging: an exclusion is reversible in one click, a merge isn't. Merging lookalike into behavioral now would cost you the exact attribution ("which segment is actually responding") the layered plan was built to produce.

Re-run the full overlap audit before launching any new tier, and again after Step 0 and Step 1 land, since the exclusion matrix and the lookalike exclusion will both move the remaining numbers.
