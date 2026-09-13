## Arcline Software — CPA drift diagnostic

**Bottom line up front:** this pattern (gradual drift, no cliff, flat spend) is a **measurement problem, not a performance problem** — and the timing points straight at the cookie banner. Read tracking first; everything downstream depends on it.

### Tracking — ❌ not fine (prime suspect)

- CPA drift started ~6 weeks ago; banner swap was ~5 weeks ago. Close enough that a gradual signal-loss curve (not everyone hits the new banner on day one — it rolls in as sessions/cookies churn) explains the "no single bad day" shape perfectly.
- A new consent banner commonly changes default state, CMP vendor, or the conditions under which the pixel/Conversions API fires. That silently drops _recorded_ conversions while real ones may be untouched — CPA rises on paper with nothing wrong in the account.
- **Check before anything else:** consent-grant rate before/after the swap; whether Consent Mode (or equivalent) is engaged and how much of "conversions" is now modeled vs observed; server-side/CAPI tagging still firing correctly; raw web-analytics or server-log lead counts vs ad-platform-reported conversions for the same days.

### Structure — can't confirm (data blocked)

- No ad-set/ad-level access, so structural issues (budget caps, overlapping ad sets, delivery imbalance) can't be ruled in or out directly.
- Nothing in what you've described (uniform-looking drift, flat spend, no discrete jump) is the usual structural signature — those tend to show as step changes when a budget or ad set is hit/paused. Provisionally fine; revisit once you get ad-set access.

### Targeting — can't confirm (data blocked)

- Same limitation: audience saturation or a bad expansion would normally show in reach/frequency, which you can't see at campaign level.
- Occam's razor: one coincident, well-timed tracking event explains the whole pattern more simply than an independent targeting problem appearing in the same six weeks. Provisionally fine, but re-test once tracking is cleared.

### Creative — can't confirm (data blocked), plausible secondary factor

- Ad fatigue is the other hypothesis that naturally produces a smooth drift rather than a cliff (frequency creeps up, CTR/CVR erode gradually).
- If your campaign-level export includes CTR over time, check it now — a declining CTR trend implicates creative; a flat CTR with declining CVR points back to tracking/landing page.

### Bids — ✅ fine as a root cause, but a likely amplifier

- Flat spend rules out you (or the agency) manually pushing bids up.
- If bidding is automated (Target CPA/ROAS), it optimizes against the same conversion counts that tracking may have broken — a shrinking, noisier signal makes the algorithm bid less efficiently, inflating real CPA further. This isn't an independent bid mistake, it's the tracking problem propagating through the algorithm.

### Recommended order of attack

1. Pull consent-grant rate and modeled-vs-observed conversion split for the last 8 weeks — this alone likely confirms or kills the tracking hypothesis.
2. Decompose CPA into CPC × (1/CVR) from whatever fields your campaign-level export has — tells you if the drift is upper-funnel (auction/bids) or lower-funnel (tracking/creative/targeting) even without ad-set data.
3. Push again for ad-set/ad breakdown or at minimum CTR/frequency at campaign level — needed to separate creative fatigue from targeting decay.
4. CRM access matters most as a _tie-breaker_ between "conversions are genuinely down" vs "conversions are fine, just invisible" — worth escalating past "maybe next month" once you have the consent-rate evidence in hand, since that evidence is what will make the case.
