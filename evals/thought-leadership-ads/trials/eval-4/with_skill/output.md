## Click-through decision for Marek's LinkedIn posts

**The core problem: Demand Gen and RevOps are arguing over an option that doesn't exist.** LinkedIn Thought Leader Ads — the product this has to run on, since it's sponsoring Marek's own organic posts under his identity — carries only Brand Awareness, Engagement, or Video Views objectives. There is no lead-gen form, no conversion objective, and critically: **no advertiser-supplied CTA button, headline, or URL field at all** (event posts are the one exception, irrelevant here). The advertiser cannot attach a "Book a demo" button to this ad no matter what anyone approves internally. A link exists in this format *only if it's physically present in the post itself* — Demand Gen's brief is asking for something the platform doesn't sell.

So this isn't "CTA vs. no CTA." It's a three-way menu, and the disagreement is really about which rung of it to use:

1. **Tracked link edited into the live post** — most attributable clicks, but requires Marek to reopen and edit an already-published post.
2. **Tracked link in a pinned first comment** — never touches the approved post; one ask, repeatable across all three posts and every future one.
3. **No link, declared in writing as a retargeting-pool builder** — zero ask, zero attributable clicks; the campaign is then judged on pool growth alone.

**Given "getting Marek to change anything already published takes weeks of nagging," option 1 is deleted, not demoted.** That's the skill's explicit rule: an executive who won't edit a live post doesn't drop to second place on a ranked list where someone revisits it in week 4 — it leaves the roster entirely, named as deleted, because it's an ask nobody here is willing or able to make against a six-week measurement gate. Ranking it #2 just means it silently never ships.

### Recommendation: pinned first comment, on all three posts, as the default

This is the option built for exactly this constraint. The ask to Marek is one comment on each post — not an edit, not a repost, nothing that touches his published feed — and it's the same ask you can reuse on every future post he approves, so you're not spending political capital you'll need again next quarter. Clicks are fully tracked with UTM parameters to the landing page, so Demand Gen gets a real, attributable link and RevOps gets its brand-lift vehicle without the team having to choose between them. Concretely:

- Landing URL: `https://quorindale.com/demo?utm_source=linkedin&utm_medium=paid-social&utm_campaign=marek-tla-q[X]&utm_content=[post-slug]` — one distinct `utm_content` per post so you can see which of the three is pulling weight.
- Comment copy, posted by Marek himself (not the brand page) within a day of each post's organic peak, once engagement has settled: something short and native, not an ad — e.g. "For anyone who wants to go deeper on this — [link]." Route the actual wording through your humanizer pass; this format dies fast on anything that reads like copy.
- Ask him once, ideally with auto-approval enabled for future sponsorships so this stops being a recurring negotiation.

### What to tell each side

- **Demand Gen:** the "Book a demo" button isn't on the table on this ad product, full stop — not a negotiation, a platform limitation. What you can get instead is a UTM-tagged link in Marek's own pinned comment, fully trackable, on all three posts. That's the ceiling here without asking Marek for something he'll resist for weeks.
- **RevOps:** "no link at all" is the fallback for when you truly can't get any ask honored — it's not the first move just because the native CTA is off the table. A pinned comment costs Marek almost nothing and still buys you attributable clicks *and* the brand-lift exposure you want. If you go with no link anyway, it has to be a written, declared choice ("this post is a retargeting-pool builder, not a click campaign") — a post with no link and no such declaration is a documented failure mode, not a minimalist choice, and you lose the ability to run the standard cost-per-landing-page-click gate entirely.

### Measurement consequence of this choice

With the pinned-comment link in place, the week-6 gate runs as designed: cost per landing-page click against your brand-account baseline (or a provisional $3–5 bar if none exists yet), plus the engager retargeting pool crossing the platform's serveable floor. If any of the three posts ends up with no link (RevOps overrides on one), flag that post explicitly as pool-growth-only in the plan — don't let it default silently into "no destination, no declared purpose," which is the one combination the skill calls out as an outright failure mode. Never score any of these on reported CTR either way — it's the one metric shown to correlate *negatively* with pipeline (rho = -0.170 in the largest published dataset), and an engagement objective's CTR denominator includes reactions/comments/shares, so it will always look great and mean nothing.

### Named deletion for the record

- **Tracked link edited into the live post** — deleted from the menu for all three posts, reason: political-capital cost (Marek requires weeks of nagging to touch a published post) against a six-week measurement window that can't absorb that delay. Revisit only if Marek's editing friction changes (e.g., he agrees to auto-approve edits going forward).

### Still open before this is launch-ready

This answers the click-through question specifically. Before spend goes live you still need, per the eligibility gate: Marek's written agreement (platform click-to-approve isn't a commercial agreement — needs term, spend cap, who may edit, revocation handling, disclosure), confirmation your retargeting audiences/conversion tracking are actually live (data not captured before launch is unrecoverable), and the budget-vs-audience frequency math sized to whatever list you're targeting. Happy to run through those next if useful.