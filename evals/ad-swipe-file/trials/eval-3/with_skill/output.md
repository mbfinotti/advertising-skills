# Harbourline Apparel — Restructuring the Competitor Swipe File

## The real number isn't 240. It's 6.25%.

15 of 240 saved ads ever reached a brief or a test — a 6.25% pipeline-conversion rate. Below a 50% floor, a swipe file is an archive, not a pipeline: it's been an archive for six months. **Doubling collection to 40 ads/week does not fix this — it makes it worse.** You'd be shoveling 4x more raw material into a funnel that already drops 94% of what enters it. The CMO's instinct ("more coverage") is solving for the wrong variable.

## Diagnosis: three compounding causes

1. **No mandatory pipeline field.** A spreadsheet of screenshots has no `test_status` column forcing every entry toward a decision. Entries sit as dead rows instead of moving `saved → hypothesized → briefed → testing → tested-won/lost`.
2. **No hypothesis step at session end.** Collecting is not the same job as converting. If nobody closes each session by writing 5–8 ranked hypotheses, saved ads never become briefs — they just accumulate.
3. **No owner.** Six months of "someone adds to the sheet when they see something" is reactive collection biased toward whatever was memorable that week, not a scheduled operation.

## What to change — restructure, don't scale

**1. Assign an owner.** One person runs the weekly session and is accountable for the pipeline-conversion rate, not the ad count. This is the single highest-leverage fix.

**2. Cut competitor scope to the direct set.** Six competitors in one pass is over the useful core (3–5 direct). Tier them now: keep 3–5 direct competitors on the weekly cadence, push the rest to an occasional adjacent/aspirational pass.

**3. Split into three collections, in this priority order:**

- **Competitor pulse** (the direct set, weekly) — the only collection that feeds decisions.
- **Pattern library** — repeatable mechanisms promoted out of the pulse at near-zero extra effort.
- **Vertical imports** — adjacent-category ideas, ad hoc, lowest hit rate.

**4. Make `test_status` mandatory on every entry, retroactively.** Go back through the 240 saved ads and tag each one. Anything that can't honestly be tagged past `saved` after six months is dead weight — archive it separately, don't count it toward the file.

**5. Enforce the schema, not just the count.** Every entry needs advertiser + tier, format, offer/angle, a longevity read (or `unknown`), one sentence of "why it might work," and a `test_status`. No entry without all five.

**6. Close every session with 5–8 written hypotheses**, format: _"We believe [change] will produce [outcome] because [insight, citing which competitor and which signal]."_ Take the top 3 forward to a brief. This step is what was missing — it's the only thing that moves ads from "saved" to "influenced a brief."

## Right-size the volume — replace the "40 ads/week" target

40/week is a vanity metric with no floor under it. Replace it with the actual guidance for a DTC apparel account:

- **20–30 ads per competitor** collected before classifying anything (not per week, per pull) — across a 3–5-competitor direct set, that's 60–150 ads for a full pulse, not 40/week forever.
- **Weekly 30–45 minute session per competitor**, hunting specifically for ads running 2+ weeks — longevity is the signal that matters, not raw count.
- Prioritize DTC-appropriate emphasis: hook and format variety, weekly refresh (fatigue is fast in apparel), high creative volume _downstream in testing_, not upstream in collection.

Volume should scale only after the pipeline-conversion rate recovers past 50%. Until then, the right move is to **hold or cut** collection volume and force every session to end in hypotheses, per the file's own recovery rule.

## Don't skip the corroboration step

Longevity alone is a weak signal — under cost-cap buying, "still running" increasingly means neglect, not a winner. Every saved ad needs at least one corroborator before it's trusted enough to brief:

`variant duplication > geographic/placement breadth > cross-competitor repetition > landing-page changes > relaunch recency`

Run cross-competitor repetition (the strongest one) as the last step of every session, once the whole pull is classified — it's the corroborator most swipe files never reach because it's only visible after classification, not during.

## Compliance flag on scaling collection

Quadrupling weekly volume across 6 competitors raises real exposure, not just an efficiency question:

- Stay logged off. Public, logged-off surfaces or official APIs only — never bypass authentication.
- **Never bulk-archive creative files.** A folder of screenshots is simultaneously the highest legal risk (verbatim reproduction at scale) and the least useful artifact (unqueryable). Capture structured records — paraphrase + one short attributed quote — never full transcriptions or downloaded assets.
- Set the ad-library country filter to an EU member state deliberately, even for non-EU markets — it's the only tier that discloses run dates and targeting, and it's the one thing that makes a longevity read defensible instead of guessed.

## The two numbers to report to your CMO going forward

Track these instead of raw ad count:

- **Pipeline gate**: ≥50% of saved entries reach `hypothesized` or further. You are currently at 6.25%. Fix this first.
- **Outcome gate**: creative win rate, ~4–9% depending on spend tier, measured only at ~20 launches per winner. If this stays near-zero once volume is adequate, that's a strategy/product-market-fit problem — escalate to an account diagnostic, not more ad collection.

## First two weeks

1. Assign the owner. Confirm the 3–5 direct competitors from your current 6.
2. Retroactively tag `test_status` on all 240 existing entries; separate the honestly-dead ones out.
3. Run one full pulse session on the direct set (20–30 ads/competitor), close it with 5–8 hypotheses, brief the top 3.
4. Report pipeline-conversion rate after this session as the new baseline — expect it far above 6.25% purely from adding the missing hypothesis step, before touching volume at all.

Once that rate holds above 50% for two consecutive sessions, that's the signal to scale — and even then, scale via more competitors or deeper corroboration, not an arbitrary weekly ad quota.
