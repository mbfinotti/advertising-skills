## How big is the LinkedIn attribution gap?

**Short answer: you can't get one clean number from what you have — and that's the actual finding.** The 38% click-ID coverage isn't a footnote to the "LinkedIn isn't working" story, it's the explanation for most of the gap.

### What the numbers actually say

- LinkedIn claims 4 of 23 closed-won deals → 17.4% of deals, ~$160k of the $920k (assuming average deal size).
- But LinkedIn's offline-conversion matching is **structurally capped by click-ID coverage**. If a lead has no click ID on file, LinkedIn has no way to claim it — full stop, independent of whether LinkedIn actually influenced it.
- Applying the 38% coverage rate to the 23 closed-won deals as a rough proxy: only ~9 of them even had a click ID to match against. Of those ~9 *matchable* deals, LinkedIn got credit for 4 — that's **~44%**, not 17%.
- The other ~14 deals (62%) weren't "LinkedIn lost the credit" — they were **unmeasurable by LinkedIn from the start**, regardless of channel truth.

So there are two different things hiding under "the gap," and they need to stay separate:

| Gap | Size | What it means |
|---|---|---|
| Measurement/instrumentation gap | ≥62% of leads have no click ID | LinkedIn is structurally blind to most of the funnel |
| Model/credit gap (within the trackable 38%) | ~56% of matchable deals still go to another channel | This is the only part that's a legitimate "LinkedIn vs. other channels" comparison |

The 17.4% headline number your CMO is reacting to blends both. It looks like a performance problem; it's mostly a plumbing problem.

### One more thing that makes it worse, not better

Don't assume closed-won deals share the 38% average coverage rate — they probably have *worse* coverage than typical Q2 leads, not the same:

- LinkedIn's click-ID window is short (default ~30 days, configurable up to 90) relative to a $40k-ACV B2B sales cycle that likely runs months.
- Multi-stakeholder deals mean the person who clicked the ad is often not the person whose email becomes the CRM lead record.
- Sales-assisted or offline conversion steps (calls, manually created CRM records) drop the click ID entirely.

If that's true here, the real matchable population among your 23 deals is smaller than 9, and LinkedIn's true in-window credit rate is *higher* than 44%, not lower.

### Why "rerun under a different model" is the wrong move

Two separate decisions are getting collapsed into one, and only the CMO's version optimizes for the wrong thing:

1. **Fix the instrumentation** — find out why 62% of leads have no click ID (Insight Tag not firing on every form/page, cookie-consent blocking, cross-device sessions, manually created leads, click-ID field not mapped into the CRM sync). This is a data-engineering fix, not an attribution-model fix.
2. **Pick an attribution model on its own merits** — a long, multi-touch, multi-stakeholder B2B cycle is exactly the case where last-touch is known to undercount top-of-funnel/paid-social channels, and where a multi-touch or time-decay model is the principled choice. That's a decision you make *before* looking at which channel it flatters, not after, "to see if it looks better."

Rerunning the same broken click-ID data through a different model to search for a friendlier number is model-shopping — it will change the story without changing the truth, and it'll be the first thing a skeptical exec or auditor challenges later.

### What I'd actually tell the CMO

"LinkedIn isn't working" isn't supported by this data. What's supported is: **at least 62% of Q2 leads are invisible to LinkedIn's attribution regardless of source**, and within the ~38% that are trackable, LinkedIn is getting credit for roughly 44% of matchable closed-won deals — not 17%. Fix click-ID capture first (this is the actual lever), then choose a multi-touch model on its own merits for a business with this sales-cycle length. Don't reverse the order.