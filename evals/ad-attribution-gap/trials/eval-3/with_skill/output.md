# Ferrostack Q2 LinkedIn Ads vs. CRM — Attribution Gap Reconciliation

## Bottom line

**The raw gap is 83%**: LinkedIn claims 4 of your 23 Q2 closed-won deals (17%), leaving 19 deals — roughly $760k of the $920k — with no LinkedIn credit in-platform.

But that 83% is not one thing, and it is not evidence LinkedIn "isn't working." Working backward from your own numbers, **an estimated ~74% of that gap (≈14 of the 19 uncredited deals) is a single, named, fixable mechanism: 62% of your Q2 leads never got a LinkedIn click ID saved to the lead record at all.** No attribution model — last-touch, multi-touch, U-shaped, anything — can credit a channel to a conversion it has no join key for. The remaining ~26% (≈5 deals) sits in a residual that needs one more data pull to classify, not a model swap, before anyone can call it explained. I could not push the explained share to a defensible number with the data given here — see "What's blocking a tighter number" below.

Your CMO's two moves both misread this:

- **"Last-touch shows it clearly, LinkedIn isn't working."** LinkedIn's in-platform number is self-reported credit, bounded from the start by whatever fraction of leads carry its click ID. At a 38% match rate, LinkedIn was structurally unable to see 62% of the leads behind these deals before any attribution logic ever ran. A report missing most of its join keys can't be read as a verdict on channel performance — it's a data-completeness problem wearing a performance number's clothes.
- **"Rerun everything under a different model to see if it looks better."** Reject this. Attribution-model choice only redistributes credit among conversions the platform can already see (i.e., leads that have a click ID). It does nothing for the 62% with no click ID — those aren't in the poolable set under _any_ model, last-touch or otherwise. Re-running the numbers specifically to find one that looks better is measurement-shopping, not measurement. If you want a model that treats LinkedIn's true influence more fairly on a long B2B cycle, that's a legitimate separate conversation (last-touch is known to under-count exactly this kind of channel, since most B2B buyers don't convert on a single click) — but it's a distinct decision from fixing the 62% capture hole, and doing it now would bury the fixable defect under a model-selection debate.

## How the 74/26 split was estimated

Two numbers you gave don't describe the same population, and that gap is itself informative:

- **38% of Q2 leads** have a click ID on file — a _lead-level_, Q2-cohort stat.
- **4 of 23 deals** were claimed by LinkedIn — a _deal-level_ stat for deals that _closed_ in Q2 (their leads may have been created months earlier, given a ~$40k ACV deal typically runs a multi-month cycle).

Applying the 38% capture rate to the 23-deal population as a rough proxy (flagging this as an approximation — it assumes click-ID presence doesn't correlate with which leads go on to close, which you can check directly): about 9 of the 23 deals would be expected to even have a click ID to join on. Only 4 were actually claimed. That splits the 19-deal gap into:

- **≈14 deals (74% of the gap): zero click ID captured.** Unclaimable by LinkedIn under any model, full stop, until capture is fixed. This is a capture defect, not a model artifact — 38% is far below the 75–85% match rate practitioners typically see on healthy B2B click-ID capture, and low enough to suspect an active problem (cookie loss, a redirect stripping the parameter, a form not saving the field on every variant) rather than an inevitable model-based writedown.
- **≈5 deals (26% of the gap): click ID present, still not claimed.** This is the part actually worth investigating with a real model/window conversation — LinkedIn's offline-import acceptance window may be shorter than your sales cycle, deals may be getting attributed to a contact who wasn't the one whose click carried the ID (LinkedIn credits accounts via the matched lead, and multi-person buying groups can break that link), or the import itself has a processing lag at the quarter edge.

## What's blocking a tighter number

I can't take this past a rough estimate, and won't dress it up as more precise than it is, without:

1. **Lead-creation dates for the 23 deals**, so the cohort is leads created (not deals closed) in the relevant window — a close-date pull like the one behind these 23 deals mixes cohorts LinkedIn saw at very different times, and structurally understates platform credit on long cycles regardless of any defect.
2. **Your actual B2B sales-cycle length** and **LinkedIn's current documented offline-conversion import window**, to check how many of the 19 uncredited deals fall outside the window on timing alone (a real, expected, non-fixable floor) versus inside it and still missed.
3. **Which of the 4 claimed deals** carry which revenue, so the $760k estimate above stops assuming average deal size.

With those three, this reconciliation would clear the 80% explained-share bar; without them, 74/26 is a directional estimate, not a closed number.

## What to do with this

- **Fix the click-ID capture gap first.** It's the highest-leverage, most fixable share of the gap (three-quarters of it, by this estimate), and it's an hour-to-days-scale fix (hidden form field, redirect audit, cookie/consent check) owned by whoever holds your lead-capture forms — not an engineering quarter and not a model debate.
- **Pull the lead-creation-date cohort next**, before anyone repeats "LinkedIn isn't working" as a conclusion. It may turn a chunk of the residual into an expected timing floor rather than a defect.
- **Keep the model conversation separate and later.** Once capture is fixed and the cohort is right, if LinkedIn's _credited_ number still reads low relative to what account-level, multi-touch reality suggests, that's the moment to talk about whether last-touch is the right lens for a multi-month deal cycle — as a deliberate choice with a stated reason, not as a way to make this quarter's number look better.
