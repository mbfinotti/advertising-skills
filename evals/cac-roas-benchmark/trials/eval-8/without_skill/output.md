## The 4.1 doesn't survive contact with your own order system

**The arithmetic is right, the inputs aren't.**

- Meta: $310,000 / $80,000 = 3.88 ROAS
- Google: $265,000 / $60,000 = 4.42 ROAS
- Sum: $575,000 / $140,000 = **4.11** — yes, that's how you got 4.1.

**The problem: platform-attributed revenue ($575K) is 47% higher than total store revenue ($390K).**

Two ad platforms, each running their own last-click/view-through attribution, are both claiming credit for a lot of the same conversions — someone sees a Meta ad, later clicks a Google ad, buys once; Meta counts the sale, Google counts the same sale. There's no dedup between platforms. So:

- $575K attributed vs. $390K actual net revenue = **$185K of phantom/double-counted revenue** — that's 32% of what the platforms are jointly claiming.
- This isn't a rounding issue or a gross-vs-net quirk. It means literally every dollar of November revenue would have to be ad-attributed, plus another $185K that doesn't exist, for both platforms' numbers to be simultaneously true.

## What the real ceiling looks like

Since you can't trust the summed numerator, use total revenue over total spend — a blended MER, not a ROAS (it also folds in organic/email/direct, so it's still an overestimate of paid efficiency, but it's a real ceiling):

- **MER = $390,000 / $140,000 = 2.79** — not 4.1.
- Breakeven MER at 42% contribution margin = 1 / 0.42 = **2.38**.
- Actual contribution profit for the month, whole business: 390,000 × 0.42 − 140,000 = **$23,800** (6.1% of revenue).

Compare that to what the 4.1 story implies: 575,000 × 0.42 − 140,000 = $101,500 in contribution profit. The gap between $23.8K real and $101.5K implied is the size of the mistake you're about to scale.

## Why this matters for the December decision

- You're sitting at 2.79 MER against a 2.38 breakeven — a margin of safety of about 0.4x, not the comfortable 1.7x headroom a 4.1 ROAS suggests.
- Pushing spend +30% (to ~$182K) assuming 4.1 economics could easily land you below breakeven once you account for: (a) the attribution overlap not shrinking, (b) diminishing returns as you scale spend, (c) other channels (organic/email/direct) not scaling with paid spend, so MER typically compresses as paid grows as a share of the mix.
- 3,800 new customers × $78 AOV ≈ $296K — i.e., new customers alone are ~76% of total revenue. Worth separately confirming this isn't itself inflated by discounting/attribution artifacts, but it's a secondary check, not today's blocker.

## What I'd do before approving the +30%

1. **Don't use summed platform ROAS as a scaling input, period.** Use MER (total revenue / total spend) as the top-line sanity metric going forward.
2. **Deduplicate attribution** — pull UTM/coupon-code-based or server-side (e.g. GA4/warehouse) attribution instead of trusting each platform's self-reported numbers, or at minimum cap combined attributed revenue at total store revenue.
3. **Run an incrementality read before scaling** — a geo holdout or a brief spend-down test on one platform — since neither platform's "attributed revenue" tells you what's incremental vs. what would've converted anyway (branded search/retargeting stealing credit for organic demand is common and would make true ROAS lower than even the 2.79 MER suggests).
4. **Reconcile this monthly**: platform-attributed sum vs. order-system net revenue, flag any month where the gap exceeds ~10-15%.

**Bottom line: real blended efficiency is ~2.79 MER against a 2.38 breakeven, not 4.1 ROAS. That's a thin cushion, not a green light for +30% spend.**