## Bottom line

Don't do this as described. What your consultant is proposing collapses exactly the splits this discipline says to protect, judged by exactly the metric that hides the damage. Here's the breakdown.

## Four things wrong with the plan as stated

**1. Brand and non-brand search sharing one bid pool.**
$9 vs $52 CPA is not a small gap, it's a canyon. Any automated bid strategy chases the cheapest conversions it can find. Brand search will eat the shared budget, non-brand growth will starve, and the blended number will look great while you go blind on the channel that actually finds new customers. This is a named, documented failure mode, not a hypothetical: pool only branches with comparable cost-per-conversion, or keep separate budgets with floors. Brand vs non-brand belongs in separate campaigns with distinct bid strategies regardless of what else you merge.

**2. Retargeting and prospecting sharing one bid pool.**
Same mechanism, worse gap: 8.4x vs 1.7x reported ROAS. Retargeting is scoring people who were already going to buy. Merge it with prospecting and the algorithm parks spend on warm converters, cold acquisition goes dark, and your reported account ROAS climbs while your actual customer pipeline shrinks. Platform-reported retargeting ROAS is commonly overstated relative to true incremental ROAS by 40-70% - it's measuring "who converted after seeing an ad," not "who converted _because of_ the ad." Blending it into one number makes that gap invisible instead of visible.

**3. It's a big-bang restructure, and big-bang is the one move this discipline rejects outright for a live account.**
Merging everything at once means every branch relearns simultaneously. When performance moves (and it will dip first), you won't be able to tell whether it was brand cannibalizing non-brand, retargeting cannibalizing prospecting, algorithm relearning noise, or a real structural win. You'll have one number and four plausible causes.

**4. Account-level ROAS after 30 days is the wrong judge, or at least an incomplete one.**
It's the metric a merged pool is specifically good at making look healthy regardless of what's actually happening underneath. Judge against your own pre-merge baseline per segment, not one blended post-merge number - and prefer an incrementality read (even a lightweight lift study) over platform-reported ROAS for the verdict, because platform ROAS is the platform grading its own homework.

## One more thing to flag

Google and Meta are separate platforms - you can't literally put Search and Meta line items into one campaign object; "merge everything" across both probably means "manage and judge them as one undifferentiated pool," which is the same problem at the account level instead of the campaign level, and arguably worse since it now also blends two totally different auction dynamics into one ROAS figure.

## What's probably actually true here

Some consolidation may genuinely be warranted - "too many campaigns" and "judge less granularly" aren't wrong instincts on $22K/month if you've got a pile of archaeological splits (old launch campaigns, a departed manager's structure, duplicate test campaigns nobody's touched in months). Those are cheap, safe merges. What's not warranted is merging _across_ the lines that map to different unit economics (brand/non-brand) or different funnel stages (prospecting/retargeting) - those splits exist for a reason, and the reason is visible in the very numbers you just gave me.

## What I'd want before recommending any specific merge

- Per-branch monthly conversion counts (not just CPA/ROAS) for brand, non-brand, prospecting, and retargeting, each on a lag-mature window
- Which of your 4+ branches are genuinely under-threshold vs. just under-reported
- Whether any branch is under-budgeted rather than under-volumed (a branch can look "small" just because it's starved of budget, not because its audience is small)
- Whether reporting splits (brand vs non-brand, prospecting vs retargeting) are something the business needs to keep visible regardless of budget structure

With that I can run the actual classification (merge / keep / keep-but-re-parent) branch by branch instead of judging the whole account with one blunt instrument. The likely shape of a real plan here is: prune any dead archaeological campaigns, consider `re-parent` (shared bid strategy, separate reporting) for genuinely similar-cost branches, and keep brand/non-brand and prospecting/retargeting structurally separate no matter what - full merge probably isn't the right rung for any of your four core segments given the cost gaps you've described.
