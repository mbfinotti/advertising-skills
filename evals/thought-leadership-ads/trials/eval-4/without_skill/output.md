## Run them as LinkedIn Thought Leader Ads, not boosted posts

The conflict is false. LinkedIn's Thought Leader Ads (TLA) format sponsors an employee's *already-published* organic post while attaching the CTA button and destination URL as a separate ad-wrapper element — the underlying post is never touched, edited, or duplicated.

**Why this resolves both camps:**
- Marek's feed post stays exactly as published — no nagging, no re-approval cycle.
- Demand Gen gets a CTA button + UTM-tagged landing URL, because those live in the ad unit, not in the post.
- RevOps's "brand lift is the point" concern is a non-issue: the CTA is a small footer button under the creative, not a swap of the post for landing-page copy. Comments, likes, and reactions on the sponsored version still roll up to Marek's real post, so organic social proof and reach both survive.

**Setup, in order:**

1. **Get Marek's one-time opt-in.** TLA requires the individual to authorize sponsorship of their posts via LinkedIn's "My Company" tab → Thought Leader Ads settings (or the sponsoring admin sends a one-time consent request). This is a single toggle, not an edit to any post — worth flagging to him that way specifically, given how protective he is.
2. **In Campaign Manager**, create a Sponsored Content campaign, objective = Website Visits or Conversions (not Brand Awareness/Engagement — that objective strips the CTA).
3. **Select "Thought Leader Ad"** as the ad format and pick the three approved posts as source creative.
4. **Set the CTA button.** LinkedIn's Sponsored Content CTA library includes "Request Demo," which maps directly to your "Book a demo" ask — use it as-is rather than inventing custom button copy, which isn't supported.
5. **Set the destination URL** with your UTM parameters (source=linkedin, medium=paid-social, campaign=marek-tla-q3, content=post-id). This is the ad's landing URL field — fully independent of whatever link, if any, sits inside Marek's original post text.
6. **Conversion tracking**: attach the LinkedIn Insight Tag conversion event for "Demo Booked" to the campaign so RevOps still gets attribution data even though they didn't ask for it — free upside.

**One thing to settle before launch:** confirm your LinkedIn account actually has TLA enabled — it's opt-in per ad account and not available in every market/vertical yet. If it isn't, the fallback is a standard Direct Sponsored Content "dark post" using Marek's name/photo as authorized creative, which functionally achieves the same separation but needs a signed permission form from him rather than the in-product toggle — slower, so check TLA availability first.

**On RevOps's "no link at all" framing** — that was solving for a problem (editing Marek's post) that TLA already solves for free. There's no scenario left where you'd actually want zero CTA: the button doesn't cannibalize brand lift, and running with no link at all just throws away demo pipeline for no measurable gain in reach or engagement.