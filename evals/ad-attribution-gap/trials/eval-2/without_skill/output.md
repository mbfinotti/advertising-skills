## Sanity check: the "74% over-reporting" framing is off

You can't get a valid over-reporting rate by summing three platforms' self-reported conversions and diffing against one order-system total. That arithmetic assumes each platform is reporting on a disjoint set of orders — it isn't. Here's why, and what to write instead.

### Why 640 + 510 + 210 ≠ a real "paid conversions" number

Each platform runs its **own** attribution model, independently, with no knowledge of what the others are doing:

- **Overlapping windows, not disjoint events.** If a customer sees a TikTok ad, later clicks a Meta ad, then clicks a Google ad and buys — Google, Meta, and TikTok can _all three_ claim that single order inside their own attribution window. Summing platform numbers doesn't give you total paid orders, it gives you total _claims_, with heavy double- and triple-counting baked in. This is expected behavior, not a bug — it's a structural property of siloed, self-reported attribution.
- **View-through and modeled conversions.** Google (and Meta) count people who never clicked at all — just saw the ad and converted later — plus statistically _modeled_ conversions to fill gaps from iOS ATT/consent-mode signal loss. Neither of those requires a matching click in your order system's tracking, so they inflate the platform number without any corresponding row for the order system to attribute.
- **Different attribution logic than your order system.** Your 780 almost certainly comes from a single-touch, deduplicated model (e.g., last non-direct click across _all_ channels, one order = one credited source). The platforms are each doing "any touch we saw, within our own window, gets full credit." Comparing a deduplicated ground-truth count against the sum of three inflated, overlapping self-reports isn't an apples-to-apples inflation rate — it's two different measurement systems.

So "paid is over-reporting by 74%" isn't defensible as written. What _is_ defensible: platform self-reported numbers are not additive and cannot be trusted as a combined total — full stop, independent of any specific percentage.

### The Google gap (640 vs ~330) is the one worth digging into

A ~2x gap on a single platform is larger than what cross-platform overlap alone typically explains, and it's worth isolating before you write anything. Check, in order:

1. **Click-through vs. view-through split** in Google Ads (Conversions → segment by attribution/interaction type). If a large chunk of the 640 is view-through, that alone can account for most of the gap.
2. **Modeled vs. observed conversions** — Google's UI shows this split. Modeled conversions (filling iOS/consent-mode gaps) can be 20–40%+ of reported volume for some accounts.
3. **Attribution window mismatch** — confirm Google's conversion window (often 30-day click / 1-day view by default) against whatever window your order system uses to tag "Google-attributed."
4. **Tracking leakage on your side** — gclid stripping by ad blockers/browsers, redirect chains dropping params, or a tagging bug could make the order system under-count Google specifically. Worth a quick UTM/gclid audit before you conclude it's 100% Google's inflation.

### Reframe the numbers for the client report

Lead with what's actually solid:

- **Blended paid CPA (defensible):** $96,000 / 780 orders = **~$123 per order**. This is the number to anchor the report on — it's grounded in your order system, not platform self-reports.
- **Blended ROAS caveat:** $402,000 revenue / $96,000 spend = 4.19x, but flag clearly that this is _total revenue over total spend_, not paid's isolated contribution — organic, direct, and email are mixed into that $402k too.
- **Platform numbers:** present them labeled explicitly as "platform-reported, self-attributed, not deduplicated across channels" — useful for relative trend/optimization signal within a single platform, not for a combined "total paid conversions" figure.

### Suggested client-facing paragraph

> Each ad platform (Google, Meta, TikTok) reports conversions using its own independent attribution model and window, with no deduplication against the others or against your order system. When a customer is exposed to more than one paid channel before purchasing, multiple platforms can claim credit for the same order — so platform-reported totals should not be summed to estimate total paid conversions. Your order management system, which attributes each order to a single source, recorded 780 paid-attributed orders last month, giving a blended cost per order of ~$123 ($96k spend / 780 orders). We're separately investigating a larger-than-expected gap between Google Ads' reported conversions (640) and Google-tagged orders in your order system (~330) — likely driven by view-through/modeled conversions on Google's side, and we're auditing tracking (gclid pass-through) on our side to rule out under-counting. We'll report back with a corrected, deduplicated view of paid channel performance once that's resolved.

### Next steps to get a real number

- Pull Google's click-through/view-through/modeled split for last month before finalizing the report.
- Run a UTM/gclid tagging audit to rule out order-system under-counting.
- If you want a genuinely deduplicated cross-channel figure, feed all three platforms' raw conversion exports into GA4 (or a similar cross-channel model) rather than trusting each platform's own dashboard — or run a holdout/geo incrementality test if the client wants to know paid's _causal_ lift rather than just attributed orders.
