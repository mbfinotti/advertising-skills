## October MER — corrected for the TikTok gap

**Don't use the sheet's $0 for TikTok — it silently breaks the MER calc.** A missing token means TikTok spend is *unknown*, not *zero*. Plugging in $0 understates total spend, which mechanically inflates MER (spend is the denominator) and makes the month look better than it is.

### Two versions of October MER

| | Total spend | MER (Revenue ÷ Spend) |
|---|---|---|
| **As reported** (TikTok = $0) | $130,000 + $95,000 + $0 = **$225,000** | 520,000 / 225,000 = **2.31** |
| **Corrected** (TikTok imputed at its historical ~8% share) | $225,000 / 0.92 = **$244,565** (implies ~$19,565 TikTok spend) | 520,000 / 244,565 = **2.13** |

Math for the imputation: if TikTok is normally 8% of *total* spend, then Meta+Google make up the other 92%. So total spend = (Meta+Google) / 0.92, and TikTok's share is the difference.

### Is the downtrend real?

**Yes — and the reported 2.31 is actively hiding it.**

- Fitting a trend line through Apr–Sep (2.35, 2.31, 2.34, 2.30, 2.28, 2.26; slope ≈ −0.017/month) projects October at **~2.25**.
- The reported 2.31 breaks that trend upward — looks like a recovery. That's the tell that it's an accounting artifact, not a real signal: nothing changed operationally to cause a rebound, the analyst just removed a whole channel's cost from the denominator.
- The corrected 2.13 comes in **below** the trend projection, not just in line with it. That means October isn't merely continuing the slide — it's underperforming even the existing downtrend. Worth treating as a possible acceleration, not just noise, though one month isn't enough to confirm acceleration on its own.

### The part that actually matters: profitability, not just the ratio

Breakeven MER = 1 / contribution margin = 1 / 0.44 = **2.27**. Below that, ad spend isn't earning back its contribution margin.

- **September (2.26)** was already sitting right at/just under breakeven — the first month in your data to cross that line.
- **October reported (2.31)** would read as a bounce back to profitable.
- **October corrected (2.13)** is not just below breakeven, it's meaningfully further below than September was (−0.14 vs. −0.01). That's the real story: this isn't a wobble, it's two consecutive months below the profitability line, with October materially worse than September.

### Bottom line

The downtrend is real and October likely got worse, not better — the $0 TikTok entry is masking a second straight month of paid spend running below your contribution-margin breakeven, and by a wider margin than September.

### One fix before you finalize this

Don't rely on the 8% heuristic for the actual books — it's a reasonable stand-in for this analysis, but TikTok Ads Manager billing/invoices are a separate system from the reporting API and are normally still accessible even when the reporting token is dead. Pull actual spend from there to replace the estimate, especially since ad delivery may have kept running (or been paused) during the outage in a way that doesn't match the historical 8% average.