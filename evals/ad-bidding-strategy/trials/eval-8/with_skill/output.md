## Verdict: No to both, as proposed

Both proposals fail the same gate before efficiency is even a question: **no conversion values flow from Salesforce to Google or LinkedIn today.** A Target ROAS or value-based strategy needs real deal values to optimize against. Right now neither platform would receive any — not noisy ones, none. That's not a target-setting problem, it's a measurement problem, and it blocks both asks regardless of campaign size.

On top of that, the portfolio-pooling piece has a second, independent problem even once values exist.

## Why the portfolio Target ROAS fails

1. **Value integrity gate.** Target ROAS is a return-goal archetype — it needs differentiated, real deal values flowing back. You have none. Pooling doesn't fix this; there's nothing to pool.
2. **The three campaigns aren't compatible enough to pool, even setting the gate aside.** Branded (120/mo), competitor prospecting (14/mo), and generic demand (9/mo) are different buyer intents at different funnel depths with different economics — branded traffic is close to a decision, prospecting is comparison-shopping, generic demand is top-of-funnel. Pooling migrates spend toward whichever campaign's economics dominate the blended signal (almost always branded), silently starving or mispricing the other two. Pooling a brand line with prospecting is the specific case this kind of policy exists to catch.
3. **The real motive is a volume workaround, and it's the wrong fix.** Target ROAS on Search documents a 15-conversions/30-days minimum. Competitor prospecting (14/mo) sits right under that bar; generic demand (9/mo) is well under it. Pooling is the agency's way to synthetically clear that floor. The correct fix for thin campaigns is either accepting a volume-appropriate archetype (cost-goal or volume-maximizing) or genuine structural consolidation if the segmentation is redundant — not blending unlike economics under one shared target.

## Why the LinkedIn value-based ask fails

Same gate, no exception: value-based bidding optimizes toward deal value. With no Salesforce-to-LinkedIn pipe, there's no value signal to optimize toward — the archetype has nothing to run on yet.

## What to green-light instead, right now

Per campaign, single-signal, no pooling:

- **Branded (120 conv/mo)** — cost-goal (Target CPA), set at trailing actual, not an aspirational number. Volume is mature and well past any documented threshold. This is also the one campaign that could plausibly earn return-goal on its own once values flow — it's the only one with volume to spare.
- **Competitor prospecting (14/mo)** — cost-goal or volume-maximizing on its own signal. Thin volume means slow diagnosis and variance, not an eligibility problem — it doesn't need to borrow signal from branded to run.
- **Generic demand (9/mo)** — same, even thinner; volume-maximizing or manual is the safer near-term choice until it builds its own history.
- **LinkedIn** — keep the current volume/cost-based strategy. Don't switch to value-based bidding until deal values are actually landing.

## The one project that actually unblocks the agency's plan

Build the CRM-to-platform value passback: differentiated deal values (not one flat number), net of lost/disqualified deals, timely enough relative to your sales cycle to matter to the bidder. This is a RevOps/ops-owned measurement project, not a bidding-strategy change — it's the precondition for everything the agency is proposing, on both platforms.

It also isn't free to flip on later: sending deal values to Google and LinkedIn is a data-sharing decision, not just a technical one — expect a consent/data-processing review before that pipe goes live, and treat that review as part of the project, not an afterthought once the integration is built.

## Switch trigger — when to revisit this

Return-goal (Google) and value-based bidding (LinkedIn) become worth reopening once:

- Deal values are flowing to the platform, differentiated and timely, **and**
- The specific campaign clears its own documented return-goal minimum on its own signal — not pooled with the other two.

Branded is the one to test this on first; it's the only campaign already carrying enough volume for the evidence to mean anything.
