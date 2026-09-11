# Format-fit diagnostic: Meraluna Skincare

**Short answer: no, the team is not right.** Every signal you've given points at creative execution and normal fatigue timing — not at vertical video as a format. The proposed fix (kill vertical video, move everything to carousels) is itself a format misfit if either campaign is running cold prospecting, which the numbers suggest.

---

## 1. The vertical video test — funnel localization

Reading your metrics top-down through the Stop → Stay → Click → Convert funnel:

| Stage | Metric | Reading | What it implicates |
|---|---|---|---|
| Stop | 3-sec view rate: 31% | Not itself the problem | The hook is getting *some* people to stop |
| Stay | Hold to 15s: 4% | **Collapse** — an ~87% relative drop from the Stop number | The on-ramp: seconds 3–15 of the creative, not the format |
| Click | CTR: 0.3% | Weak, but largely a downstream consequence of the Stay collapse | Desire/offer clarity mid-ad |
| Convert | Purchases ≈ 0 | Unmeasurable in isolation | Sample past the click is too thin to say anything about the landing page yet |

The diagnostic rule this skill uses is: **raise a format verdict only when a signal specifically implicates the format** — and none of the format-implicating signals have fired here:

- No completion-collapse-on-long-asset (this is a short-form asset, not applicable).
- No forced-view metric being misread as success (this isn't non-skippable/CTV inventory).
- **Frequency out of band** — not reported for this campaign. You need this number before ruling out audience/placement supply as the cause.
- **Placement-breakdown divergence** — not checked. If this is running across multiple vertical placements, a per-placement pull could show it's one bad surface, not "vertical video."
- **Failure persisting across every creative variant on one surface** — only readable if you've actually run more than one hook/cut. If this is one video, one hook, you don't have this signal yet either.

Meanwhile the practitioner refresh priority is **Hook → Visual treatment → Format → Body copy/CTA**. The team jumped straight to rung 3 without ruling out rungs 1–2, and your own numbers (a hard break between Stop and Stay) are a textbook hook/on-ramp signature, not a format signature.

**The static-image comparison doesn't rescue the conclusion either.** Comparing raw performance across two different campaigns is exactly the contaminated comparison this method warns against — delivery optimizes for marginal cost, not average, so the ad system chose who saw which asset under different objectives, budgets, and (probably) audience temperatures. "Static converts, video doesn't" from two live campaigns is not a controlled test; it's an anecdote with a dashboard attached.

## 2. The hero video "fading" at day 26 — this is on-schedule fatigue, not a format failure

Two numbers here, both inside normal range:

- **Frequency 2.1 on cold prospecting** — the comfortable band for cold prospecting is ~1.0–2.5. 2.1 is inside it. This is not an audience-exhaustion signal.
- **Day 26 of decay** — short video's expected creative lifespan is ~21–35 days. Day 26 is squarely inside that window.

This is fatigue arriving exactly on schedule, not evidence against the format. The correct move is a creative refresh (hand this to the creative-fatigue workflow), not a format verdict — and definitely not extrapolating "the hero video that crushed it for three weeks is now fading" into "vertical video doesn't work," when a 3-week hot streak followed by expected-window decay is closest thing to a success case this data shows.

## 3. Why "move everything to carousels" is itself the wrong prescription

If either campaign is cold prospecting (the hero video explicitly is; the vertical test likely is, given the metric set you're tracking), carousel is structurally the wrong landing spot: carousel's structural fit is **consideration, multi-product, warm audiences**, and it's explicitly flagged as wrong for **cold first touch** — it demands sequential swipe attention nobody gives on a first, cold exposure. Short vertical video, by contrast, is one of the few formats that structurally spans awareness through conversion, and it's the *top* efficiency row for demand creation (ahead of single image, in-stream, display, and carousel, in that order). Swapping your best cold-prospecting format for a warm-audience format because two data points looked bad would trade a creative problem for a structural one.

## 4. What I don't have, and what it would change

I'm answering off the numbers you gave, without the full interview (platform, objective the video campaign was actually optimized under, audience temperature for the video test, its frequency, placement breakdown, number of variants tested). None of that changes the direction of the verdict — the Stop→Stay collapse and the in-band fatigue numbers are strong enough on their own — but it would sharpen the fix. In particular: if the video campaign was bought on a video-views objective rather than conversions, judging it by purchase volume is comparing the wrong thing entirely — that objective optimizes delivery for watch time, not purchase intent.

## 5. Recommended next steps, cheapest evidence first

1. **Placement/creative breakdown on the existing report** (minutes, no spend): pull frequency, hold rate, and CTR split by placement and by hook. This alone should tell you whether it's one bad placement, one bad hook, or genuinely uniform across the format.
2. **Re-cut before you swap.** The video test's fix sits on the cheapest rung: re-cut the on-ramp (seconds 3–15) and tighten the offer/CTA — an hour of editing, fully reversible, original asset survives. Do this before spending a quarter's worth of effort commissioning a carousel program.
3. **Queue the hero video's refresh now**, ahead of full decay, rather than reading its softening as a verdict on the format — it's arriving right on the 21–35 day short-video lifespan window.
4. **Don't reallocate budget off two-campaign averages.** If you want a real format comparison, isolate vertical video vs. static in its own ad set with audience and budget controlled (a day of setup) before trusting a cross-campaign read.
5. Escalate to a holdout only if the isolated ad set stays ambiguous — that's a week-plus and real political capital, reserve it for a decision that moves the whole budget line, which "kill vertical video entirely" is.

## 6. Watch list

- Hold rate (3s→15s) on the next video cut, after re-cutting the on-ramp — this is the signal to confirm the fix worked.
- Frequency on the vertical video test, once available — if it's out of the 1.0–2.5 cold-prospecting band, that reopens a targeting/reach question the current data doesn't show.
- Placement-level CTR divergence — if one surface is eating most of the spend at a suspiciously cheap CPM, that's a placement problem wearing a "format doesn't work" costume.

## 7. Dated-numbers appendix

All practitioner heuristics, Aug 2026 snapshot, not platform-published gates — reverify against your own historical data before treating as a threshold:

- Cold-prospecting frequency comfort band: ~1.0–2.5 — **unverified-current**.
- Short-video/carousel creative lifespan: ~21–35 days — **unverified-current**.
- Static creative lifespan: ~14–28 days — **unverified-current**.

None of these gate a launch decision here (this is post-launch diagnosis, not a step-1 eligibility check), so I haven't pulled platform docs for them — they're practitioner convention, not a hard platform limit. Confirm against your own account's historical decay curves before you lean on the specific day-counts.