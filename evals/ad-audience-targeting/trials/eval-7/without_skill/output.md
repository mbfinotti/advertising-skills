## Duvette & Co — Meta Ads Audience Overlap: What To Actually Do

**Short version: don't merge yet. Fix exclusions first — they're skewing every overlap number you're looking at. Then re-measure, then act pair by pair, and "merge" is the wrong verb for most of what needs to happen.**

### Why "just merge everything that overlaps" is the wrong instruction

- Overlap ≠ redundancy. Two ad sets can reach the same people while serving different jobs (funnel stage, creative angle, intent signal). Overlap alone doesn't tell you to collapse them.
- You can't cleanly "merge" a Lookalike source + an Interest audience + a Behavioral signal + Broad into one ad set. Combining audiences uses AND logic (shrinks reach toward zero) or requires building a new OR-combined Custom Audience — and merging anything with Broad is close to meaningless, since Broad already has no restriction and is a superset of the others.
- Literally merging ad sets resets each one's delivery history and learning phase. You lose the ability to ever know which source actually drove results — the opposite of what an overlap review is supposed to protect.
- Right now, your overlap numbers are contaminated. With zero exclusions anywhere in the account, some real chunk of every pairwise overlap is just "same existing customers and same warm retargeting users showing up in all four pools" — not genuine prospecting redundancy. Acting on today's numbers means acting on the wrong signal.

### Step 0 — Fix exclusions first (today, before touching any ad set structure)

This isn't optional prep, it's the actual highest-priority issue in this account — bigger than any of the four overlap numbers.

1. **Exclude your Customer List (all-time purchasers) from all four prospecting ad sets** — Lookalike, Interest, Behavioral in-market, Broad. Right now you're paying acquisition CPMs to re-show ads to people who already bought.
2. **Exclude your Retargeting pool from all four prospecting ad sets.** Without this, prospecting and retargeting are bidding against each other in the same auctions for the same warm users — that alone inflates CPMs account-wide and steals conversion credit from whichever campaign happens to win the auction, independent of which one is actually better.
3. **Decide what the retargeting pool is for**, then exclude accordingly: if it's meant to convert non-buyers, exclude the Customer List from it too; if it's also doing winback/repeat-purchase, split that into its own segment rather than blending it — otherwise you can't tell "new conversion" from "repeat purchase" in retargeting's numbers either.

### Step 1 — Let it settle, then re-pull overlap

Give it a few days of clean delivery post-exclusion (enough to exit the post-change turbulence and accumulate real signal) before re-running Ads Manager → Audiences → Show Audience Overlap on all pairs. Expect the numbers to move, likely down, especially interest-vs-behavioral and lookalike-vs-behavioral.

### Step 2 — Handle each pair on its own merits, in this order

Work from highest overlap to lowest — the Behavioral in-market ad set is the common thread in three of your four measured pairs (24%, 38%, 56%), so resolving its position first has the biggest knock-on effect.

**Behavioral in-market vs Broad prospecting — 56%. Priority #1.**
High overlap here is structurally expected: Broad has no targeting restriction, so it's a superset containing Behavioral by definition. The real question isn't "do they overlap" but "does the narrower audience still earn its keep." Don't merge — run a real test: pause Behavioral in-market for 1–2 weeks, let Broad absorb its budget, compare CPA/ROAS. If Broad matches or beats it (common once a pixel has enough conversion volume for Meta's algorithm to work), retire Behavioral permanently and put that budget/creative effort into Broad. If Behavioral still clearly wins post-exclusion, keep both, but exclude the Behavioral audience from Broad specifically so Broad stops re-competing for ground Behavioral already owns.

**Lookalike vs Behavioral in-market — 38%. Priority #2.**
This is real redundancy, not structural. After exclusions, if it's still above ~30%, don't merge the audience definitions — pull CPA/ROAS for both, and either (a) consolidate spend under Campaign Budget Optimization so Meta's auction allocates dynamically between them, or (b) pause the weaker one and redirect its budget, keeping the definition on file to re-test later rather than deleting it.

**Interest vs Behavioral in-market — 24%. Watch, don't touch.**
This sits in the ambiguous middle. These two represent genuinely different intent signals (interest = passive affinity, in-market = active purchase intent) which is a legitimate reason to keep them separate even with moderate overlap. Re-check this number after exclusions — if it drops toward 15% or below, leave it alone indefinitely. If it holds at 20%+, the fix is creative differentiation (make sure in-market gets urgency/comparison messaging and interest gets discovery/awareness messaging) before you even consider a structural change. No merge.

**Lookalike vs Interest — 8%. No action.**
Below any meaningful threshold (industry rule of thumb: under ~15% is noise). This pair is healthy audience diversification working as intended. Leave it exactly as is.

### One-line summary of the plan

Exclude customers and retargeting pool from all prospecting ad sets → wait and re-measure → test retiring or de-overlapping Behavioral against Broad → test consolidating Lookalike/Behavioral spend via CBO or pausing the weaker one → leave Interest/Behavioral to a creative fix, not a structural one → leave Lookalike/Interest untouched. Don't merge audience definitions anywhere — retire, exclude, or consolidate budget instead.