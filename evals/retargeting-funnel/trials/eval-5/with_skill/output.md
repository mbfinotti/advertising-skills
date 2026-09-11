Short version: **there's no cap field to set.** On Meta, the impression/frequency-cap control only exists on Reach and Brand Awareness objectives — it isn't exposed on Sales (conversion) campaigns like this one. So "what frequency cap should I set" doesn't have an Ads Manager field to type a number into here. What you actually control is a **cap-proxy**: a frequency reading you act on, backed by decay signals, plus audience size and creative rotation (those are the real levers on a conversion objective).

**Cap-proxy for this ad set:**
- Watch: frequency 2–4/week
- Warning: 4–6/week → this is where you add creative or start trimming
- Act: >6/week → rotate creative and/or cut spend, don't wait for it to climb further

(Meta retargeting generally tolerates 5–7/week before fatigue; practitioner data shows CTR roughly halving between frequency ~2 and ~5, and cost-per-purchase ~2x baseline by frequency 7.)

**Where you are:** frequency 9, CTR down 39% (1.8%→1.1%), CPM up 36% ($14→$19). Both decay triggers (CTR −15-20%+, CPM +10%+) are already blown past — this isn't approaching the cap, it's well into "act," already burned.

**Why it happened:** it's not really a missing cap number — it's a 3,200-person pool running **one** creative. A small warm audience with a single ad is, functionally, an uncapped frequency machine: everyone in the pool sees the same video over and over because there's nothing else in rotation for delivery to serve.

**What to actually do right now:**
1. Set your going-forward proxy at 4 (intervene) / 6 (hard stop or rotate) per 7-day rolling frequency, checked weekly.
2. Get at least 2 more distinct creative concepts into this ad set — 3+ concepts is the floor for any retargeting stage this small; one video against 3,200 people has nowhere to go but stale.
3. Don't fix the live ad by editing it — on Meta that resets the Sales-objective learning phase. Launch the new creative as new ads alongside it, and let the fatigued one wind down or pause it.
4. If budget lets you, cut spend on this ad set for a few days while the new creative comes online, so frequency decays before you push more impressions into an already-fatigued pool.
5. Re-check in 7 days against the 4/6 proxy bands, not against 9 — 9 is the number that tells you it's already too late this time, not the threshold to reset to.

One more thing worth flagging since it wasn't part of the question: at 3,200 people this is a single warm pool, not staged — if this is your only retargeting audience, exclude converters from it explicitly if you haven't already, since a 3,200-person warm-visitor pool re-serving buyers is a separate way frequency gets wasted on people who can't convert again anytime soon.