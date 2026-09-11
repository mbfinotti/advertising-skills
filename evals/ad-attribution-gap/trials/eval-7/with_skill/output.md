# Attribution Gap Reconciliation — Pinwheel Labs Signups (Analytics vs Billing)

## Direct answers

**Is the 12% gap normal?** ✅ Yes. A gap that is stable over a year, in the expected direction (analytics undercounting the money system), and decomposable into known mechanisms is the textbook definition of "normal" in attribution reconciliation. It needs monitoring, not fixing.

**Can you ship the 1.12x correction factor?** ❌ No. Don't institutionalize a static multiplier. It breaks the moment the gap's composition shifts even slightly — and you have live proof that it's shifting right now (the direct-channel jump). Below is why, and what to do instead.

---

## 1. Headline

Anchor: billing system (source of truth for money — same role an order/CRM system plays in any reconciliation; a PLG signup funnel run this like a self-serve B2C motion, with the billing record as the anchor rather than a CRM).

Anchor count: N signups per period per billing (exact figure not supplied).

Verdicts:

| Pair | Verdict |
|---|---|
| Analytics vs billing (total, 12% gap, 12+ months) | ✅ Structural and explained — normal |
| Analytics vs billing, channel mix (direct 31%→44%, last 2 months) | ⚠️ Residual under investigation — not yet a confirmed defect, not yet explained |
| Proposed "×1.12 correction factor" | ❌ Reject — see §5 |

## 2. Normalization basis (assumed, pending confirmation)

- **Grain:** monthly, consistent with "over a year" and "last two months" framing.
- **Anchor:** billing system signup/account-creation event, since that's what carries money and is what "signups vs billing" implies you're already comparing.
- **Conversion definition:** assumed a completed signup as recorded by billing (trial-start or account-created), vs. analytics' equivalent event. Confirm both sides fire on the *same* step (e.g. "created account" vs "started checkout" are different events and would manufacture part of the 12% on their own).
- **Date basis / timezone:** not supplied — if analytics event-timestamps and billing event-timestamps use different timezones or date-stamping rules, re-derive after aligning them before trusting the 12% figure at all.
- **What's not yet known:** whether the 12% is itself already net of any known adjustments, or a raw comparison. Treat it as raw until confirmed.

## 3. Variance table (qualitative — no export data available yet)

| Source pair | Metric | Direction | Bucket | Cause | Direction check | Status |
|---|---|---|---|---|---|---|
| Analytics vs billing | signups | analytics low ~12% | Definitional/Bucket 2 | Consent banners, tracking-prevention (ITP/ETP), ad-blockers on a dev-tools audience — this audience skews toward ad-blocker and privacy-tool usage above baseline | analytics low — passes | Plausible primary driver, needs consent-rate data to confirm size |
| Analytics vs billing | signups | analytics low | Bucket 1/Timing | Signups completed via API/CLI/server-side flows (common in dev tools) that never load a client-side analytics tag | analytics low — passes | Check whether any signup path bypasses the browser entirely |
| Analytics vs billing | signups | analytics low | Definitional/Bucket 2 | Cross-device/session gaps — signup started on one device, completed on another (e.g. email verification link opened elsewhere) | analytics low — passes | Plausible, unquantified |
| Analytics vs billing, **channel mix only** | direct share | +13pts (31%→44%) over 2 months, paid-social & organic-social down, **total flat** | **Bucket 3 — residual, channel-level** | Candidate causes below | mix shift with no total change — matches known pattern, not yet isolated to one mechanism | **Investigate** |

Channel-mix candidate causes, ranked by how well they fit the observed pattern (total-level gap unchanged, only mix moved):

- **Stripped tracking parameters.** Social platforms' own link wrappers, in-app browsers (LinkedIn, X/Twitter, TikTok), or a redirect/link-shortener change can drop UTM parameters, and traffic with no UTM/referrer defaults to "direct" in most analytics tools. Check whether paid-social and organic-social posting workflows changed in the last ~2 months (new scheduling tool, new landing-page redirect, new short-link domain).
- **AI-assistant referral traffic.** Traffic arriving via AI assistants (ChatGPT, Claude, Perplexity, etc.) typically carries no referrer and lands in "direct." For a dev-tools audience this is a live and growing channel — developers routinely ask an AI assistant for tool recommendations. This is directionally plausible but not something to assert without evidence; a growth newsletter's ~70%-no-referrer figure for AI-assistant traffic is illustrative, not a verified constant for your account.
- **Real behavior shift, ruled less likely.** If paid-social/organic-social traffic genuinely declined (algorithm change, reduced posting cadence, campaign pause), you'd expect *total* signups to move too. Total signups holding flat while only the mix moved is evidence against a pure real-demand explanation and in favor of a misattribution mechanism.

Diagnostic checks to isolate the cause (analyst-hours scale, no engineering needed to start):

1. Pull a sample of "direct" sessions from the last 2 months and inspect landing pages. If a disproportionate share land on pages that only ever get linked from social posts (a specific blog post, a specific feature page), that's stripped-parameter traffic, not real type-in direct.
2. Check referrer strings on that same sample for known AI-assistant user-agent or referrer patterns.
3. Audit whether paid-social and organic-social posts in the window carry UTM parameters consistently, and whether any new link-shortener, redirect, or campaign-scheduling tool was introduced around the inflection point.
4. Compare the timing of the inflection to any tagging/pixel/consent-banner change shipped in that window.

## 4. Residual statement

- **Total-level (Analytics vs billing):** 12% gap, stable 12+ months, direction consistent with known consent/cross-device/server-side mechanisms. Passes the judgment test (stable, expected direction, decomposable in principle even without exact per-cause quantification yet). Within the cited "analytics vs order/billing backend" normal band (roughly under ~25%) with real margin to spare — not close to the ~35% investigate line.
- **Channel-mix level:** unresolved residual, actively being monitored, not yet classified to a named mechanism. This is the one open item, and it sits *inside* the stable 12% total — proof that "the total looks fine" does not mean nothing is moving underneath.

## 5. Why the correction factor should not ship

A flat ×1.12 multiplier assumes the 12% is one static number caused by one static mix of reasons. Three things break that assumption:

- **It's compositional, not atomic.** The 12% is the sum of several causes (consent loss, server-side signups, cross-device gaps, and whatever channel-level misattribution is happening right now). Those causes drift independently. The total can hold at 12% while the internal mix moves — which is exactly what the direct-channel data show happening this quarter. A multiplier calibrated on last year's mix silently misrepresents a different mix next quarter, with no warning, because the *output* number still looks unchanged.
- **It multiplies channel-level numbers too.** If it's applied to "every dashboard," it gets applied to channel splits, not just the total. That means the direct/paid-social/organic-social distortion happening right now gets scaled up and baked into every downstream report as if it were real, durable channel performance — turning a temporary tracking artifact into a budget-allocation input.
- **It removes the detection mechanism that caught this.** The reconciliation process — the "tedious comparison" your manager wants to retire — is what surfaced the channel-mix shift in the first place. A static multiplier applied and then never re-checked would have let this drift accumulate for months before anyone noticed a channel budget decision was being made on bad data. Stopping the comparison removes exactly the instrument needed to catch the next version of this problem, including a future case where the *total* gap itself starts moving instead of staying flat.

What the skill's own failure-mode list calls this directly: "Measuring an average gap once and subtracting it forever as a fixed correction — consent rates and media mix shift the gap continuously. Re-derive it each period."

## 6. Recommendation — what to do instead

- **Don't apply a multiplier to analytics.** For any board- or budget-facing number (total signups, revenue), report off billing directly — it's already the anchor and the source of truth. Analytics stays the tool for behavioral and channel-mix insight, not a stand-in for billing.
- **Make the reconciliation cheaper, not gone.** The manager's real complaint is likely effort, not value. Turn the comparison into a lightweight recurring check (e.g., a monthly total-gap number plus a channel-mix drift check) instead of a full manual audit each time — automate the pull, keep a human eyeball on the trend line and any inflection.
- **Investigate the direct-channel spike now, as its own item**, separate from the 12% total-gap question. It's a live Bucket 3 candidate with a plausible, checkable cause (stripped params or AI-referral no-referrer traffic), and it's actionable this week at analyst-hours effort — no engineering required to start.
- **Carry the 12% forward as a documented, re-derived expectation**, not a fixed constant: re-check it each quarter, and treat any future *change* in the gap's size or direction as the actual trigger for investigation, exactly as you already correctly did with the channel-mix shift.