## Bottom line

Don't double the budget yet. The current setup will optimize spend toward the wrong conversions and is likely undercounting the one that matters. Fix conversion tracking first, then scale.

## Three problems, in order of severity

**1. Five primary conversions with wildly different volumes = bidding chases the wrong one**

Smart Bidding optimizes toward whatever primary conversions exist, pooled together. Form Fill, Newsletter Signup, and Pricing Page View almost certainly outnumber Closed Won by 10-50x in volume. Given more signal from the cheap, high-frequency actions, the algorithm will effectively optimize toward newsletter signups and pricing page views — not revenue — even though you _intended_ to target Closed Won.

Fix: only Closed Won should be primary. Demote Form Fill, Demo Booked, Newsletter Signup, and Pricing Page View to **secondary** — they still get tracked and reported in a separate column, but they stop feeding the bidding algorithm and stop counting in your headline "Conversions" number.

**2. ~7 Closed Won/month is not enough data for Smart Bidding to work directly on Closed Won**

Google's own guidance is roughly 30+ conversions in a trailing 30-day window per campaign before Smart Bidding has enough signal to converge; below that it stays in a perpetual learning state — volatile CPCs, erratic spend, no real optimization. At 7/month account-wide, split across however many campaigns you run, no individual campaign gets close. Optimizing straight to Closed Won today means the algorithm is flying mostly blind.

Fix — a phased approach, not a single toggle:

- **Now:** bid toward Demo Booked as the primary target. It's the best available proxy for a $15k ACV deal — much lower funnel than Form Fill or Newsletter Signup, high enough volume to give Smart Bidding real signal, and a strong historical predictor of Closed Won.
- **In parallel:** keep importing Closed Won (as secondary) with **deal value**, not just a binary count, so you're building the value data you'll need later.
- **Later, once Closed Won hits ~30+/month** (or you're comfortable with more variance at lower volume): switch primary to Closed Won, ideally on Target ROAS using actual deal values rather than Target CPA on a flat count.

**3. 30-day click-through window is shorter than your sales cycle — you're losing Closed Won conversions**

If the average deal takes 45 days from click to close, any deal that took longer than 30 days won't get attributed back to the original click at all — Google Ads simply won't count it. Your true Closed Won volume from ads is probably higher than what you're seeing; the setup is silently throwing some of it away. This makes problem #2 worse, not just an accuracy issue.

Fix: extend the click-through conversion window to 60-90 days (90 is the max Google allows) to cover the full 45-day average cycle plus some tail. Also check that "days to import" / lookback settings on the Salesforce offline import match, or Closed Won deals won't reconcile even with a longer window.

## Smaller items

- **Counting = "Every" on Closed Won:** correct, keep it — each closed deal is a distinct value event.
- **Counting = "Every" on Form Fill/Newsletter Signup:** worth switching to "One" per conversion action if the same person can resubmit a form multiple times — otherwise these (now-secondary) metrics get inflated and are less useful for funnel diagnostics.
- **Enhanced conversions for leads:** if not already on, turn it on. It improves match rate between the Salesforce-imported Closed Won events and the original ad clicks, which directly helps the sparse-signal problem in #2.

## Sequencing before you double the budget

1. Demote everything but Closed Won to secondary.
2. Extend the click-through window to 60-90 days.
3. Switch the bidding target to Demo Booked (or Maximize Conversion Value using Demo Booked + Closed Won value, if you want to start blending toward revenue immediately).
4. Let it run 1-2 weeks to re-baseline on the corrected signal.
5. Then increase budget — and do it in steps (e.g., +25-30% every few days) rather than a single 2x jump, so Smart Bidding isn't forced into a new learning phase on top of a config change and a spend shock at the same time.

Doubling budget on the current setup would mainly buy you more pricing page views and newsletter signups at a higher cost, not more revenue.
