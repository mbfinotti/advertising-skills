# Hollowbeam — Grab Bag Routing

## (a) Meta 210 / GA4 150 / CRM 96 — none is lying 🔴 needs data access

Three different measurement systems, three different definitions of "conversion":

- **Meta (210)** — highest because it counts view-through conversions (up to 1-day) plus modeled/estimated conversions when Event Match Quality is weak. Post-iOS14.5, Meta over-attributes without a well-tuned Conversions API.
- **GA4 (150)** — session-based, click-only, no view-through by default. Undercounts vs. Meta due to consent-mode cookie loss, ITP/Safari attribution-window truncation, and any cross-domain gap between your landing page and demo/signup flow.
- **CRM (96)** — the only number that reflects real, deduplicated, human leads. Lowest because it strips spam, duplicates, bounced/invalid form submits, internal tests — but also loses leads to broken UTM passthrough on multi-step forms and lead-sync lag.

**Verdict:** trust CRM directionally for revenue impact, but the 210→96 drop is two separate problems, not one: platform overcounting *and* CRM undercounting. Don't average or pick a winner.

**Route:** this needs a lead-level email match across Meta Events Manager, GA4 DebugView, and CRM lead-source field for one week's cohort — I don't have live access to Meta Ads or your CRM in this session (only GA4/GSC/Posthog/Ahrefs are your standing MCP setup, and none are connected here). Hand this to whoever owns the CRM export: pull last week's leads, tag each as matched-to-Meta / matched-to-GA4 / neither, and you'll see exactly which stage is leaking.

## (b) Three video openers — 🔴 blocked, can't watch files not in this session

I don't have the three cuts — they're not in this repo/session, and per your own sandbox rule I should ask rather than assume file locations. Send me the paths or clips and I'll give a read.

Independent of that: a personal opinion on 4 seconds of hook is weak evidence next to real audience data. Recommend instead:

1. Run a 3-way split test on the platform the demo will actually run on (Meta/LinkedIn), $50–100/variant, same targeting, same rest-of-video.
2. Measure **hook rate** — 3-second plays ÷ impressions (Meta) or avg. % viewed at 3s (LinkedIn/YouTube) — not completion rate.
3. Call it once each variant clears ~5–10k impressions.
4. If timeline doesn't allow a test, score each opener against: problem stated in first 2 words, product UI visible by second 2, no logo/intro card, readable sound-off (text overlay).

## (c) One newsletter, one podcast — 🟢 done

- **Newsletter: Demand Curve** (weekly). Tactical performance-marketing/paid-acquisition tests and channel shifts, no industry gossip — closest fit to a dev-tools paid-media budget.
- **Podcast: Marketing Against the Grain** (HubSpot, Kipp Bodnar & Kieran Flanagan, weekly, ~45 min). Covers platform/algorithm changes and B2B spend allocation directly, skips consumer-brand fluff.

Budget: 15 min reading + 1 episode/week. That's a bounded commitment, not a feed to monitor — drop anything else that isn't one of these two.

## (d) AI shopping-assistant sponsored slot — 🟢 done (needs product specifics filled in)

I don't know which assistant (shopping-copilot vs. a devtools-directory AI answer bot) or its char/word limit, so three variants at decreasing length — drop in the real product name/differentiator/metric:

**Long (~45 words, factual-lead):**
> Sponsored. [Product] is a [category] tool for [ICP], used by [N] teams to [core outcome]. Typical result: [concrete metric, e.g. "40% fewer failed deploys in 90 days"]. Free tier available; no credit card required. [Link]

**Comparison-style (~35 words):**
> Sponsored. Looking for [category]? [Product] does [core job] without [common pain point competitors have]. [Proof point/metric]. Try it free: [link].

**Proof-point-led, shortest (~20 words):**
> Sponsored. [Product]: [core outcome] in [timeframe]. [N] teams switched from [common alternative]. [Link].

Rules applied: plain declarative sentences (AI answer engines down-rank hype adjectives), one factual claim with a number, explicit "Sponsored" disclosure, single CTA. No skill in your current set targets paid AI-answer-slot copy specifically (copywriting-hooks explicitly excludes ad copy) — this was written from general GEO/AEO principles, so sanity-check the disclosure wording against that specific platform's ad policy before submitting.