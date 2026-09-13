## 1. Splitting ads by spouse via CTV household graphs

Mostly no, not on the TV screen itself — but yes, adjacently, if you have both names.

**Why CTV can't do it directly:** Roku, Samsung Ads, Vizio/Inscape, Comcast/FreeWheel — their audience graphs resolve to _household_ (IP, device ID, ACR data), not the individual sitting on the couch. One shared TV, one ad slot, no way to know which spouse is watching. Any vendor pitching "target the husband vs. the wife on the same Roku" is overselling what ACR data actually resolves.

**Where it _is_ real:** Identity-resolution platforms (LiveRamp RampID, The Trade Desk UID2, Experian) can split a household into individuals — but only if you feed them separate identifiers per spouse (two names + two emails/phones from your CRM or quote forms). Once matched, you can serve differentiated creative on each spouse's _personal_ devices — mobile display, Meta, Google — not the shared TV. So "household graph" targeting is really "cross-device graph off a shared address," and it only works as well as your first-party data.

**Why I'd skip it for you specifically:**

- Programmatic identity match typically needs minimum audience sizes (several thousand matched users) to avoid CPM penalties and thin-audience suppression — a regional installer's local market likely won't clear that economically.
- You probably don't have two-name records for most households today (most CRMs capture one contact per job).
- Build cost and minimum test spend ($5–10K/mo range) buys you a segmentation trick, not incremental $14K jobs, until proven.

**What actually solves your problem cheaper:** one ad, two messages, aimed at the household screen. Since your reviews already show the pattern — one spouse researches, one spouse fears getting locked in — write creative that answers both in 15 seconds: comparison/efficiency numbers for the researcher, "fixed-price, no-pressure, cancel-anytime consult" language for the contract-wary one. That's a copywriting fix, not a targeting-infrastructure fix, and it reaches both spouses on the same screen without needing to resolve who's who.

If you _do_ start capturing both spouses' contact info at the quote-request stage, retargeting each on their own phone/inbox with tailored follow-up (financing calculator to one, no-obligation-quote reassurance to the other) is cheap and worth doing — that's email/SMS/retargeting, not a CTV buy.

## 2. Same mapping for the $89 tune-up?

No.

A duct-cleaning tune-up is a single-decision-maker, low-consideration purchase — whoever manages home maintenance books it, usually without a household debate. The CAC from any identity-resolution or dual-persona campaign infrastructure won't pencil out against an $89 ticket; you'd be spending replacement-level acquisition cost on a maintenance-level product.

Better use of the tune-up offer: treat it as the _top of funnel_ for the $14K decision, not a parallel funnel needing its own persona mapping.

- Run it as a low-friction lead magnet — cheap entry point, gets a technician in the home.
- Retarget technician visit data: units flagged as aging/at-risk during a tune-up become your warmest replacement leads, and _that's_ where the two-persona system messaging kicks in.
- The in-home upsell moment (tech finds a failing unit) converts far better than any ad — make sure your techs are trained to hand off the "researcher" a spec sheet and the "risk-averse" spouse a plain-language, fixed-price quote on the spot.

One more thing worth doing before spending on any targeting build: mine those 220 reviews for the actual language each persona uses (efficiency ratings/financing terms vs. words like "locked in," "pressured," "fine print"). That gives you two ad copy variants and a call-script split for technicians — higher leverage than an identity-graph project, and it costs nothing but analysis time. Happy to do that pass if you share the review export.
