Neither. Both options are based on a misreading of what Cost Per Result Goal actually does, and Bid Cap would likely make your results *worse*, not better.

**What Cost Per Result Goal actually controls**

It's a *campaign-level average target*, not a per-result ceiling. Meta's bidding system (this applies the same way under the older "cost cap" naming) optimizes toward hitting that average across all results in the campaign — it explicitly does **not** guarantee that every individual result stays under the number. Some purchases will cost more, some will cost less, and the system is allowed to bid above your goal on individual auctions if it believes it'll balance out elsewhere.

**Why your numbers don't show a bug**

Your campaign average is $29.50 against a $28 goal — that's about 5% over target. That's well within the normal range Meta's bidding aims for; it doesn't hold the average exactly at the goal, it hovers around it, sometimes a bit over, sometimes under, depending on auction competition day to day. A handful of individual purchases at $47 or $63 sitting inside that average is completely expected — high-value individual auction wins are diluted by cheaper ones elsewhere in the campaign. This isn't a glitch, it's the tool working as designed.

**Why a support ticket won't go anywhere**

Meta support will point you to the same documentation: Cost Per Result Goal is an average, not a per-conversion cap. There's no "broken" behavior to fix here, so a ticket will just cost you time.

**Why switching to Bid Cap at $28 is the wrong move, not the fix**

Bid Cap does something different and much blunter: it caps what you bid *into the auction itself*, not your average cost per result. Setting Bid Cap at the same number as your former cost goal ($28) will generally:

- Shrink your auction eligibility — you'll simply lose more auctions to competitors bidding higher, especially on your best-converting audiences.
- Reduce volume, often sharply, without proportionally improving average cost — because Bid Cap doesn't have the pacing/smoothing behavior Cost Per Result Goal has.
- Frequently *raise* your effective cost per result in practice, since the campaign now delivers into a narrower, sometimes lower-quality slice of inventory.

Bid Cap is the right tool when you have a hard, non-negotiable ceiling per auction and are willing to sacrifice volume for it — not when your goal is "keep the average near $28."

**What I'd actually do instead**

1. Leave Cost Per Result Goal in place — $29.50 vs a $28 goal is not a meaningful miss.
2. If $29.50 genuinely doesn't work for your margins, raise the goal modestly (e.g., to $30–32) rather than fighting the system down to $28 — a goal set too aggressively relative to real auction prices causes underdelivery and volatility, not better cost control.
3. If you want tighter cost consistency, look at increasing budget/stability rather than switching bid strategy — thin daily budgets and low result volume make per-result cost swing more since the smoothing needs volume to work.
4. Only consider Bid Cap if you specifically need a hard per-auction ceiling and are fine trading off scale for it — and if so, test it starting *above* $28, not at $28, since Bid Cap and Cost Per Result Goal aren't calibrated the same way against the same number.