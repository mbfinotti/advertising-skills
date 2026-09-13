## Don't tighten the ladder. It's the ladder that's causing this.

Your diagnosis has the causality backwards. You're reading "abandonment climbed after we launched escalating discounts" as "people are cooling off faster, so hit them faster/harder." The much more likely read: **you've spent three months training a chunk of your customer base to abandon on purpose**, because abandoning now reliably produces a discount. Tightening the ladder doesn't fix that — it accelerates it.

### The mechanism

A cart abandoner who knows (or learns) that waiting gets them 10% tomorrow, 15% in a week, 20% in two weeks has a dominant strategy: **always abandon, always wait for at least the 10%.** Every cycle through this:

- More shoppers discover the pattern (return visitors remember it, coupon-code sites index it, browser extensions surface it at checkout).
- The trained segment grows, so raw abandonment rate rises — even if nothing about product-market fit or checkout friction changed at all.
- "Coupon ads convert great" stops being evidence the program works and becomes the smoking gun: of course a guaranteed, escalating, no-penalty discount converts well against people who already put the item in their cart. That's not incremental demand you created — it's margin you handed to demand that already existed.

74% → 79% over exactly the three months since launch, in a program specifically designed to reward abandoning, is the expected signature of discount-conditioning, not of colder leads. Making the first offer faster and bigger (your plan) shortens the training loop and raises the reward — it should make the metric you're worried about get worse, not better, and faster.

### What to check before changing anything (a week, not a quarter)

1. **Repeat vs. first-time abandonment rate.** If repeat customers/emails abandon at a meaningfully higher rate than first-timers, that's the game being played, not cooling interest.
2. **Time-to-purchase clustering.** Pull the distribution of "time from abandon to purchase" for converted abandoners. If you see spikes right at +24h, +7d, +14d instead of a smooth decay curve, people are waiting for the code, not forgetting and reconsidering.
3. **AOV and gross margin per recovered order, pre- vs. post-launch.** If AOV crept up (padding the cart to "make the discount worth it") while margin per order fell faster than the discount rate alone explains, that's cannibalization.
4. **A real holdout.** Take 15–20% of abandoners and give them zero discount — just a plain reminder. Compare their organic recovery rate and the net margin per abandoner (treated vs. holdout) after 30 days. This is the only way to know the ladder's _incremental_ lift instead of its gross conversion rate, which is currently lying to you.

### What to actually do

- **Freeze or widen the ladder, don't tighten it**, until the holdout test tells you the incremental effect. My prior: incremental lift is small and shrinking, and most of the "conversion" is redistribution of margin you didn't need to give up.
- **Gate eligibility, don't broadcast it.** Move from "everyone who abandons gets the sequence" to a suppression/targeting model: exclude customers who've redeemed an abandonment discount in the last 60–90 days, and only serve day-1 discount to segments with low predicted organic-recovery probability (new visitor, no email engagement, price-sensitive category). Let everyone else get a plain, non-discounted reminder first.
- **Break the predictability.** Fixed 10/15/20 at fixed days is exactly what gets memorized and gamed. If you keep a ladder at all, randomize timing and amount within a band, and cap total uses per customer so it can't be treated as a standing offer.
- **Change the metric you're optimizing.** "Coupon ad conversion rate" should be retired as a success metric. Replace it with incremental recovered revenue net of discount, from the holdout comparison. That's the number that tells you whether the program is making or losing you money.
- **Try a non-price first touch.** Urgency/social proof/stock-level reminder with no code, 2–4 hours after abandonment, before any discount enters the sequence. It costs no margin and won't teach anyone anything.

Net: the fix for "abandonment is climbing despite (because of) our discount ladder" is to make the discount less certain and less generous, not faster and bigger — and to actually measure incrementality before spending more margin chasing a number the program itself is inflating.
