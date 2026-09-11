## Landing Page Audit — Loftbeam Meta Demo Campaign

### Verdict: This is not a landing-page problem. Evidence points upstream to creative fatigue. Audit stops here and hands off.

Per this skill's workflow (step 2, "rule out upstream causes first"), a CPA chart alone cannot distinguish a page problem from an ad problem — but your numbers don't even require that judgment call, because **CTR is a pre-click metric**. Nothing on the landing page can move CTR; CTR is decided entirely by the ad and the audience seeing it, before anyone reaches the page. A CTR collapse from 1.7% → 0.8% (a 53% relative decline) over the same five weeks the page never changed is evidence the *ad*, not the *page*, degraded.

Cross-checked against the two hard triggers this skill is required to check before forming any page opinion:

| Signal | Your data | Read |
|---|---|---|
| CTR decline | 1.7% → 0.8% (−53%) | Well past the 20–30% decline band practitioners flag as fatigue (practitioner consensus, no controlled study behind the exact band) |
| Frequency | 2.2 → 5.9 over 5 weeks | Crossed the 2.5–3.0 prospecting-fatigue flag early and is now in/above the 4–6 band practitioners call "tolerable only for retargeting" — for a demo-gen (prospecting) campaign, 5.9 is high |
| Targeting/offer | Unchanged since March | Rules out an account-side targeting or offer swap as the cause |
| Page | Unchanged since March | Rules out a page regression as the cause — it's the one constant while CPA doubled |
| Conversion tracking | Dedup verified last week | Rules out tracking breakage as a confounder |

Rising frequency + collapsing CTR + a flat offer, targeting, and page is the textbook signature of the same audience seeing the same creative too many times — this skill's own trigger list names exactly this combination for hand-off to `ad-creative-fatigue`, not for a page audit.

**Why I'm not giving you a page fix list:** this skill is explicit that "a beautiful page that breaks message match wastes spend regardless of on-page craft" — and the inverse holds too: a page that's the one thing that *hasn't* moved isn't where a CPA doubling driven by pre-click metrics originates. Shipping page fixes now would spend engineering/design effort on a variable that isn't the leak, while the actual leak (fatigued creative burning spend on a shrinking effective audience) keeps compounding. Auditing the page when the ad is the problem is this skill's own #1 named failure mode.

### Hand off to: `mbfinotti/advertising-skills@ad-creative-fatigue`

Take these five weeks of CTR/frequency/CPA data there. That skill will run a proper confounder screen (budget changes, learning-phase resets, auction CPM inflation, seasonality) before confirming fatigue and will recommend the remedy — most likely creative refresh, possibly with `ad-copy-variants` or `ugc-ad-scripts` for the replacement asset, or `ad-account-diagnostic` if its own screen turns up something structural instead.

### Could not check (would sharpen the fatigue diagnosis, doesn't change this hand-off)
- The ad creative itself (copy/visual/hook) — needed to confirm this is whole-ad vs. hook-only fatigue.
- Audience/pool size and whether it's been narrowed — small pools hit high frequency faster and confound the read.
- CPM trend over the five weeks — separates auction-cost inflation from pure creative wear-out.
- Whether any budget increase coincided with the frequency climb — budget changes alone can push frequency up without fatigue.

### Come back here if
`ad-creative-fatigue` confirms fatigue, you refresh creative, and CPA is *still* elevated once frequency and CTR return to baseline. At that point the page becomes a plausible contributor and this audit should run in full — including the ad-to-page message-match check (I'd start there: "Scheduling that runs itself" is a strong, ownable headline, but it needs to be checked against whatever the *replacement* ad's promise is once you have one, not the current fatigued ad).

**Re-check:** log this hand-off now; re-open the page audit only after a creative refresh has had a full business cycle to show in CTR/frequency/CPA — re-running the page audit before then would just repeat this same upstream verdict.