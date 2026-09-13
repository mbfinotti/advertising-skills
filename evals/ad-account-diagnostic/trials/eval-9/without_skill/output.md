# Meta Ads Performance Audit — Juniper Wellness

## Bottom line up front

The premise driving this audit — "we're below benchmark, therefore the account is broken" — doesn't survive contact with your own data. Before you take a "fix list" to the board, you should know that the evidence you've given me points to a **stable, profitable account**, not a **broken** one. Presenting this as a crisis will cost you credibility the first time someone on the board asks "if it's broken, why hasn't it gotten worse in 12 months?"

Here's what the numbers actually say, and what I'd audit instead.

---

## 1. Why benchmark comparison is the wrong diagnostic tool here

A purchased "industry average" report is a weak instrument for judging one specific account, for reasons that have nothing to do with whether Juniper is doing well:

- **Attribution mismatch.** You don't know what attribution window/model the benchmark report used (7-day click, 1-day view, blended, platform-reported vs. verified). Meta's own reported ROAS is well known to overstate incrementality relative to blended/MMM numbers. If the benchmark's 3.5 is platform-reported and your 2.4 is also platform-reported, that's a like-for-like gap worth investigating — but you haven't confirmed that.
- **"Supplements" is not one business model.** The category mixes $20 one-time-purchase SKUs, $80 subscription stacks, quiz-funnel personalized regimens, and MLM-adjacent brands. AOV, subscription attach rate, and funnel depth all swing category-average ROAS by 2x or more. Averaging across that tells you almost nothing about a specific brand's ceiling.
- **CTR is objective-dependent, not just creative-dependent.** If you're optimizing for purchases (you almost certainly are), Meta deliberately serves ads to people it predicts will buy, not people who will click — that suppresses CTR by design. A 0.9% CTR on a purchase-optimized campaign is not comparable to a 1.6% benchmark unless you know the benchmark's campaign objective mix (traffic vs. engagement campaigns inflate CTR and mean nothing for revenue).
- **Survivorship and self-report bias.** Vendors who sell benchmark reports skew toward brands willing to share flattering numbers or toward their own client base. Treat "3.5 average ROAS" as a marketing claim, not a scientific baseline.

**Action item:** before this number touches a board slide, get the benchmark vendor's methodology (attribution window, objective mix, AOV range, sample size). If they won't share it, the 3.5 isn't a number, it's a rumor.

---

## 2. What your own data says, read correctly

**Profitability, not the benchmark, is the right yardstick.**

With 55% contribution margin, breakeven ROAS is:

```
Breakeven ROAS = 1 / contribution margin = 1 / 0.55 = 1.82
```

At a 2.4 ROAS, every $1 of ad spend returns $2.40 in revenue → $1.32 in contribution profit → **$0.32 of net contribution profit per dollar spent**, before overhead. That is a profitable, healthy contribution margin on ad spend. Nothing in "ROAS 2.4 vs. benchmark 3.5" changes that arithmetic. You are not bleeding money on this channel — you're making money on it, consistently.

**Platform ROAS vs. blended MER — the gap is small and stable, which is good news, not bad.**

- Meta-reported ROAS: 2.4
- Blended MER (all channels, all spend, no platform attribution inflation): 2.1
- Gap: ~13%

That's a modest, normal amount of platform over-claiming — not the 40–60% inflation you often see in accounts with broken tracking, heavy view-through attribution, or brand-search cannibalization. A large or widening gap would be a real red flag (Meta claiming credit for sales that would've happened anyway via brand search/organic). A small, _stable_ gap over 12 months suggests your measurement isn't the problem.

**12 months of flat performance is the strongest signal in this whole brief, and it cuts against "broken."**

- ROAS: 2.3–2.5 band, all year
- CTR: ~0.9%, all year
- MER: steady at 2.1
- No account changes

Real breakage produces _drift_, not _flatness_: creative fatigue shows up as declining CTR and rising frequency over weeks; audience saturation shows up as rising CPMs and falling ROAS as you scale; tracking breaks show up as sudden discontinuities (iOS updates, CAPI misconfigurations, pixel changes) correlated to a date. Twelve straight months of tight-banded stability across every metric is the signature of an account that has settled into an **equilibrium given its current budget, targeting, and creative mix** — not one that's decaying.

**The real story to bring to the board is stagnation risk, not failure.** A channel that hasn't moved in 12 months despite no changes is also a channel nobody has stress-tested. That's a legitimate finding — just a different one than "broken."

---

## 3. What I'd actually audit (the real fix list)

Reframe the audit from "why are we below benchmark" to "is this account budget-constrained or performance-constrained, and where's the real ceiling":

1. **Elasticity test — has anyone actually tried to scale spend?** Twelve months flat with no changes could mean the ceiling was found, or it could mean budget was never pushed hard enough to find it. Run a structured 20–30% spend-up test on your best-performing campaigns for 2–3 weeks and watch marginal ROAS. If ROAS holds near 2.4 as spend rises, you're leaving profitable growth on the table — that's a much bigger board story than a benchmark gap.
2. **Incrementality/holdout test.** Run a geo-holdout or PSA-style incrementality test to see what fraction of that 2.4 ROAS is truly incremental vs. brand-search/organic cannibalization. This tells you the _true_ return on the channel, independent of both Meta's and MER's assumptions.
3. **Funnel-stage mix audit.** Break down spend and ROAS by prospecting (cold) vs. retargeting (warm). A CTR/ROAS profile like yours is consistent with an account that's retargeting-heavy and prospecting-light — profitable but capped in reach. Check what % of spend is cold; if it's low, growth is available by expanding prospecting even at a lower per-campaign ROAS, since blended MER is what matters.
4. **Creative testing velocity.** Flat CTR for 12 months with "nothing changed" often means creative refresh cadence has stalled too. Check: how many new ad concepts launched per month, not just new copy/image variants of the same concept. Low velocity is fixable and is a legitimate, concrete board action item.
5. **Frequency and audience saturation.** Pull average frequency by campaign over the 12 months. If frequency has crept up while performance stayed flat, the algorithm may be quietly compensating (shifting budget to retargeting) and masking a prospecting-side problem.
6. **Attribution/reporting alignment.** Confirm Meta's reported ROAS, your MER calculation, and the benchmark report all use comparable windows and definitions before quoting any of them side by side again.
7. **Target-setting.** Replace "beat the benchmark" with a profit-based target derived from contribution margin and the company's actual CAC payback/LTV goals. That's the number that should govern whether 2.4 is "good" or "bad" — not a third-party average.

---

## 4. Suggested board narrative

Don't present this as "the account is broken, here's the fix list." Present it as:

> "Our Meta channel is stable and profitable — every dollar spent returns $0.32 in contribution profit after cost, consistently for a year, with no red flags in our attribution. The purchased benchmark comparison isn't a reliable yardstick because it doesn't control for attribution methodology, business model, or campaign objective. The real opportunity isn't 'fixing' underperformance — it's that we haven't tested this channel's ceiling in 12 months. We're proposing a structured set of tests (spend elasticity, incrementality, funnel mix, creative velocity) to find out whether 2.4 is our floor or our plateau."

That version is defensible under questioning, doesn't overclaim a crisis you can't substantiate, and gives the board a concrete, fundable next step instead of a list of "fixes" for an account that isn't actually failing.
