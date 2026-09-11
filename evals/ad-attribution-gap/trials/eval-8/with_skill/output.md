## The short answer

Don't present it as reconciled, and don't switch source-of-truth to Google Ads. Both moves fail for the same underlying reason: an ad platform is reporting *claims*, your order system is reporting *money received*, and closing that gap to zero (or handing the CMO's platform-flattering number the "source of truth" label) launders 470 conversions you can't currently account for into a number that looks clean because it's fabricated, not because it's understood. A board that later discovers the "reconciled" number wasn't will trust every number after it less than if you'd shown 66.7% explained on day one.

Here's the reasoning, then the packet to actually bring to the board.

---

## 1. Why "fully reconciled" is the wrong call

A financial reconciliation ties to $0.00. An attribution reconciliation never does — Google Ads and your order system are structurally counting different things (click-based vs. money-based, view-through included vs. not, modeled vs. deterministic). A gap that resolves to exactly zero after "adjustments" is evidence someone forced it there, not evidence the systems agree.

Run the actual numbers: 940 / 1,410 = **66.7% explained**. The bar for calling a residual "acceptable and stop investigating" is ~80% explained *plus* the residual being stable, direction-consistent, and not resembling a known failure mode. You're at 67%, and you're telling me you haven't yet tested the 470 against the standard checklist of causes — you said "can't explain yet," not "checked every known mechanism and it's genuinely inert." That's not a residual yet. It's an unfinished investigation wearing a residual's clothes.

Presenting it as fully reconciled also creates a specific, board-visible failure mode: next quarter, someone reruns the numbers, the "clean" tie-out doesn't reproduce, and now the story isn't "attribution is messy, as expected" — it's "the first data hire's numbers didn't hold up." The honest version is durable. The fabricated version has a shelf life of one quarter.

## 2. Why Google Ads shouldn't become the source of truth

Push back on this specifically, because "Google has the most complete data" is the platform's own marketing claim, not a property of the data:

- **Google Ads counts claims, not money.** It has no visibility into refunds, cancellations, chargebacks, or whether the order ever actually shipped. Your order system is the only system in this conversation that reconciles to revenue recognized.
- **"Most complete" is true and misleading in the same sentence.** Google is complete about *what Google can see*: its own clicks, its own view-through window, its own modeled/estimated conversions for users it lost to consent or tracking prevention. It has zero visibility into what any other channel contributed, and every platform's attribution is self-crediting by design — this is true of Meta, TikTok, etc. too, not a Google-specific flaw. Standardizing reporting on any single platform's counts means every other channel's contribution silently disappears from the story you tell yourself.
- **The 4.1 ROAS is built on the inflated number.** If 1,410 of Google's claimed conversions don't match orders, the revenue attached to those conversions is doing the same inflating to the ROAS figure. You cannot use a number as your headline metric while simultaneously treating its denominator as unreliable enough to need a 1,410-unit reconciliation.

The fix isn't "distrust Google Ads instead" — platform data is genuinely useful for in-platform bid optimization, that's what it's built for. The fix is: **order system anchors every board and finance number; Google Ads numbers stay labeled as an in-platform, non-incremental signal.** That's not a compromise position, it's the standard the skill this analysis follows is built around, and it's defensible in the room if the CMO pushes back (see talking points below).

## 3. What to do with the two weeks you have

You have enough runway to close real ground on the 470, not enough to run a holdout test (needs a full test period) or stand up self-reported attribution (needs a period to accrue after setup). Spend the two weeks on analyst-hours-scale decomposition instead — this is exactly the work a reconciliation is supposed to do before anyone calls a number a residual:

**Re-check the 940 first.** Before touching the 470, make sure the 940 is actually correctly bucketed and not itself hiding overlap or misclassification — "window differences, view-through, refunds" is three lines, but each should have its own quantified amount with a direction check (does this cause push Google's count *up* vs. orders? view-through and window-open-late do; refunds unwound by the order system but not Google also does). If any of the 940 double-counts the same conversions under two labels, your explained share is actually lower than 66.7%, not higher.

**Walk the 470 against the standard checklist, ranked by what's fastest to check and most likely to be non-trivial in a B2C ecommerce funnel:**

| Check (near-zero to hours of effort) | What it would show |
|---|---|
| Ratio check: is 1,410 / your quarterly order count above ~1.5x? | If yes, strongly suggests double-counting somewhere in the residual, not spread evenly across "small stuff" |
| Test/internal orders polluting the order system | Anchor pollution is the analyst's own to fix, no other team needed |
| Duplicate Google Ads tag firing (e.g. on the order-confirmation page reloading or a SPA re-firing the tag) | Single most common B2C cause of platform-high gaps, and an hour-scale fix once found |
| Browser vs. server event dedup (shared order-ID / event-ID between pixel and any server-side conversion send) | Missing or mismatched IDs double-count the same purchase |
| Modeled/estimated conversions Google added for consent-blocked users, not separately labeled from deterministic ones | If Google's UI conflates observed and modeled counts, that's a real, nameable definitional line, not a mystery |
| "Every" vs "one" conversion-per-click counting rule in Google Ads settings | A repeat-purchase click misfiring as multiple conversions is checkable directly in platform settings |

Each of these has a direction: all of them push Google's count *above* the order system's, same direction as your observed gap, so each is a legitimate candidate — you're not casting around randomly.

**Also run the MER cross-check now, in parallel — it's cheap and it's independent evidence for the board slide:** total revenue ÷ actual billed ad spend, both from your own systems, no attribution model involved. If MER looks healthy while the per-platform ROAS is inflated, that's a second, harder-to-dispute data point that platform-reported ROAS is overstating things — useful precisely because the CMO can't wave it away as "attribution model disagreement."

Realistically, expect this to move the explained share meaningfully (duplicate tags and dedup failures are the most common B2C cause and often explain a large single chunk), but don't force it to 100%. If you're still short of 80% in two weeks, say so — an honest 70-75% with named exclusions is a stronger board position than a fake 100%, and it's a stronger position than where you are today.

## 4. The board packet

Structure it as a reconciliation, not a single ROAS slide:

**Headline** — Anchor: order system. Anchor's number: [your order count, net revenue for the quarter]. Verdict on the Google Ads pair: "gap is [X]% explained, defect investigation in progress on the remainder" — not "reconciled."

**Normalization basis** — one line each: date basis (order-event date vs. Google's click-interaction date), timezone, revenue basis (net, excluding tax/shipping/refunds), attribution window as currently configured in Google Ads settings (don't assume the default — read it), view-through included or excluded.

**Variance table** — one row per cause, in the shape from the worked example above: source pair | metric | amount | % of gross gap | bucket (timing/definitional/residual) | cause | direction check | evidence | owner | status. This is the artifact that turns "1,410 conversions off" from an alarming headline into a list of named, mostly-expected things.

**Residual statement** — "Gross gap: 1,410. Explained: 940 (66.7%). Residual under active investigation: 470 (33.3%), narrowing via [duplicate-tag audit / dedup check / anchor-pollution check], results by [date]." If you close some of the 470 before the meeting, restate the percentage — don't silently fold newly-explained units into the original 940 line without updating the table.

**Defects and handoffs** — if the tag/dedup checks surface an actual bug, name it, quantify its share, assign an owner (likely your web/eng team), and route the fix there. Reconciliation work stops at "here's what's broken and how much it's worth" — the fix itself isn't this analysis's job.

**Known deltas to carry forward** — the point of doing this once well: next quarter's reconciliation starts from "Google Ads runs ~X% high on view-through + window, ~Y% on refunds not unwound" as documented, expected deltas, not as a fresh alarm.

## 5. Talking points for the CMO conversation

- "Google's data being complete *about Google* isn't the same as complete about the business — it has no visibility into refunds, cancellations, or what any other channel contributed. Every platform reports in a way that flatters itself; that's not a Google flaw, it's true of all of them, which is exactly why we don't let any one of them be the scorekeeper."
- "A 1,410-conversion gap isn't a red flag on its own — it's normal for these two systems to disagree. What matters is whether we can name where it comes from. We can name 67% of it right now, and I want two more weeks to push that further before I put a number in front of the board that I can't defend if someone asks 'what's in this figure.'"
- "I'd rather show the board a real number with a documented gap than a clean number I can't stand behind next quarter."
- Propose the forward operating model explicitly: **order system for the board and finance figure, Google Ads for in-platform bid optimization, this reconciliation re-run every quarter so the "known deltas" section — not a fresh panic — is what greets next quarter's numbers.** That's a stronger position for a first data hire to plant than "which single platform do we trust," because it's the one that survives audit.