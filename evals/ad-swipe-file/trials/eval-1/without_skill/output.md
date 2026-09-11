## Before you touch a single library: three things in your plan will cost you data quality

**1. US-only country filter — you'll lose the early-warning signal.**
Ad transparency filters (Meta Ad Library, TikTok Commercial Content Library, Google Ads Transparency Center) show ads *targeted* to whatever country you pick. If a competitor's campaign includes the US, it'll surface under a US filter — so you won't miss anything currently live. But DTC brands routinely soft-launch new hooks/formats in cheaper-CPM test markets (Canada, UK, Australia) 2–4 weeks before rolling to the US. Filtering to US-only means you see the winner *after* it's already scaled, not while it's still in testing. ⚠️ Recommendation: run each competitor twice — once at "All countries" (or add CA/UK/AU) to catch test creative early, once at US to confirm what's actually live in your market. Tag which pass each ad came from.

**2. Tagging format + hook on first contact — you don't have a taxonomy yet.**
You can't consistently tag "hook" on ad #1 because you haven't seen ad #200 yet — you don't know your own categories. First-pass tagging on an unstable taxonomy means silent renaming and drift (ad #3 called "social proof," ad #80 that's the same pattern called "testimonial"), and you'll have to re-tag everything anyway once patterns emerge — the exact second pass you're trying to avoid. ⚠️ Recommendation: burn 30–45 minutes on a fast scan across all 12 competitors, jotting raw impressions only. Freeze a format list and a hook list from that scan. *Then* do the tagging pass against the fixed lists. This is faster than one pass done twice.

**3. "Spare personal login for one platform" — I need one clarification before I build this into the workflow.**
Which platform, and is it your own personal account or a separate/burner profile? This matters because:
- If it's your real personal identity logging into a platform to see gated ad-library detail (e.g., TikTok's Commercial Content Library requires an account to search) — fine, that's normal, but don't use an account tied to your identity/company if the platform surfaces "who viewed" signals to page admins on some tools.
- If the intent is to log in as a "customer" to see competitors' *retargeting/personalized* ads (not the public library) — that's a different, legitimate technique (simulating a shopper), but it should run on a clean/incognito profile with no history, not your personal account, or your existing browsing graph will skew what you're shown and you'll conflate "what's targeted at me" with "what's targeted at a fresh coffee shopper."
- If it means bypassing a login wall the platform put up specifically to gate data — check that platform's ToS first; some ad libraries restrict automated/bulk access even when login-gated for humans is fine.

Tell me the platform + account type and I'll fold the exact login step into that platform's section below. Everything else here is ready to run today.

---

## Platform setup (US DTC subscription — coffee)

**Meta Ad Library (Facebook + Instagram)** — your highest-priority library; this is where most DTC coffee subscription spend lives.
1. Go to the Ad Library, switch from "Issues, elections or politics" to **"All ads."**
2. Search each competitor by exact Page name (not brand keyword — you'll get false positives from resellers/affiliates). Confirm via the verified Page link, not just name match.
3. Set country to US for the "live now" pass; re-run at "All" for the early-signal pass (see flag #1).
4. Note: Meta only reliably shows **currently active** ads in the standard commercial library — once a competitor kills an ad, it drops out fast (no long historical archive like the political ads library has). **Screenshot or save the creative, don't just bookmark the link** — the link dies when the ad does.

**TikTok Commercial Content Library** — needed if any of your 12 run TikTok (likely, for a DTC subscription targeting a younger cohort).
1. Search by advertiser/business name; requires the login you flagged above for full search access in some flows — this is the one to clarify.
2. Same country-filter nuance as Meta.
3. TikTok ad video assets often download directly — grab the file, not just a thumbnail.

**Google Ads Transparency Center** — covers Search, Display, YouTube, Shopping. Lower priority for hook/format creative analysis (Search ads have limited creative range) but essential for **catching Shopping/PMax creative** and **YouTube pre-roll**, both relevant to a subscription product with an unboxing/ritual angle.
1. Search by advertiser domain, not name — more reliable match.
2. YouTube video ads: same rule, save the file.

**LinkedIn Ad Library** — skip unless any of the 12 run B2B/gifting/corporate-office angles. Low priority for consumer coffee subscriptions; don't spend today's time here.

**Pinterest / Snapchat** — no public commercial ad library equivalent to the above as of now; if any competitor is visibly active there, you'll need manual browsing (clean profile) rather than a transparency tool. Not part of today's setup.

---

## Tracking sheet (build this before you open the first library)

One master sheet, one row per ad, filterable — not 12 separate tabs. The whole value of this exercise is cross-competitor pattern-spotting, which a per-competitor tab structure kills.

Columns:
- `Competitor`
- `Platform`
- `Ad permalink` (Meta/TikTok library link — treat as ephemeral, see below)
- `Saved creative` (link to your own screenshot/video copy — this is the durable record, the platform link is not)
- `Date first seen`
- `Country pass` (US / All-countries-early-signal)
- `Format` (from your frozen taxonomy — see below)
- `Hook` (from your frozen taxonomy)
- `Offer/promo visible` (e.g., "$10 off first bag," "free shipping")
- `CTA`
- `Notes` (free text — visual style, talent type, music, anything that doesn't fit a column)

## Starter taxonomies (freeze after your scan pass, then use consistently)

**Format:** static image · carousel · single-video · UGC/testimonial video · founder-to-camera · unboxing/POV · review-screenshot collage · comparison chart · meme/text-post · ASMR (brew process, pour)

**Hook:** pain point (bad coffee/expensive café habit) · social proof/reviews · founder story · comparison-vs-competitor · discount/offer-led · curiosity/question · before-after (energy, ritual, savings) · scarcity/urgency · unboxing reveal · seasonal/trend-jack

Adjust both lists after the scan — coffee subscriptions skew heavily toward "ritual/routine" and "vs. Starbucks spend" hooks that a generic taxonomy won't capture; let the actual scan tell you what's there before you lock it.

## Cadence going forward

Standard commercial ad libraries mostly show what's *currently* live, with weak-to-no historical archive. Set a **weekly** re-check (same sheet, append new rows, flag `date first seen` = today for anything new) — anything less frequent and you'll miss short-lived creative tests entirely, which is often where the most interesting hooks show up before they get scaled into evergreen ads.