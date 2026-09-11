## Arcline Software — ad-account diagnostic (ad-account-diagnostic skill)

Straight answers first, full reasoning below — but note upfront: the skill this runs on explicitly bans collapsing findings to pass/fail when evidence is missing ("unknown is not pass — an unchecked layer silently marked clean is the most common way audits go wrong"). So a few of these are "can't tell yet," not "yes."

| Layer | Fine? | Why |
|---|---|---|
| **Tracking** | **No — leading suspect, not confirmed** | Consent-banner swap ~5 weeks ago sits almost exactly inside your 6-week drift window. That's a real mechanism (consent-gated tag firing, modeled-vs-observed conversion drift), but you haven't yet run the one check that would confirm it. |
| **Structure** | **Can't tell yet — but this is the pattern's other best fit** | "CPA drifted up steadily, no single break day" is this skill's own textbook signature for fragmentation/erosion, not for a typical tracking break. You have the data to check this and haven't pulled it yet. |
| **Targeting** | **Can't tell yet** | Needs per-campaign CPM/frequency trend. You have campaign-level access — just not pulled. |
| **Creative** | **Can't tell yet, and partly unresolvable right now** | Real creative-decay diagnosis needs per-ad CTR trend, which your portal blocks. Campaign-level aggregate CTR/CPM direction is a partial substitute you haven't pulled either. |
| **Bids/budget** | **Can't tell yet** | Needs the edit log (any bid/budget/target changes in the window) and the lost-impression-share split. Spend being flat rules out "we just have less money," nothing more. |

Nobody gets a clean "yes" today, because the Evidence Gate isn't cleared — see below. That's a real finding, not a non-answer.

---

### ROOT-CAUSE VERDICT — Arcline Software, 2026-09-12

```
platform(s)   : not specified (agency portal) | model: B2B
window        : last 6 weeks, gradual drift, no break date, vs prior period — lag-maturity/day-of-week matching unconfirmed
volume        : spend flat, CPA +45% → implies conversions down ~31% at constant spend | reconciliation: unreachable (CRM blocked)

decomposition : not run — you have campaign-level impressions/clicks/conversions, just haven't pulled CPM/CTR/CVR trend yet
localisation  : not run — campaign-level breakdown is available and unused; ad-set/ad breakdown blocked by portal

layer screen
  tracking            : unknown, leaning FAIL - consent-banner timing + mechanism fit; not settled, no tag-firing/modeled-ratio check run yet   [severity: high, confidence: low-medium]
  structure           : unknown, plausible - gradual no-break-date drift is this skill's reference pattern for fragmentation; not settled     [severity: medium-high, confidence: low]
  targeting           : unknown - per-campaign CPM/frequency trend not pulled                                                                 [severity: unknown, confidence: low]
  creative            : unknown, partly access-blocked - ad-level CTR trend unavailable; campaign aggregate CTR/CPM not pulled                [severity: unknown, confidence: low]
  bidding/budget      : unknown - edit log and lost-IS split not pulled                                                                       [severity: unknown, confidence: low]
  offer & downstream  : n/a this pass - can't route here without knowing which link (CPM/CTR/CVR) actually moved
  external            : n/a - diagnosis of exclusion, can't claim it while every internal layer is unknown

confidence    : low — Evidence Gate not cleared
verdict       : insufficient evidence for a single root cause. Two internally-consistent candidates are open — tracking
                degradation from the consent-banner change, and structural erosion/fragmentation — and campaign-level
                data you already have is the fastest way to tell them apart.
evidence      : (1) gradual, no-break-date drift matches this skill's own structure signature, not a typical tracking-break
                signature; (2) the consent-banner change sits ~5 weeks into a 6-week drift — plausible, not exact; (3) flat
                spend + CPA +45% looks identical whether conversions genuinely fell (structure/targeting) or were
                undercounted (tracking) — CPA alone can't distinguish these.
prediction    : not issued — no verdict to attach one to yet
re-check      : one full window after the two actions below are run and reported back
```

### Why this isn't "it's the consent banner"

You handed me that detail as an aside, and it's tempting to anchor on it — that's exactly the trap this skill's method exists to catch: the first story offered becomes the hypothesis everything gets fitted to. The timing is suggestive, not proof. The *shape* of your drift (gradual, no cliff) fits the fragmentation/erosion pattern at least as well as it fits a tracking break. Both stay open until you run the checks below.

### What's actually blocking a verdict (Evidence Gate)

- **Conversion volume unknown** — can't judge if the account even has enough monthly conversions for automated bidding to behave sanely (B2B reference point: ~15-30/campaign/month before signal gets thin).
- **No edit log** — can't rule out a bid/budget/target/optimization-event change resetting delivery mid-window.
- **No CRM reconciliation** — every finding here is capped at medium confidence at best until backend truth is reachable.
- **No ad-set/ad breakdown** — creative and fine-grained targeting can't be fully screened; this is a hard access gap, not a data-quality gap.

None of this needs new access to start closing — two of the four gaps are closeable with what you already have.

### Ranked next actions (efficiency, not cheapest)

1. **Tracking check — near-zero effort, do this first, no CRM needed.** Pull the platform's own modeled-vs-observed conversion split by day for the last 10-12 weeks (Google Ads exposes this directly; check your platform's consent-mode equivalent). Separately, use tag-manager/browser preview to confirm the conversion tag still fires correctly across the consent banner's new flow, and check the site's consent-grant rate before vs. after the swap if analytics shows it. This is rung 1 and can't be skipped or demoted — every other number in the account reads through it.
2. **Campaign-level breakdown-and-compare — near-zero effort, data you already have.** Pull daily impressions/clicks/cost/conversions per campaign for the drift window plus an equal prior window; compute CPM/CTR/CVR per campaign per week. Uniform rise across every campaign points at tracking/external; concentrated in specific campaigns points at structure/targeting. This single pull is what actually separates your two live candidates.
3. **Edit log — minutes.** List every bid, budget, target, or optimization-event change in the window, per campaign, and date each one against the drift.
4. **Ad-set/ad access — blocked, not deleted.** If #2 shows a concentrated (not uniform) pattern, ask the agency for a one-time raw export of just the affected campaign's ad sets/ads rather than the full account — a smaller, more fundable ask than "unblock the whole portal."
5. **CRM reconciliation — deleted for this pass, not demoted.** No access anywhere in scope this month. Keep it on the list: if the eventual answer is "optimizing to the wrong conversion event" (the single most common B2B root cause this skill tracks), the offline-outcome feedback loop is the fix that actually compounds, and it needs this data to exist at all.

Don't reach for budget or bid changes yet — spend is flat and every rung above bidding is still unscreened, so a bid/budget move right now would just add a learning-window reset on top of an unresolved measurement question.

### Handoff once #1 and #2 come back

- Tracking confirmed → hand fix to `mbfinotti/advertising-skills@ad-conversion-tracking`.
- Structure confirmed → hand consolidation plan to `mbfinotti/advertising-skills@ad-campaign-consolidation`.
- Creative flagged once ad-level access opens → `mbfinotti/advertising-skills@ad-creative-fatigue`.
- CRM access lands → re-run this diagnostic's reconciliation step before touching anything else; it changes the confidence on every layer above.