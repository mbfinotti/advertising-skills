# Attribution Reconciliation — Corvid Analytics, September 2026

## Headline

Anchor: CRM, 74 demo bookings/month. Google + LinkedIn combined self-report 118 — a 1.59x combined multiplier, not a 44-unit gap to explain. **Never sum platforms**: this isn't 44 phantom demos, it's two platforms each claiming credit for overlapping subsets of the same 74. Verdict: **structural, not a defect** — but it can't be _settled_ by reconciliation math alone, and your constraint (no holdout, anywhere) removes the one method that would settle it outright. The 9% residual is a separate, smaller problem, and it's already solved: stop working it.

Bottom line on your actual question: **no, don't buy an MMM platform, not for this.** Wrong tool for both problems you named. Details and what to do instead follow.

## Problem 1 — the 118-vs-74 platform fight

This is Bucket 2 (definitional), specifically the line the skill names directly: _cross-platform self-crediting overlap — several platforms each claiming the same conversion._ Expected mechanism: Google Ads and LinkedIn Ads each apply their own last-touch (or their own attribution window) against their own click, blind to the other platform's touch in the same buyer journey. A B2B demo booking that saw both a LinkedIn ad and a Google search ad gets claimed in full by both. That alone can produce numbers like yours with zero tracking defect anywhere.

Before treating this as fully explained, run the ratio check the skill specifies — you're missing one input:

- **Split the 118**: how much does Google alone claim vs. the CRM's 74, and how much does LinkedIn alone claim vs. the same 74?
- **If either platform alone is above ~1.5x the CRM number**, that individual platform moves to Bucket 3 (duplicate-firing tag, dedup failure) — a tracking defect, not a crediting-model artifact, and it hands off to your conversion-tracking work, not this analysis.
- **If neither is individually above ~1.5x**, the whole 118-vs-74 gap is explained by self-crediting overlap. Document it as a known delta, not a residual.

This is a 10-minute pull from each platform's own dashboard. Do it before anything else below — it changes which of the next steps even apply.

**What reconciliation cannot do, no matter how well you run it**: prove _which_ platform's claim is more real. Both platforms genuinely believe they drove the demo. The CRM can prove the demo happened and can show which touches occurred (if you're capturing click IDs), but it cannot arbitrate causal credit between two channels that both touched the same buyer. That's not a math problem — it's a causal-inference problem, and reconciliation, however rigorous, is not a causal-inference method.

## Problem 2 — the 9% residual

Apply the judgment test: stable period over period, small, survives every known mechanism you've checked. That's a **pass**, not an open investigation. Your own framing ("steady at that level," "survives every explanation") is the pass condition stated in your own words. Officially published tolerance (GA4's own docs) treats up to 10-20% as expected and not a concern; 9% sits inside that band.

Stop chasing it. Document it as a known delta, re-derive it next period (it will drift with consent rates and mix, don't treat it as a fixed correction), and move on. Continuing to investigate a stable, in-band, already-decomposed residual is the specific failure mode the skill calls out: _driving the residual to zero is evidence of fabrication, not rigor._

## The actual decision: is MMM the next rigorous step?

Run it against what each method actually buys, given your one hard constraint.

**Your constraint deletes the one rung built for exactly this fight.** A holdout or geo test is the only method that "settles a two-platform ownership fight outright" — literally the skill's language for the situation you're in. "CFO will not approve turning ads off anywhere — no dark regions, no test cells" is precisely the condition that deletes that rung. So the method purpose-built for your question is off the table. That's worth saying to leadership plainly: **given the current constraint, no method — including MMM — delivers the certainty they're asking for.** Certainty on channel-level causal credit requires either withheld spend somewhere, or accepting a proxy that isn't causal.

**Why MMM specifically doesn't fit, independent of the holdout question:**

- MMM's value proposition is _portfolio allocation across channels no conversion record covers at all_ — offline, brand, channels with no click-level tracking. You have two channels, both fully digitally tracked, both feeding a CRM with named-account resolution available. There's no coverage gap for MMM to fill here.
- MMM is a standing job: pipeline, modeling, a refresh cadence someone owns permanently. At $70k/month across what reads as essentially two paid channels, there isn't enough spend variance across enough independent channels/geos over time to identify stable coefficients — a model with that few degrees of freedom returns wide, unstable confidence intervals, which is the opposite of the certainty leadership is asking for.
- It doesn't resolve the specific dispute you have. MMM outputs portfolio-level elasticity, not "which platform gets credit for this cohort of demos." Even a well-built MMM here would not tell you whether Google or LinkedIn drove a given batch of the 74 — it would tell you aggregate revenue response to spend shifts, at a scale too small to trust the read.

Ranked against the deleted holdout, what's left:

- **efficiency**: self-reported attribution > server-side collection with shared event IDs > consent-signal configuration > MMM
- **value**: server-side collection with shared event IDs > self-reported attribution > MMM > consent-signal configuration
- **effort**: MMM > server-side collection > consent-signal configuration > self-reported attribution

MMM loses on efficiency and doesn't win on value here because its value proposition (offline/brand coverage) doesn't apply to your channel mix. It's not merely last — its condition for promotion (portfolio spans channels no conversion record covers, someone owns a permanent refresh cadence) isn't met. **Delete it from this account's menu rather than parking it as "later."**

## What to do instead, ranked

1. **Split the 118 by platform against the CRM's 74** (today, ~10 minutes). Confirms whether Problem 1 is pure crediting overlap or hides a Bucket 3 tracking defect on one platform. Gate everything else on this.

2. **Self-reported attribution — the default rung, promote it now.** Add "How did you hear about us / what made you book this demo?" as a required field at the point of demo booking, closed-won or not.
   - You spend: an hour of form work plus one reporting field, then a period before it reads.
   - You get: an independent channel signal that survives the entire self-crediting fight — the buyer, not either platform, states the answer. Coarse and self-report-biased, but unblockable by your constraint since it withholds nothing.
   - You owe: a privacy-notice line for the new field.
   - This is the fastest thing that actually moves leadership toward an answer, and it runs starting this week.

3. **Server-side click-ID capture on the CRM lead record**, if not already in place (`gclid`/`wbraid`/`gbraid` for Google, `li_fat_id` for LinkedIn) — this is the standard B2B bridge the skill names, and it's what makes the platform-split in step 1 auditable going forward instead of a one-time pull. Practitioner-reported match rates run 75-85%; below ~50% on either platform signals a capture defect (cookie loss, redirect stripping), which is a Bucket 3 handoff to your tracking-fix work, not this analysis.
   - You spend: engineering weeks, one hidden form field, CRM schema work.
   - You get: observed multi-touch paths per demo instead of two platforms each claiming 100% blind to the other — this is what actually lets you see overlap directly instead of inferring it from a ratio.
   - You owe: nothing regulatory beyond what you already handle for the CRM.

4. **Reopen the "no dark regions, no test cells" constraint as a narrower ask**, once you have the platform split from step 1. If one platform is carrying most of the disputed credit, a scoped, short, single-metro or single-campaign-type holdout is a much smaller ask of the CFO than "turn ads off somewhere" — and it's the only thing that converts "we believe" into "we measured." Worth one direct conversation before writing this off entirely: the constraint as stated ("no dark regions, no test cells... spend keeps running") may be a reaction to a much larger ask than what a scoped test actually requires. Frame it as weeks, not indefinite, and reversible by turning spend back on.

5. **MMM: not now.** Revisit only if the channel mix genuinely expands to include spend MMM is built for — offline, brand, sponsorship, channels with no conversion record at all — and someone is named to own a permanent modeling refresh cadence. Neither condition holds at $70k/month across two fully-tracked digital channels.

## What to tell leadership

The 9% is closed — document it, stop spending analyst time on it. The 118-vs-74 is not a gap, it's two platforms both telling the truth about a touch they each saw; the real open question is causal credit between them, and the one method built to answer that is currently off the table by CFO policy. Certainty is available, but it costs a scoped test, not a bigger analytics purchase. Everything short of that (self-reported attribution, server-side stitching) gives triangulating evidence, not proof — useful for the reallocation decision, but label it as such when it reaches the board deck.
