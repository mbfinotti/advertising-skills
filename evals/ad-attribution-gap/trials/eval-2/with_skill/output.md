## Quick answer first

No — 74% is not the number, and the way it's built is exactly the mistake this kind of reconciliation exists to catch. You summed three ad platforms' self-reported conversions (640 + 510 + 210 = 1,360) and compared that to a single deduplicated order count (780). Ad platforms never get summed against an anchor: each one claims credit for conversions it influenced, and those claims overlap heavily with each other. 1,360 isn't "1,360 orders the platforms saw that the order system missed" — it's three overlapping claims on a pool of 780 real orders. The 74% figure measures the size of the overlap, not an over-count rate.

The Google-specific number you flagged is the one worth escalating: 640 claimed vs. 330 Google-tagged orders is a 1.94x ratio. That crosses the ~1.5x heuristic where over-reporting stops looking like normal platform self-crediting and starts looking like double-counting or a dedup defect. That's the actual finding here — not the 74%.

Below is the reconciliation, in the report shape this is meant to ship in, with every number sourced to what you gave me and every gap in the data called out rather than guessed at.

---

## Reconciliation report — Bluewater Peak Supply, paid channels, last month

### 1. Headline

**Anchor: order system.** Anchor count: **780 paid-attributed orders.** (Anchor holds the money — platform-reported conversions are claims, not orders received.)

Verdicts:

- **Google Ads vs. orders: gap too large to call structural — flagged as a likely defect, pending investigation.** 640 claimed vs. 330 Google-tagged orders (1.94x, +94%).
- **Meta vs. orders: cannot be verdicted yet.** No Meta-tagged order count was given — only a combined non-Google total (see Open questions).
- **TikTok vs. orders: cannot be verdicted yet.** Same gap.
- **"1,360 vs. 780 = 74% over-reporting": invalid comparison.** Platforms summed against a deduplicated anchor. Retract this number from the report; it doesn't describe anything real.

### 2. Normalization basis

This is where a "quick sanity check" usually turns out to not be quick — none of the axes below were confirmed, and the Google ratio can't be called a defect with full confidence until they are. Recorded here as open, not assumed:

| Axis                                         | Status                                                                                                                                                                           |
| -------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Date basis (interaction-date vs. event-date) | Not confirmed — Google backdates to click date, order system presumably stamps on purchase date                                                                                  |
| Timezone                                     | Not confirmed                                                                                                                                                                    |
| Attribution window per platform              | Not confirmed — do not assume defaults, pull from each platform's own settings                                                                                                   |
| Click-through vs. view-through conversions   | Not confirmed — Google's 640 may include view-through, which the order system's click-ID match never sees                                                                        |
| Modeled vs. observed conversions             | Not confirmed — Google's consent-mode modeling can inflate the platform number over a deterministic order count                                                                  |
| Counting rule ("every" vs. "one" per click)  | Not confirmed                                                                                                                                                                    |
| Revenue basis                                | Not confirmed — assume net of tax/shipping/refunds unless told otherwise                                                                                                         |
| Lag maturity                                 | **Likely issue** — "last month" data pulled now may still have an open attribution window on the tail days, inflating the platform-side number relative to a settled order count |

None of this changes the headline math, but it does change how confidently you can call the Google gap a _defect_ rather than a _documented delta_ in the client write-up. Right now it's provisional.

### 3. Variance table

| Source pair                                     | Metric      | Amount           | % of gross gap | Bucket                         | Cause                                                                                                                                                                                   | Direction check        | Evidence           | Owner   | Status                                         |
| ----------------------------------------------- | ----------- | ---------------- | -------------- | ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | ------------------ | ------- | ---------------------------------------------- |
| Google Ads (640) vs. Google-tagged orders (330) | conversions | +310             | —              | **Residual, candidate defect** | Ratio 1.94x exceeds the ~1.5x double-counting heuristic; view-through, modeled conversions, and open attribution window are all candidate definitional/timing causes but none confirmed | platform high — passes | none collected yet | Analyst | **Investigate — see open questions**           |
| Meta (510) vs. orders                           | conversions | unknown          | —              | Unclassified                   | No Meta-tagged order figure exists to compare against                                                                                                                                   | n/a                    | none               | Analyst | **Blocked — need per-channel order breakdown** |
| TikTok (210) vs. orders                         | conversions | unknown          | —              | Unclassified                   | Same                                                                                                                                                                                    | n/a                    | none               | Analyst | **Blocked — need per-channel order breakdown** |
| Google + Meta + TikTok (1,360) vs. orders (780) | conversions | +580 (the "74%") | —              | **Not a valid comparison**     | Cross-platform self-crediting overlap — several platforms claim the same conversion                                                                                                     | n/a — invalid pairing  | —                  | Analyst | Retracted from report                          |

Non-Google paid orders (780 − 330 = **450**) is the only other real data point you have. Meta (510) and TikTok (210) individually claim more between them than that 450 total, but they can't be split out or ratio-checked individually without the order system's per-channel tagging — the 450 is a combined figure, and comparing either platform's raw number against it would repeat the same summing error at one level down.

### 4. Residual statement

- **Google vs. orders:** gross gap 310 (94% of anchor), explained share **0%** — nothing has been classified into timing or definitional yet because none of the normalization inputs are in hand. Residual is 100% of the gap by default, which fails the 80%-explained pass bar outright. This is provisional pending the checks below, not a final verdict.
- **Meta vs. orders, TikTok vs. orders:** cannot be computed. No anchor-side breakdown exists per channel.
- **Blended cross-check (MER):** total revenue ÷ total ad spend = $402k ÷ $96k = **4.19x**. A commonly cited (vendor-sourced, not a standard) benchmark is "around 5.0+," so this sits a bit under that reference point — directionally not alarming, but it's a blunt instrument: it says nothing about which platform is over-claiming, only that paid spend overall isn't wildly disconnected from total revenue. Don't use it to clear the Google-specific flag.

### 5. Defects and handoffs

| #   | Defect                                                   | Revenue/volume at stake                                                                           | Fix effort                                                                                                                                   | Position                                                                                                                                                    |
| --- | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Google Ads reporting 1.94x the Google-tagged order count | 310 conversions of ambiguous revenue impact (paid-attributed revenue per channel wasn't provided) | Hours: pull view-through/modeled breakdown from Google's own reporting, confirm attribution window setting, re-check after the window closes | **Top of the list** — cheapest possible checks, and the ratio is high enough that it's worth ruling out a dedup or duplicate-tag issue before anything else |

If the checks below don't explain the gap, this becomes a Bucket 3 residual and should be handed to a conversion-tracking specialist to check for duplicate Google Ads tag firing or a browser/server dedup failure — both are the standard explanations for a ratio this far past 1.5x.

### 6. Known deltas to carry forward

None yet — nothing here is confirmed enough to bank as an expected, recurring delta. Once the open questions below are answered, the Google definitional share (view-through + modeled + window) becomes the number you re-apply next month instead of re-alarming on it.

---

## What's actually blocking a clean answer

Three things, all fast to get:

1. **Google Ads: view-through share, modeled-conversion share, and the account's current attribution window setting**, pulled straight from Google's own reporting UI. This alone probably explains a meaningful chunk of the 1.94x.
2. **Order system: per-channel breakdown for Meta and TikTok** (same tagging logic that got you the 330 Google figure), not just the combined 450. Without it, Meta and TikTok can't be reconciled at all — right now you only know they're _not verified_, not that they're fine.
3. **Confirm the window is lag-mature** — if last month's data was pulled recently, Google's attribution window may still be open on the final days, which inflates the platform number relative to the order system's settled count. Re-pull after the window fully closes, or explicitly flag the tail days as immature.

## How to write this up for the client

Don't lead with a percentage. Lead with the correction and the one real flag:

> Paid channels aren't reconciled to a single "over-reporting" number this period — summing conversions across Google, Meta, and TikTok double-counts orders that more than one platform claims credit for, which is expected and not evidence of a problem on its own. The one figure that does warrant a closer look: Google Ads reports roughly 1.9x the orders our system attributes to Google-tagged traffic (640 vs. ~330), which is above the range normal cross-platform crediting differences typically produce. We're pulling Google's view-through/modeled conversion breakdown and checking for a possible tag or dedup issue before drawing a conclusion. Meta and TikTok can't be individually verified yet — we need channel-level order tagging to check them the same way; today we only have a combined non-Google total. Blended return (total revenue ÷ total ad spend) is 4.2x, which doesn't itself suggest overall paid performance is disconnected from revenue.

That framing does three things a client report needs: retracts the invalid 74%, hands them one concrete, sized flag instead of a vague "paid is over-reporting," and states plainly what still needs data rather than papering over it with a number that looks more finished than it is.
