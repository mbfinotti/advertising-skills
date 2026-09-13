# Grainhollow landing page — priority fix order

Ranked by what's cheapest to execute in the CMS (copy/image only), not by impact — two items carry outsized risk despite being cheap, flagged below.

## 1. Kill the "guaranteed to double your salary" claim — seconds, do it today

Single sentence edit in the hero. Income/earnings guarantees are FTC-regulated and violate Google Ads' misleading claims policy — this single line is a live account-suspension risk on your paid spend, not just a conversion issue. Replace with a specific, substantiated stat (real outcome %, sourced) or drop the numeric promise entirely.

## 2. Rewrite the headline to name the course — seconds

Match it to what the ad promised. This is a message-match problem: it hurts Quality Score / Ad Relevance (raises your CPCs) and spikes bounce because visitors can't confirm they landed in the right place. Pure text swap, no layout risk.

## 3. Turn off autoplay + sound on the hero video — one widget toggle, minutes

Most CMS video blocks (Vimeo/YouTube/native embeds) have an autoplay/mute toggle without touching code. Switch to a static poster image or click-to-play. Two wins for one edit: fixes the accessibility violation (autoplay-with-sound breaks WCAG 2.2.2) and, if that video/poster is your largest above-fold element, likely knocks real time off your 5.2s LCP — the closest thing to a speed fix you can do without a dev.

## 4. Disable the resetting countdown timer — seconds to remove/deactivate

"Converts well" isn't the same as "safe." A timer that resets every load is a textbook dark pattern — FTC and EU/UK regulators have actively pursued this pattern since 2023, and it's the kind of thing that gets ad accounts and landing pages flagged on review. If you have a real deadline (weekly cohort close, actual promo end), swap in a genuine non-resetting date via the widget's date field. If you don't have a real deadline, just remove the module — don't rebuild fake urgency.

## 5. Move testimonials above the fold — minutes, more clicks (drag/reorder + mobile check)

Drag the testimonial block up near the hero/CTA in the CMS. Slightly more effort than the others because you should preview it on mobile after moving it — footer content dropped into a hero area can break spacing. Still zero-code.

---

## Not in this list — you can't fix these, don't try

- **Mobile LCP 5.2s (c):** this is a page-speed/infra problem (server response, unoptimized assets, render-blocking JS) — no CMS content edit gets you under Google's 2.5s "good" threshold. Item 3 above is the only lever available to you; the rest requires someone who can touch code. Since mobile is 74% of spend, this is your biggest conversion leak — worth a real ask for one-time dev/agency budget, even a scoped freelance engagement, rather than accepting it as permanent.
- **14-field signup form (f):** same story — the form stack isn't yours to edit. This is very likely costing you more conversions than everything else on this list combined. Flag it as the top business case for getting _any_ dev resource, even a few hours' worth.

If you can only get budget approval for one outside engagement, ask for the form (f) first — it's usually the single biggest lever on a paid-search landing page, ahead of even LCP.
