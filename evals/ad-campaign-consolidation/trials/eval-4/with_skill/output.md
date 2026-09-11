## Sanity check: don't run this plan as written

The plan stacks three learning-resetting actions into one weekend, deletes the rollback path, and times all of it to land mid-relearn during your highest-value week. Each piece individually breaks a rule from the consolidation skill; together they're close to a worst case.

### What's wrong, mapped to why

**1. "Edit the 3 keepers in place" — this is the core mistake.**
Editing targeting *and* switching the optimisation event inside a live campaign resets its learning phase (both are named triggers, separately). You're not doing one edit, you're doing two, on the same entity, at once. Build the 3 target structures **fresh** — new campaigns/ad sets with the new targeting and the purchase objective — and shift budget into them. Never edit a live winner in place when you can build alongside it.

**2. Switching add-to-cart → purchase is the riskiest single change here, and you're doing it days before your biggest week.**
That's a real optimisation win in principle — purchase is a stronger signal than ATC — but it also means the algorithm starts relearning against a threshold (~50 optimisation events per ad set per rolling 7 days on Meta) *on the purchase event specifically*. Do you know each of these 3 campaigns' **purchase**-conversion volume (not ATC volume) clears that bar? If not, you're gambling that a thin signal exits learning fast, during Black Friday, with no fallback. This is the one change in the plan that most belongs *weeks* before a peak, not days before it.

**3. "Move 100% of the budget over on Sunday" — this is a big-bang move disguised as a phase.**
The skill's own budget-migration step: shift in steps of ~20% every 3–5 days, not 100% in one move. A full jump maximises the relearning dip exactly when auction prices and volume peak.

**4. "Delete the other 5 on Monday" — do not do this.**
Pause, never delete. Deletion destroys the learning history and reporting you'd need to (a) roll back if the new structure underperforms and (b) prove the consolidation actually worked. Pausing costs nothing and keeps your only rollback path alive.

**5. Timing, stacked on top of all of the above.**
"Next weekend" from Nov 15 is ~5–9 days before Black Friday — nowhere near the 7–14 day floor a merged/re-optimised campaign needs to stabilise, let alone the 14–30 days for a real read. You'd be asking freshly-relearning campaigns to carry your peak week, with the old campaigns already deleted so there's no control and no way back if delivery goes sideways on Black Friday itself.

### What's missing before this can be signed off

The skill requires this before any `merge` classification is valid, and none of it is in your message:
- **Why these 3 and not the other 5?** Deliberate splits (different product lines, prospecting vs. retargeting, geography) need preserve rules, not deletion. "Archaeological" splits (old tests, launch leftovers) are the ones actually safe to fold in.
- **Per-branch conversion volume on the *purchase* event**, over a lag-mature window — this is what the whole plan hinges on and it's absent.
- Whether any of the 8 protect something structural (retargeting vs. prospecting pools especially — collapsing those right before Black Friday is how retargeting eats the budget while reported ROAS looks great and net-new reach quietly dies).

### What I'd actually do instead, given the deadline

1. **This week:** pull purchase-event volume per campaign for the last 4–6 weeks. Confirm the 3 keepers can plausibly clear ~50 purchase events/7 days once merged. Confirm why the 5 losers were split out in the first place — 10 minutes with whoever built the account.
2. **Do the optimisation-event switch now, not next weekend.** If purchase volume looks viable, flipping ATC→purchase on the 3 keepers *this week* gives them a week-plus of relearning before Black Friday instead of days. If volume looks thin, don't flip it at all until after Black Friday — let ATC carry the peak and revisit post-BF.
3. **Build the 3 target campaigns fresh** with the new targeting, rather than editing in place.
4. **Shift budget in ~20% steps**, watching each keeper's delivery, not one 100% jump.
5. **Pause the 5, don't delete them.** Keep them at reduced/zero budget as your rollback and control through Black Friday weekend. Revisit deletion in December once the new structure has a full read.
6. **If purchase volume can't support this in time, don't force it before Black Friday.** Run Black Friday on the existing 8 (maybe pruning only the ones nobody can justify, budget shifted in steps), and do the real consolidation + event switch in the slower weeks after, with a proper no-touch window.

Bottom line: the destination (3 well-fed purchase-optimised campaigns) is probably right. The sequence — edit-in-place, 100% budget jump, delete, all inside one weekend, right before Black Friday — is the part that will get this reverted on day three, likely during your biggest sales day. Slow the mechanics down; you don't need to slow down the timeline as much as you think if you start the optimisation-event switch now instead of next weekend.