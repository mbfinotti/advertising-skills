# Brightpath Paid Ads Consolidation Plan

## TL;DR

Two of the "rules" you've been given are folklore, not platform documentation — acting on them first would waste a month. Fix the diagnosis, then consolidate: fold the 9 persona ad sets into a smaller number of ad sets that carry one creative variant per persona (so the algorithm gets pooled signal and your CMO still gets per-persona reporting), carve Medlow out untouched, and turn Target CPA on now instead of waiting.

---

## 1. Two rules to drop before doing anything else

**"Raise each ad set's daily budget to 10x CPA before merging."**
No platform documents a 10x multiplier. TikTok documents ad-group budget ≥ 5x target CPA — a different platform, different number. Meta documents no CPA-to-budget ratio at all; what it documents is a _volume_ exit threshold (~50 optimization events per ad set per rolling 7 days). Funding 9 structurally overlapping ad sets to hit an arbitrary multiplier before merging is the worst order of operations available: you'd pour budget into 9 audiences that already compete with each other for the same HR/CFO/IT-admin buyers at the same target accounts, instead of merging first and funding the survivor. Drop the 10x step. Fund the _merged_ structure to clear the real threshold instead (math in §4).

**"Holding off on Target CPA until we hit 15 conversions in 30 days."**
Google's own documentation: Smart Bidding strategies including Target CPA work with no conversion history — they just get less certain early on. The 15-conversions/30-days figure you've heard is the _Target ROAS_ eligibility floor for Search/Shopping/Display specifically, not a Target CPA gate, and even that number is an evaluation checkpoint, not an on/off switch. **Turn Target CPA on now.** Waiting for a threshold that doesn't exist for this strategy is pure opportunity cost — and the fact that you're this far under 15/30 days at all is itself a useful data point (see §5): it says your bottom-funnel event may be too sparse for this account, on any bid strategy, until you either consolidate or move up-funnel.

---

## 2. What's actually going on, structurally

Your 9 ad sets are split by persona, which sounds like a defensible segmentation — but check it against why segmentation is normally worth keeping: it's worth keeping when the _offer or message_ genuinely differs per segment. Yours doesn't, yet: all 9 ad sets serve the same product demo ad. That's the exact anti-pattern this method flags — a dozen stacked interest and job-title filters propping up one generic creative. You're paying the fragmentation cost (signal split 9 ways, likely real audience overlap between HR Director, CFO, and IT Admin at the same target accounts) without collecting the benefit (nobody is actually seeing a message written for them).

That reframes the real question. It's not "consolidate vs. keep 9 ad sets" — it's "where does the persona knowledge you already have actually pay off: in the targeting filters, or in the creative?" Put it in the creative.

---

## 3. Target structure

**Carve out Medlow first, untouched.** The $2,000/month co-marketing guarantee is an externally mandated budget — the one preserve rule nothing else overrides. It keeps its own line with its own budget floor, reported separately, for the life of the contract. _Confirm one thing: is the Medlow line one of the 9 persona ad sets today, or a separate 10th line?_ Either way it stays structurally separate from the merge below; it just needs to be excluded from the shared pool.

**Merge the remaining persona ad sets into a small number of ad sets (default: one), each running one ad per persona as a creative variant — not one ad set per persona.**

- Consolidate the targeting: fewer, broader filters per merged ad set instead of ~12 stacked ones each. Let the algorithm find the audience; let the creative do the segmenting.
- One ad per persona inside the merged ad set(s), each speaking that persona's language (an HR Director ad ≠ a CFO ad ≠ an IT Admin ad — different pain point, different proof point).
- This is what answers "consolidate without losing control over who sees which message": delivery still matches ad variant to viewer, you just stop paying nine times over for nine separate audiences to each individually reach Meta's exit threshold.
- **Reporting:** Meta reports at the ad level even inside a merged ad set, so your CMO's weekly "spend and leads per persona" review survives untouched — you're reading it off the ad breakdown instead of the ad-set breakdown.

**Split back out only where you can name a real economic difference.** If CFO deals close at meaningfully different size/rate than IT Admin deals, that segment may deserve its own budget floor rather than full pooling — that's the one thing I can't decide for you without your numbers. Tell me if unit economics differ materially by persona and I'll adjust the target structure from "1 merged ad set" to "2–3 economics-based bands," each still running multiple persona creative variants inside it. Absent that, default to the fewest groups: one merged ad set, nine creative variants.

**Fallback if ad-level reporting isn't acceptable to the CMO for some reason:** `keep but re-parent` — pool budget and bid strategy under a shared structure while each persona keeps a separately reported line. This is the lower-risk, lower-negotiation move, but it only pools funding, not ad-set-level learning — your volume problem can still fail to clear even after doing this. I don't recommend it as the primary move here; use it only if full merge is politically blocked.

---

## 4. The budget floor, done with the real number

Replace "10x CPA" with the actual derivation: minimum daily budget ≈ target CPA × exit threshold ÷ threshold period.

- Meta's documented exit threshold is ~50 optimization events per ad set per rolling 7 days.
- So: **minimum daily budget per merged ad set ≈ target CPA × 50 ÷ 7.**
- I need your actual target CPA (and whether it's derived from unit economics or inherited from a dashboard — flag it either way) to turn this into a dollar figure. Send it and I'll compute the floor for the merged structure directly.

---

## 5. The evidence gate — where this plan is provisional

I can't yet certify a numbers-backed "merge exactly these branches" table, because I don't have:

- Per-ad-set conversion counts and spend on social (need this to run the volume + 3x-spend-for-significance tests per branch).
- The Google side's campaign/ad-group inventory (count, structure, spend, conversions per branch).
- Confirmation the target CPA is unit-economics-derived.
- Sales cycle length and whether there's a hard deadline or upcoming peak season (shapes how aggressive the migration phasing can be).

None of that changes §1–§4 — the folklore corrections and the creative-variant consolidation model hold regardless of the exact numbers. What it _does_ gate is the precise count of surviving ad sets and the exact budget floor. Send the export (per-branch daily spend + conversions, 30–60 days, same attribution window throughout) and I'll finish the branch-by-branch classification.

One flag worth taking seriously in the meantime: your Google side is already under 15 conversions in 30 days _account-wide_. If the fully-merged social structure and a consolidated Google structure still can't clear a reasonable per-branch threshold on "demo completed," consolidation alone won't fix it — no amount of merging conjures conversions that don't exist. The next move in that case is optimizing to a higher-funnel proxy event (demo _requested_, form started) and retargeting through it with CRM-fed outcomes, not more restructuring. Keep this on the table; don't act on it until the export confirms it's needed.

---

## 6. Migration sequence

| Phase               | What happens                                                                                                                                                                                                               |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0                   | Carve out Medlow's line at its own $2,000/month floor. No other change to it.                                                                                                                                              |
| 1 — prune           | Pause any social ad set with clearly duplicated audience and near-zero results; do not raise anyone's budget yet.                                                                                                          |
| 2 — merge           | Build the new merged ad set(s) fresh, with the persona creative variants, broader targeting. Do not edit the old 9 ad sets in place — editing resets learning, pausing doesn't.                                            |
| 3 — control         | Run the old structure at reduced budget alongside the new one for a few days as a comparison point, then pause (not delete) it once the new structure is live.                                                             |
| 4 — no-touch window | Pre-commit in writing: no significant edits for at least 14 days (30, or a full sales cycle, for a real verdict on a B2B buying cycle this long). Expect a transient dip — that's normal, not a signal to revert on day 3. |
| 5 — Google          | In parallel: turn on Target CPA now; once the branch export is in, collapse any single-keyword ad groups into few intent-themed campaigns (Hagakure method).                                                               |

Time phase 2 off any peak hiring/budgeting season you know is coming.

---

## 7. Measuring it

- **Baseline:** current blended cost-per-lead across the 9 ad sets, pre-merge.
- **Pass threshold at re-check date** (one learning cycle + one sales cycle after phase 3 completes): merged ad set(s) clear their volume/budget floor, blended CPL at or better than baseline, CMO still gets per-persona lead counts off ad-level reporting.
- **Rollback trigger, set now, before phase 2:** blended CPL worse than ~1.5x baseline after the no-touch window matures, or the Medlow line drops below its $2,000/month floor. Rollback = shift budget back to the paused (not deleted) old structure.
- **Verdict method:** prefer a platform lift study over raw reported ROAS/CPL for judging the merge — reported numbers on pooled retargeting-heavy structures routinely overstate true incremental performance. Escalate to a geo holdout only if this merge ends up moving a large share of the $15K.

---

## What I still need from you to finalize the numbers

1. Per-ad-set spend + conversions (30–60 days) for the 9 social ad sets.
2. Google campaign/ad-group inventory with the same.
3. Confirm: does any persona have materially different deal size/close rate than the others?
4. Confirm: is Medlow's line one of the 9 personas or a 10th, separate line?
5. Target CPA — from unit economics or inherited?
6. Sales cycle length / any hard deadline.

Send those and I'll turn §5's provisional flag into a final per-branch classification table and an exact budget floor in dollars.
