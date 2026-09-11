## How to measure whether the briefing process is working

The CMO's condition and her requested dashboard measure two different things. "Winner within two sprints" measures the *campaign*. "Briefs that produced winners" as the *day-one* quality metric measures the *process* — but it's the slowest, noisiest signal available, and it's the one metric this skill explicitly says not to stand up first. Putting it on a day-one dashboard sets the process up to look broken when it isn't, or look fine when it is.

### The math the CMO's condition is fighting

At 4 concepts/month, two sprints (≈1 month) is one concept batch of ~4. Motion's published number — ~5% of creatives become winners, across 578,750 creatives and $1.29B of spend — isn't a per-concept guarantee, it's a large-sample average, and it's measured on ad variants, not concepts. Even reading it optimistically per concept, a 4-concept sample has a real chance of producing zero winners with a perfectly healthy process. AppsFlyer's field number points the same direction: marketers typically test upward of 50 variations to find one winner. Two sprints of one team's output is not a large enough at-bat count to falsify or confirm the briefing process either way — a zero-winner month is expected noise, not evidence of failure.

So: don't let "did sprint 1-2 produce a winner" be the pass/fail gate on the process. Use it as a bonus outcome, not the test.

### What to actually instrument, in order

Stand these up in this sequence — each is strictly cheaper to run than the next, and the cheap ones are also the ones that are actually diagnostic of *briefing* quality specifically, rather than of concept luck, market fit, or media buying.

**1. Rebrief rate — the day-one dashboard metric.**
Share of briefs sent back by the executor for clarification before production starts, out of all briefs issued. One counter, kept by whoever issues briefs, updated the moment a brief bounces. This is the metric that actually isolates brief quality: a brief that gets rebriefed failed at the brief-writing stage, full stop, independent of whether the resulting ad ever runs or wins. Target: under 20%, then tighten against your own history once you have a baseline. This is what should be on the CMO's dashboard from day one — it's near-zero cost to track and it answers "is the brief clear" directly.

**2. Brief-to-launch cycle time — add in week 2-3.**
Two timestamps per brief: brief approved, asset live. Published B2B reference point: 10 business days or less. At 4 concepts/month this is one date pair per concept, trivial to log alongside the rebrief counter. It catches a different failure mode than rebrief rate — a brief that's clear but produces slow, stuck production (revision spirals, unclear ownership, missing assets).

**3. Concepts-briefed-to-winner ratio — a rolling 90-day trend, not a launch metric.**
This is the number the CMO wants. Stand it up, but on a rolling 90-day window, and treat it as noise until enough concepts have shipped — at 4/month, that's ~12 concepts in the first window, which is still thin. Read the *trend* against your own account's history, never against Motion's 5% figure as an absolute bar; that figure is an industry base rate, not your target. If your reporting stack already logs concept outcomes automatically, this ratio is closer to free and can move up the list — check that before assuming it has to wait.

### How to read the three together

- Rebrief rate climbing → brief problem. Fix the brief template, the interview, or who's approving.
- Cycle time climbing with rebrief rate flat → production/handoff problem, not a briefing problem — don't let it get blamed on the brief.
- Winner ratio flat or falling *while rebrief rate and cycle time stay clean* → a concept-diversity problem, not a briefing-process problem. The brief did its job; the account needs more distinct angles/personas in the mix, not tighter briefs.

That last line is the one to put in front of the CMO explicitly: a clean process (low rebrief, fast cycle) with no winner yet in month one is not evidence the process failed. A rising rebrief rate would be.

### Dashboard spec (what ships day one vs. what's labeled provisional)

| Tile | Status at launch | Cadence | Source |
|---|---|---|---|
| Rebrief rate (rolling 30d) | **Live day one** | Updated per brief | Manual counter, whoever issues briefs |
| Brief-to-launch cycle time | Live by week 2-3 | Per brief | Two dates on the brief doc |
| Concepts-briefed-to-winner ratio | Shown, but labeled "insufficient sample — provisional until ~90 days / ~12 concepts" | Rolling 90d | Brief outcome field + angle bank |

### What to bring back to the CMO

Reframe the sign-off condition from "produces a winning ad within two sprints" to: "produces a clean briefing process within two sprints — rebrief rate under 20%, cycle time under 10 business days — with the winner ratio tracked openly on the same dashboard from day one, reported as provisional until the 90-day/~12-concept mark." This gives her the visibility she wants immediately, without grading a process on a sample size too small to grade it fairly, and it gives you a documented basis to point to if a slow month gets read as a process failure.