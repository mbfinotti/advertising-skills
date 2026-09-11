# Klarawave — Creative Test Block
**Channels:** Meta, TikTok · **Launch:** Monday, Sep 14, 2026 · **First checkpoint:** Wednesday, Sep 16 (AM)

## 1. Test setup

- 6 creative files launch Monday, Sep 14, simultaneously on Meta and TikTok.
- Treat each file as 12 independent data points: 6 files × 2 platforms, scored separately (a file can pass on one platform and fail on the other).
- Equal budget/impression pacing across all 6 files per platform — no early reallocation before the Wednesday checkpoint.

## 2. Hook rate definition

| Platform | Hook rate formula | Source |
|---|---|---|
| TikTok | 3-second video views ÷ impressions | TikTok Ads Manager |
| Meta | 3-second video plays ÷ impressions | Meta Ads Manager (video metrics) |

Pull both from platform-native dashboards so the 32% bar is measured the same way on each side.

## 3. Sample size gate

- A file is only eligible for a kill/keep decision once it has **600–900 impressions**.
- If a file hasn't reached 600 impressions by Wednesday AM, hold the decision — flag it "insufficient data," let it run to the floor, and re-check same day afternoon or Thursday AM.

## 4. Wednesday morning kill rule

- Checkpoint: **Wednesday, Sep 16, AM** (fix a specific hour, e.g. 9:00 local, so the whole team pulls numbers at the same moment).
- Rule: **hook rate < 32% → kill.** Same bar on Meta and TikTok, per the TikTok agency's healthy-rate benchmark.
- Kill = pause spend on that file in its current ad set.
- Files at ≥32% keep running unchanged, same audience, no action needed.

## 5. Mid-week second chance (audience swap)

⚠️ Read this alongside §4 — "kill" and "give a second chance" are two different actions applied in sequence, not simultaneously. Resolution used below: **kill = stop spend in the original audience; the swap is the one-time reprieve**, not a reason to keep spending in the same audience that already failed.

1. For every file killed in §4: pause it in the current audience, then relaunch the **same creative** into a **new audience segment** the same day.
2. This is a one-time second chance — not a repeating loop. No further audience swaps this cycle.
3. Second checkpoint: **Friday, Sep 18 AM** (or whatever your reporting cadence is) — apply the same 32% hook-rate bar.
4. If the new audience doesn't get to 600 impressions by Friday, judge directionally (hook rate trend so far) rather than forcing a hard call — no fresh threshold was set for this window, so use judgment and flag it in the recap.
5. Fails again at the second checkpoint → final kill, no further swaps.

## 6. Reporting

- Log for each of the 12 file/platform combinations: launch date, impressions at each checkpoint, hook rate, kill/keep/swap decision, and (if swapped) the second-checkpoint result.
- Roll this into the **end-of-month slide deck** as usual — one slide per platform, or one combined table with a pass/kill/swapped-and-passed/swapped-and-killed column.

---

**Flag for you to confirm before Monday:** the audience-swap step above is my interpretation of "gets killed" + "fair second chance" — if you actually meant something looser (e.g. swap audience *instead of* killing, or swap only applies to a softer underperformance tier below 32% but above some lower floor), say so and I'll rewrite §5.