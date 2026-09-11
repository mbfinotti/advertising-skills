## Is the 12% gap "normal"?

Plausible as a baseline, but you can't sign off on "normal" without knowing the cause — and something changed two months ago that should worry you more than the gap itself.

**Why a steady gap is unsurprising:**
- Dev-tool audiences over-index on ad blockers / tracking-blocking browsers (uBlock, Brave, Safari ITP, Firefox ETP) — this alone commonly produces 10-20% analytics undercount vs. backend truth for technical audiences, higher than consumer products.
- Other routine contributors: bot/spam signups that hit billing checks but skip JS trackers, consent-banner rejections, signups completed via email/API flows that never fire a pageview, timezone/day-boundary mismatches between the two systems.
- A *stable* ratio over a year is actually reassuring in one sense: it suggests a structural, systematic cause rather than random drift — which is exactly why the mix shift below matters so much.

**Why you shouldn't just wave it through as "normal":** you've never named the mechanism. "It's been ~12% for a year" is an observation, not a root cause. Without knowing *what* is missing, you can't know whether it's still *only* 12%, or whether it's currently 12% net while some channels are wildly over/under-tracked and others compensate.

**The channel-mix shift is very likely the same underlying problem, showing up differently.** Direct jumping 31%→44% while paid-social and organic-social drop, with totals flat, is the textbook signature of a tracking/attribution regression, not a real behavior change: real social-attributed visits are losing their referrer/UTM data and falling into the "direct" bucket (analytics' garbage-can category), rather than users actually switching channels. Two months ago is your window — check, in order of likelihood:
1. UTM parameters stripped or broken on paid-social campaign links (creative refresh, new campaign manager export, agency change).
2. A social platform change in link wrapping/in-app browser behavior (Meta, LinkedIn, X in-app browsers are notorious for stripping referrers or opening a fresh, cookie-less session).
3. A consent-management/CMP or tag-manager update ~2 months ago that now blocks/delays the tracking script specifically on social-referred sessions.
4. Any GA4/tag-manager/analytics migration or server-side tracking cutover in that window.

Pull session-level data for the last 2 months: are "direct" sessions landing on unusual URLs (campaign landing pages with no UTM), spiking from mobile in-app browsers, or clustering right after a specific deploy/tag change? That will confirm it's a measurement artifact, not real mix change. This needs root-causing this week — it's actively corrupting whatever channel ROI/budget decisions get made off this dashboard right now.

## Should you ship the 1.12 correction factor?

No — hold it, for concrete reasons, not just "more rigor is good":

1. **It fixes the wrong dimension.** The correction factor is a topline multiplier on total signups. It does nothing for the channel-mix problem — "direct" will still read 44% after you multiply everything by 1.12, because the error is in *attribution*, not in *count*. Shipping this factor lets the team feel like they've "solved" the analytics-billing discrepancy while the actual live bug (broken referrer/UTM tracking) keeps corrupting every channel-level decision downstream.

2. **A flat multiplier assumes the gap is uniform — that's exactly the assumption the current anomaly is breaking.** If the 12% is unevenly distributed across channels (e.g., ad-blocker usage differs by acquisition source, or the newly-broken tracking is channel-specific), multiplying every dashboard number by the same constant systematically misstates some channels and correctly states others, while looking uniformly "corrected." That's worse than an acknowledged gap, because it manufactures false confidence.

3. **The gap has never been root-caused, so "12%" isn't a known constant, it's a currently-observed ratio.** Baking it into every dashboard as a permanent multiplier turns an unexplained number into policy. If the true gap drifts — which it may already be doing, given the mix shift — the fixed 1.12 quietly becomes wrong and nothing will flag it, because the comparison process that would catch that drift is precisely what's being retired.

4. **The reconciliation process is the thing that caught this bug.** The channel-mix shift surfaced *because* someone was still doing the "tedious" analytics-vs-billing comparison. Institutionalizing a static correction factor and stopping that comparison removes your only early-warning system, right as it's mid-alarm.

**What to propose instead to your manager:** keep it cheap, not tedious — a lightweight automated monthly check (analytics vs. billing totals *and* channel-level deltas), alerting only when the gap moves outside a historical band (say 10-14%) or a channel's share moves more than a few points month-over-month. That gets them out of manual spreadsheet comparisons without giving up detection. Once the current channel-mix bug is root-caused and fixed, it's reasonable to revisit whether a documented, versioned correction is appropriate for a *specific known and stable* gap component (e.g., "ad-blocker undercount, revisited quarterly") — but not as a blanket, unexplained, "set and forget" 1.12 across every dashboard starting now.