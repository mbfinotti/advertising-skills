# Channel Plan — Notchset, 2026-09-12

**Short answer: no.** LinkedIn Lead Gen Forms are priced for a $10K–15K+ LTV enterprise sale. Notchset is a $29/month self-serve tool. The gap isn't close — it's 30–40x. Put the $3,500/month into paid search instead, with a cheap review-site listing running alongside it.

## 1. Economics

| Input | Value |
|---|---|
| Price | $29/month |
| Gross margin | **Assumed 80%** (typical for a Chrome extension — near-zero COGS beyond payment processing/support). Not confirmed — flag this before finalizing, though see note below. |
| Monthly gross profit/customer | $29 × 0.80 = **$23.20** |
| Avg. tenure | 14 months (given) |
| Implied monthly churn | 1/14 ≈ 7.1% → monthly retention ≈ 92.9% |
| Implied **annual** retention | 0.929¹² ≈ **41%** |
| Allowable CAC (9-month discounted payback, mid-band) | 9 × $23.20 × 0.41 ≈ **$85** (range ~$60–115 across a 6–12 month discounted-payback target) |
| Raw payback at $85 CAC | 3.7 months — looks healthy |
| **Discounted** payback at $85 CAC | 3.7 / 0.41 ≈ **9 months** — the honest number |

**Why the discounted number matters here:** "14-month average tenure" sounds comfortable, but it's produced by a steep early churn curve — only ~41% of customers are still paying at month 12. A naive LTV calc ($29 × 14 = $406) overstates what you can afford to spend by roughly 2.4x. Use $85 as the working allowable CAC, not $400.

This conclusion is **not margin-sensitive**: even at 100% margin, LTV gross profit tops out near $400. The gate that kills LinkedIn below isn't close enough for the margin assumption to change the verdict.

## 2. Deleted channels

| Family | Gate failed | Specifics |
|---|---|---|
| **B2B professional networks (LinkedIn Lead Gen Forms)** | Affordability | Requires LTV ~$10,000–15,000 to recoup the CPL premium — Notchset's is ~$325–400. Typical CPL ~$110; even the platform's own "favorable case" ($20–60 per qualified lead) assumes a sales-qualification motion Notchset doesn't run at $29/mo, plus the ~$5,000/month floor this plan doesn't clear. Realistic CAC at cold-lead-to-self-serve-paid conversion rates lands at $370–2,200 — 4x to 26x your $85 ceiling. |
| **Connected TV** | Affordability + N/A | $23.20/month contribution can't clear $20–40 CPMs plus $1,500+ production; wrong buyer surface entirely. |
| **Podcast/audio** | Affordability | $3,500/month budget is 23% of the ~$15,000 measurability floor. |
| **Retail media** | Disqualifier (N/A) | Not sold on a marketplace. |

All four are out of the candidate set — not ranked low, gone.

## 3. Candidates ranked by efficiency — survivors only

| Rank | Family | Value subtotal | Effort subtotal | Value ÷ Effort |
|---|---|---|---|---|
| 1 | **Paid search** | 15 (presence 4, reachability 5, reach 3, measurability 3 — pending real keyword/tracking check) | 4 (creative burn 1, skill/coordination 2, reversibility 1) | **3.75** |

Evidence: recruiters actively search this category — "LinkedIn Recruiter alternative," "recruiter Chrome extension," competitor brand terms (ContactOut, Lusha, SignalHire, Wiza-type queries). That's real, pre-existing capture demand, unlike LinkedIn's cold-form interruption. Effort is near-zero: text ads plus a landing page, pausable in minutes — the right fit for a solo founder with no standing creative team.

**Price-discovery bucket (unranked, eligible as a parallel low-effort line, not the primary):**
- **Paid review listings (G2/Capterra)** — B2B buyers comparing recruiting tools mid-evaluation is exactly your intent pool. G2 Starter is $299/month flat; Capterra PPC floors at $500/month, $2/click minimum. Cheap enough to run *alongside* search from day one without starving it — it's a fixed listing, not a second auction competing for learning volume.

**Not ranked — insufficient input:** paid social prospecting and short-form video need Q9 (is the buyer reachable there specifically, not just "on LinkedIn"), Q11 (creative capacity), and Q7 (geography) answered before scoring. Don't add either until search validates.

## 4. Primary recommendation

**Paid search.** It's the only surviving family whose benchmark economics can plausibly clear an $85 allowable CAC, it matches existing category search demand, and it fits a solo founder's effort ceiling (a week of setup, no standing creative job). This is capture-first, per the framework's own logic: the category has search volume, capture is unfunded, so it goes first.

One caution, stated directly: your instinct toward LinkedIn comes from platform fluency, not from this math. That's the named failure mode this framework flags explicitly — "the channel the team knows" overriding the economics. Your LinkedIn expertise isn't wasted; it's just not this budget's job yet. It becomes relevant again if Notchset ever adds a $10K+/year team/enterprise tier.

## 5. Funding plan

Budget: $3,500/month.
- **Paid search: $2,800/month (80%)** — clears the ~10-clicks/day signal floor (~$1,620/month at the $5.42 all-industry avg CPC) with more than 2x headroom for price discovery and the real test.
- **G2 Starter listing: $299/month** — fixed cost, high-intent capture, doesn't compete with search for auction signal.
- **Buffer/reserve: ~$400/month** — held for scaling whichever channel validates first, not split into a third experiment.

## 6. Test design

1. **Price discovery**: ~$100 on exact-match category + competitor-brand terms to learn real CPC/CPL for this niche — published all-industry benchmarks ($5.42 CPC / $66.69 CPL) are not this niche's number.
2. **Real test**: $300–500 per concept (3–5x the ~$85–115 target CAC) over 2–4 weeks (standard search test window). Confirm actual sales cycle (unknown — assumed impulse-to-weeks given self-serve $29/mo pricing) before locking duration.
3. **Pass**: cost per paying customer ≤ ~$85–115 at 90–95% confidence.
4. **Kill**: $200–300 spent on a concept with zero paid conversions after a readable sample.

## 7. Second-channel trigger

Add G2/Capterra spend up or test paid social prospecting only once search saturates (rising CPA on impression-share limits) — not before, and never by re-splitting the $3,500 into simultaneous experiments.

## 8. Measurement approach

Default rung for a capture-heavy plan at this budget: UTM discipline + last-non-direct, plus one added field — "How did you hear about us?" at signup. Skip MER/incrementality; the spend isn't material enough yet to justify the build.

## What's unconfirmed and should be checked before you commit real budget

- **Gross margin** (assumed 80% — doesn't change the verdict, but confirm for the real CAC ceiling).
- **Landing page + conversion tracking readiness** (unverified — launching before this wastes the whole test).
- **Target geography** (assumed US/English — confirm before budgeting non-US CPCs).
- **Employment special-ad-category status**: worth a one-line policy check before any social spend — selling software *to* recruiters isn't the same as advertising a job *to* candidates, so this likely doesn't apply, but confirm before it strips targeting on a future campaign.