# Landing Page Audit — Veldscript Google Ads Landing Page

```
traffic        : Google Ads (search, presumed) | model: B2B legal-tech SaaS
goal           : not confirmed (demo/trial/contact-sales — unknown)
window         : "last month" (exact dates not given)
volume         : 41,000 sessions (GA4) | conversions: 236 (GA4) vs 412 (Google Ads) — not comparable, see below
volume floor   : cleared on raw counts (both readings clear ~1,000 sessions / ~30 conversions)
economics      : target CPA/ROAS not given — gap unknown
inputs         : ad creative: NOT received | analytics: partial (two headline totals only) | recordings: none | page: NOT received (URL never arrived)
```

## VERDICT

I can't verdict the page itself — the live URL and the ad were never actually included in this message, despite the stated intent to paste them, so none of the on-page checks (message match, above-the-fold, trust, form friction, speed, accessibility, policy, post-click path) can be run. What *is* checkable from the numbers you gave points at the click path and the measurement layer, not at page craft, and it has to be fixed before a page verdict would mean anything:

The 324/41,000 = 0.8% figure you've been reporting is not a real number. It averages a Google Ads platform count (412) with a GA4 on-site count (236) — two different measurement systems with different attribution windows and view-through rules, which this skill's own failure-mode list calls out by name as never combinable — and then divides that invalid average by a GA4 session count that matches neither source. That's two independent errors stacked on top of each other, not one. Stop reporting it as-is.

There's a second, more interesting thread worth pulling before touching any copy: every click routes through a tracking redirect (`go.veldscript.com`) before the page — and the page's headline personalization is keyed off `utm_term`. If that redirect drops or rewrites query parameters on the hop, two things break at once and would explain both symptoms you're seeing: (1) the dynamic headline silently falls back to its generic variant for real ad clickers — which you'd never notice by opening the page yourself, since typing the URL directly never carries `utm_term` or goes through the redirect either; and (2) GA4 loses the paid-source attribution on those sessions, undercounting conversions relative to Google Ads' own click-based count. This is a hypothesis, not a finding — it needs a real click-through test with the actual ad — but it's the single explanation that ties the "page looks great to me" observation, the dynamic-headline architecture, and the 412-vs-236 gap together, so it's first in line below.

## FIX NOW (ranked by efficiency; all three gate everything else)

**1. Verify click IDs and `utm_term` survive the `go.veldscript.com` redirect**
Click a real ad (or simulate the URL with a real `utm_term` value) and check, in the network tab, whether the redirect's response preserves the full query string and the Google click ID through to the landing page and into GA4/Google Ads tags.
`funnel step: click → land (and land → attributed conversion)` · `evidence: opinion (unverified — needs a live test)` · `source: practitioner consensus (redirect param-stripping is a known paid-traffic bug class)` · `severity: critical` · `effort: hours`

**2. Stop blending Google Ads and GA4 into one conversion number**
Report the two sources separately, each with its own consistent numerator/denominator. Right now the only internally consistent rate you can compute from what's given is the GA4 one: 236 / 41,000 = 0.58%. The Google Ads figure (412) needs Google Ads' own click count as its denominator, which hasn't been provided — request it before publishing a Google-Ads-side rate.
`funnel step: measurement (all steps are read through this)` · `evidence: observation (the practice and the source mismatch are directly stated)` · `source: practitioner consensus` · `severity: critical` · `effort: hours`

**3. Load the live page with a real `utm_term` from the actual ad and confirm the personalized headline renders — don't judge message match by opening the page directly**
Opening the page without ad parameters (as you did) can only ever show the fallback state; it cannot confirm or rule out a message-match failure for real ad traffic.
`funnel step: land → engage (message match)` · `evidence: opinion` · `source: practitioner consensus` · `severity: major` · `effort: hours`

## RULED OUT

None. The Interview's deadline, mandate (one-off recovery vs. compounding asset), effort ceiling, and page ownership were never obtained — see Could Not Check. Nothing is being deleted from a fix list that doesn't exist yet; re-run prioritisation once those answers land.

## TEST, DON'T GUESS

- Once fixes 1–2 land and a single trustworthy conversion number exists: if the redirect turns out *not* to be the cause of the personalization gap, test a static, ad-matched headline against the dynamic `utm_term` system — judged on land→engage rate on a reconciled data source. Plausible (the contractor-built system is unverified and unowned), but not evidenced enough to rip out yet.

## NOT A PROBLEM

- **Volume floor**: 41,000 sessions and both conversion readings (236, 412) individually clear the ~1,000-session / ~30-conversion floor — once the numerator is fixed, this page has enough traffic to support a real statistical read, not just first-principles judgment.
- **Existence of the redirect**: a branded tracking redirect (`go.veldscript.com`) is not itself a policy or trust problem — it's standard practice. The concern is narrowly whether parameters survive it, per fix 1, not that it exists.

## COULD NOT CHECK

- **The page itself** — no URL was received, so checks A–I of the heuristic review (verbal/visual/offer/geo match, above-the-fold, offer clarity, form friction, trust placement, speed, accessibility, policy risk, post-conversion path) were not run at all.
- **The ad** — no creative, copy, or target keyword/`utm_term` values were received, so the verbal/visual match axes and the specific personalization variants to test are unknown.
- **Device split and geo/language mix** — not provided; mobile-weighting and localization checks are untouched.
- **Target CPA/ROAS** — not provided; the size of any performance gap, and whether it needs a promoted (offer-clarity-scale) fix vs. an hour-scale one, is unknown.
- **Downstream truth for this B2B motion** — whether "conversion" here means a raw form fill or something quality-gated (MQL/SQL/pipeline) is unknown; this matters before touching form length.
- **Qualitative evidence** — no recordings, heatmaps, or verbatims supplied.
- **Prior tests/changes on this page** — unknown, including anything the departed contractor may have already tried.
- **Root cause of the 412-vs-236 gap** — competing explanations (attribution-window/view-through differences, which is normal between these two platforms, vs. parameter loss at the redirect, vs. a firing/dedup issue) remain open; fix 1 is what would distinguish them. If the redirect turns out to be intact and firing is confirmed correct, this becomes a handoff to conversion-tracking reconciliation rather than a page issue.

## RE-CHECK

- **Fix 1** (redirect param survival): predicted effect — if parameter loss was the cause, the GA4-vs-Google-Ads conversion gap narrows and GA4 correctly attributes more of these sessions to paid. Judge 2026-10-12 (one reporting cycle).
- **Fix 2** (stop blending sources): predicted effect — leadership reporting shows two labeled source-specific rates, no blended figure reappears. Judge at next monthly report, 2026-10-12.
- **Fix 3** (live personalization test): predicted effect — contingent on fix 1; if the fallback was serving to real clickers, verbal message match improves and land→engage rate rises once the underlying number is trustworthy enough to read. Judge 2026-10-12.

To actually run the page-level checks (A–I), send the live URL and the ad copy/creative as originally planned — this report will extend from there rather than restart.