Don't restructure the account or touch creatives yet — the data you've given points almost entirely at the product-page template and price increase, not at ad fatigue or account structure.

**Why the timing rules out your plan**

- CPM flat, CTR flat, impression share stable → traffic quality and auction dynamics haven't changed. If creatives were fatiguing or the account structure were causing budget misallocation, you'd expect CTR to erode, CPMs to drift, or impression share to wobble as spend shifts around. None of that moved.
- CVR -41% starting exactly March 3, the same day the new product-page template and the 12% price increase shipped. Two changes landed on the same day, which is itself a problem (see below), but a same-day cliff in conversion rate with flat upstream metrics is the signature of something breaking or repelling users *after the click*, not a traffic or creative problem.
- Platform-reported purchases within 7% of your order system, consistent with baseline → rules out tracking breakage (pixel misfire, consent-mode changes, deduped/inflated platform reporting) as the explanation. The drop is real, not a measurement artifact.

Restructuring the account or refreshing creatives would burn time and budget addressing metrics that aren't broken, while the actual cause keeps suppressing every dollar you spend.

**What to check first, in order**

1. **Isolate template vs. price.** They shipped together, so right now you can't tell which one (or both) is responsible. Ask the web team if the template can be rolled back independently of the price, or if you can split-test old vs. new template at the current price for a few days. This is the single highest-value thing you can do this week.
2. **QA the new template like a user, on mobile and desktop.** Look for: broken or slow-loading add-to-cart button, layout shift pushing CTA below the fold, broken size/variant selectors, checkout/payment step regressions, page speed regression (Core Web Vitals), broken trust signals (reviews, shipping/returns info) that were present in the old template.
3. **Segment CVR by device and new vs. returning visitors.** A template bug often hits one device disproportionately (e.g., mobile layout broken, desktop fine) or hits new visitors harder if returning visitors have cached pages or different entry points.
4. **Segment CVR by landing page / product.** If price increase is the driver, expect the drop to correlate with price elasticity by product tier (cheaper desks hit harder than premium ones). If it's the template, expect it to correlate with which product pages actually got the new template first (rollout may not have been instant/uniform).
5. **Check for a checkout funnel step-by-step drop-off**, not just top-of-funnel CVR — pinpoint whether people are bouncing on the product page itself or dying later (cart, shipping calc, payment).
6. **Sanity-check the price increase against competitors and against your own historical price elasticity** if you have it from past increases.

**Bottom line:** this reads like a product-page/pricing regression, not a media-buying or creative problem. Fix or isolate the March 3 change first — restructuring the account now would be optimizing the wrong layer and could mask the real cause for weeks while still spending $80K/month at degraded CVR.