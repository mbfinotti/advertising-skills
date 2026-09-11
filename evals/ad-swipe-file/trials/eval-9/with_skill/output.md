## Two changes to the plan before you touch anything

**Don't delete last month's pull folder.** This isn't a tidiness call — it's a hard rule in `ad-swipe-file`: *"Dated raw pulls live separately from this synthesized file and are never overwritten... re-runs create a new dated pull."* Deleting is strictly worse than overwriting.

Why it matters concretely here, not just as a rule:
- Most ad-library surfaces **purge a paused ad's disclosure the moment it stops running** (Meta Ad Library does this for non-political ads). Your dated pull is likely the *only remaining record* that those 3 Vantiro ads ever existed. Delete the folder and you can't re-verify, re-classify, or screenshot-cite them again — ever.
- The "2 ads relaunched from spring" read is a **relaunch-recency signal**, the skill's weakest-but-real corroborator — and it only exists because you can compare two dated snapshots. Deleting the folder that made that comparison possible undercuts the exact inference you just used it for, and blocks the same comparison next month.
- Storage isn't actually the cost people think it is: the guardrails already forbid bulk-archiving creative assets (images/video/full copy) — you're only supposed to be storing structured records and short paraphrases. A folder like that is tiny. There's no real tidiness gain from deleting it.

If the workspace genuinely needs decluttering, move the old pull folder to a `pulls/archive/` subfolder — don't delete it.

**"Update the master sheet in place" is correct, but only via change-log entries and field updates — not by silently editing or removing rows.** Concretely:

- **The 3 disappeared Vantiro ads:** don't delete their rows from the master sheet either (same rule, applies at the synthesized-file level too). Mark them inactive with a `disappeared as of [this pull's date]` note. Do **not** write "these lost" as fact — a pulled ad can mean it lost, graduated into a bigger buy, got replaced by a landing-page test, or was folded into a new concept. That's the observation/inference split the skill insists on: log the disappearance as observation, leave the "why" as an open inference or don't record one.
- **The 2 relaunched ads:** log them as `relaunched`, not `appeared` — they're returning entries, not new ones, so don't spin up duplicate records if they're still recognizably the same concept (dedupe on concept, per the hard rules). Relaunch is direct corroborating evidence: bump `longevity_signal` / `confidence` on those entries to reflect it. This is your second dated pull, which is exactly when relaunch-recency corroboration turns nearly free and starts pulling weight in the ranking — worth leaning on it here rather than treating it as a footnote.
- Add both as **change-log entries** in the master sheet: one `disappeared` (×3), one `relaunched` (×2), dated to this pull. That log is what step 9's "maintain the file on a cadence" actually requires each session — a raw pull alone doesn't satisfy it.

## Before you close this session

Per the workflow's maintenance step, this pull isn't done until you've also done the parts that are easy to skip:

1. **Test-status pass** on old entries — anything sitting at `hypothesized`/`briefed` for the disappeared ads' concepts, decide if it's now stale.
2. **Cross-competitor repetition check**, deliberately, now — it's the strongest corroborator in the whole list and the one the per-session efficiency ordering structurally starves. Worth 5 minutes: do the 2 relaunched concepts (or the pattern behind the 3 dropped ones) show up elsewhere in your direct set?
3. **A fresh hypothesis pass** — the relaunch is your strongest new signal this session (survived a pause-and-return, which is stronger evidence than an ad that just never stopped). If it scores well on signal strength and is absent from your own account, it belongs in this month's top-3, likely ahead of anything about the disappearances, which carry no positive signal by themselves.
4. Check the **pipeline gate** (≥50% of saved entries should reach a test status eventually) — a second monthly pull is a good checkpoint to see if last month's entries are still sitting at `saved`/`hypothesized` with no movement.

If you want, hand the resulting top hypotheses to `ad-creative-brief` next — that's the intended next stop once this session's classification and change log are settled.