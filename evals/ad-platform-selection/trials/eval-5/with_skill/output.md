# Sanity check: Ferrostat — LinkedIn kill + all-in on search

**Verdict: don't do this. Both calls are built on the same failure mode this framework flags explicitly — reading attribution and test noise as a channel verdict. Reverse the kill, fix the measurement, then re-split the budget.**

## 1. The LinkedIn kill was premature, not a real verdict

Run the numbers against the B2B-professional-networks gate:

- **Spend rate**: $3K over 3 weeks ≈ $4,300/month pace — under the "don't run pipeline tests below ~$5,000/month" floor. This test was never funded to produce a real signal.
- **Duration**: 3 weeks vs. the ~3-month commitment norm for this family, and against a 4-month sales cycle. This is the textbook false-negative trap: _"a test shorter than the sales cycle reads as zero lift even when the channel works... never judge before one full cycle has elapsed."_ 3 weeks against a 4-month cycle is an extreme mismatch, not a marginal one.
- **Sample size**: 2 MQLs total. The realistic signal threshold for this family is 15-25 conversions/month. 2 leads over 3 weeks isn't a readable sample in either direction — it's noise.
- **What the number actually says**: $3,000 / 2 MQLs = $1,500 CPL, against a typical benchmark of ~$110. That's a real anomaly worth diagnosing (audience sized outside the 5,000-50,000 working range, weak creative, wrong titles) — but it's an execution signal, not evidence the channel is dead. You killed it on the wrong axis.

Economics were never the problem here, whatever your exact margin turns out to be (see gap below): at a $60K ACV, LinkedIn's LTV floor (~$10-15K) is cleared several times over, so this channel was never close to failing the affordability gate. It failed a test that was too small and too short to mean anything.

## 2. The search reallocation is built on the exact bias this framework warns about

_"Platform-reported attribution systematically over-credits capture channels and undercounts creation channels — last-click favors the channels people pass through when already ready to buy."_ That's precisely what "9 of 11 closed-won deals as last-click" is measuring. For a $60K ACV, 4-month, presumably-committee sale, the realistic path is: someone finds Ferrostat via LinkedIn/content/referral weeks or months earlier, then does one final high-intent branded Google search right before booking a demo. Last-click hands 100% of the credit to that final search and erases everything upstream — including the exact touch you just killed. Moving the whole budget to search on this evidence is the failure mode named directly in this framework: _"reading attribution artefacts as performance — over-crediting capture, then over-funding it."_

There's also an 11-deal sample size here — thin enough that "9 of 11" could reasonably read differently at 20 or 30 deals.

## 3. Structural risk in going 100% search regardless of attribution

Search's value ceiling is bounded by existing category search volume. "Industrial IoT monitoring" is a specialized, low-volume B2B search category by nature — plant managers and ops/maintenance buyers aren't typing generic high-volume queries. $20K/month may simply exceed what the auction can efficiently absorb: money either sits unspent, or gets forced into broader/lower-intent terms that push CPL up and quality down. Verify this with the $100 price-discovery step before committing the full $15-20K — don't assume the ceiling matches the budget.

## 4. Recommended fix

- **Reverse the kill.** Re-fund LinkedIn as a properly designed test: ≥$5,000/month (clears the floor), ~3-month commitment (aligned with the sales cycle), audience checked against the 5,000-50,000 working range before relaunch — the $1,500 CPL is worth a targeting/creative diagnosis first.
- **Split the $20K, don't zero anything out.** Suggested: **~$15K (75%) to search as primary** — capture was legitimately underfunded before, this part of the instinct is right — **~$5K (25%) to LinkedIn**, clearing its floor with room to spare. This is two channels, both cleanly above their own thresholds, not the five-way "$60-80/day, nothing learned" anti-pattern.
- **Fix measurement before judging either channel again.** Add self-reported attribution ("How did you hear about us?") to the demo/RFQ form now — one form field, cheap, and the direct antidote to the last-click bias. Read CRM first-touch alongside last-click for the next cycle. Never judge a creation channel (LinkedIn) on last-click alone.
- **Set real pass/fail this time**: cost per SQL/opportunity ≤ allowable CAC at a readable sample (15-25 conversions/month), over the full 3-month LinkedIn commitment, tracked against the 4-month cycle rather than judged at week 3.

## 5. What's missing to finish the math precisely

Gross margin, LTV/retention, and current blended CAC weren't given, so I can't hand you an exact allowable-CAC/payback figure. It doesn't change this verdict — at $60K ACV, LinkedIn's ~$110 CPL (or even a $1,500 troubled CPL) is nowhere near the affordability ceiling under any plausible industrial-IoT margin — but you'll want those numbers before locking the final split and the search test's real-test budget (3-5x target CPA per concept).
