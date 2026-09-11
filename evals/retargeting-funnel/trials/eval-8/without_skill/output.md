## Short answer

No — neither approach will hold up to a CFO who's already skeptical, and for good reason: both designs are correlational, and the specific pattern you're describing (huge reported ROAS, flat total revenue) is the textbook signature of **retargeting attribution bias**, not something a before/after chart or an OLS regression can distinguish from a real effect.

## Why the platform's 14x ROAS is already suspect

Retargeting by definition only serves people who already showed intent — site visitors, cart abandoners, trial starters. That population converts at a much higher baseline rate than cold traffic *with or without the ad*. The platform's attribution model (last-click or last-touch, usually with a generous 7–28 day window) credits the ad for every one of those 640 signups, including the ones who were coming back to finish signing up regardless. This is the single most common way retargeting looks incredible on-platform and does nothing to the top line — you're literally paying to take credit for organic conversions. The fact that total new revenue didn't move is a strong signal this is exactly what happened here (that, or a pull-forward effect — spend accelerated signups that would have happened next quarter anyway, which nets out to zero over two quarters).

## Why your two proposed methods won't fix this

**Before/after comparison**: has no counterfactual. Anything that changed between the two quarters — seasonality, pricing, a product launch, a competitor's outage, macro conditions, even your other marketing channels — is confounded with "we launched retargeting." A CFO's first question will be "how do you know it wasn't X?" and you won't have an answer.

**Regression of weekly signups on weekly spend**: looks more rigorous but has the same disease plus three more:
- **Reverse causality / endogeneity**: spend is usually set *in response to* expected or observed demand (you spend more in weeks you expect to convert well), so the correlation runs both ways.
- **Omitted variable bias**: anything moving both spend and signups over the quarter (seasonality, a blog post going viral, a pricing change) will show up as a spend effect.
- **Tiny sample, autocorrelated**: one quarter is ~13 weekly points. With autocorrelated time series and that few observations, you'll get a coefficient with a huge confidence interval — easy for a numerate CFO to reject as noise, and correctly so.

Neither method can separate "the ads caused this" from "the ads happened to run alongside this."

## What would actually convince her: an incrementality test

The only design that isolates causation is a **randomized holdout (incrementality/lift test)** — the standard the ad platforms themselves use internally, and the standard finance teams trust because it's the same logic as an A/B test.

**Design** (works well for a self-serve product like yours):
1. From your retargeting-eligible audience (site visitors / trial dropoffs / cart abandoners), randomly withhold a slice — typically 10–20% — from receiving retargeting ads. Meta and Google both support this natively ("Conversion Lift Study" / "PSA holdout") so the holdout group sees a public-service ad or nothing instead, keeping exposure otherwise identical.
2. Run it for at least one full sales cycle (long enough to cover your typical consideration-to-signup lag).
3. Compare **actual signup and revenue rate** between holdout and exposed groups — not platform-attributed conversions, your own product/billing data.
4. Incremental lift = (exposed conversion rate − holdout conversion rate) / holdout conversion rate. Incremental ROAS = incremental revenue attributable to that lift ÷ spend.

If your platform doesn't support a native holdout, fall back to a **geo-based experiment**: turn retargeting off in a matched set of regions/markets for the test period, compare revenue trend there to markets where it stays on (synthetic control if the geos aren't perfectly comparable). Weaker than a randomized audience holdout, but far more defensible than before/after, because at least you have a contemporaneous control group instead of a different time period.

**On statistical power**: do the sample-size math *before* running it. With a baseline signup rate and your traffic volume, compute the minimum detectable effect for, say, 80% power at 95% confidence — this is the number to bring to the CFO up front, because "we ran a test but it was underpowered to detect anything below 40% lift" is a common and embarrassing failure mode.

## What to bring to her

1. The holdout-test design and its statistical power calculation, before running it — this alone will show her you understand why the 14x number is unreliable, which buys credibility even before you have results.
2. The incremental lift and true incremental ROAS from the test, computed off your own revenue data, not the platform's dashboard.
3. An explicit note reconciling why platform ROAS and true incremental ROAS differ (the intent-targeting bias above) — she'll want to know you understand the gap, not just that you found one.

If you want, I can help design the exact holdout percentage and power calculation once you share your weekly retargeting-eligible audience size and baseline conversion rate.