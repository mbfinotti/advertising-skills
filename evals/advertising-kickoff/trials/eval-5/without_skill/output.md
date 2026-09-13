Straight answer: I can't map your four tasks to specific skills, because there is no usable "advertising skills collection" available to me in this session or repo.

**What I checked:**

- The skills currently loaded for this session (via the `Skill` tool) — none are advertising/PPC-related (they're SEO/content/dev-tooling skills: `audit`, `dataviz`, `design`, etc.).
- This repo (`skills-affiliation`) itself — it's an affiliate-program tracker, not a skills collection. The only thing here that touches "advertising" as a topic is `research/2026-08-24-priority-skills-advertising-crm-sales.md`, which is a **third-party reference list** (other authors' skills.sh listings, e.g. `coreyhaines31/marketingskills`, `agricidaniel/claude-ads`, `claude-office-skills/google-ads-manager`) used internally for gap analysis when _scoping_ a future `advertising-skills` repo — it's not a finished, usable collection, and nothing in it specifically covers geo-holdout incrementality testing or a suspension appeal.
- The actual work-in-progress build of that `advertising-skills` repo lives under `skill-wip/` — which you told me not to read, search, or reference, so I have no visibility into what it will actually contain or whether it's finished.

So there's nothing I can honestly point you to as "skill X handles task Y" right now. If you want that mapping, either point me at the real skill collection (once it's outside skill-wip and installed/loaded), or lift the skill-wip restriction for this question.

What I _can_ give you, from general Google Ads/Meta Ads platform knowledge rather than any packaged skill:

1. **Hiking-boots keyword build-out** — pull Search Terms Report + Keyword Planner for the category, layer exact/phrase match on proven terms, keep broad match only under Smart Bidding with a tight negative list, and mine competitor/category modifiers (waterproof, mens/womens, wide-width, trail vs. hiking vs. backpacking boots).
2. **Geo-holdout incrementality test** — design a matched-market geo experiment (Google Ads Geo Experiments or a manual GeoLift/CausalImpact setup): split DMAs/regions into test vs. holdout, hold spend at zero in holdout for 4-6+ weeks, compare incremental conversions via a pre-period matched baseline, not just last-click attribution.
3. **Suspended account ("circumventing systems")** — this policy is usually tied to detected duplicate/related accounts, payment/billing mismatches, or automated rule/bid activity flagged as system manipulation; file through the in-account appeal form (not a new account — that risks a permanent ban), and the appeal needs concrete evidence there's no other linked account or automation violating policy.
4. **400 disapproved Merchant Center items** — pull the Diagnostics tab or Content API `productstatuses.list`, bucket disapprovals by reason (GTIN/MPN mismatch, price/availability mismatch vs. landing page, missing required attributes, image policy), and fix at the feed-rule/supplemental-feed level rather than one SKU at a time since 400 items usually collapse into 3-5 root causes.
