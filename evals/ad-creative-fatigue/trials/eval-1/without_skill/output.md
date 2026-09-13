## Verdict: the fatigue read doesn't hold up — this looks like a budget-shock misdiagnosis

🔴 **Don't brief the replacement creative on this data yet.** The pattern points at the $600→$1,050/day step change (+75% in one move), not at hero-ad wear-out.

### Why fatigue doesn't fit

1. **Timing is wrong for fatigue.** Creative fatigue is a _gradual_ decay curve — CTR erodes over weeks as the same audience sees the ad repeatedly. What you have is a _step change_ that lines up exactly with day 11, the day you moved the budget. Five weeks of stable performance, then an overnight break — that's a delivery-mechanism signature, not a wear-out signature.

2. **All three creatives broke the same way, same day.** If the hero were specifically fatigued, you'd expect it to decline while the other two creatives (presumably fresher) held steady or declined less. Instead all three moved together — that's an **ad-set-level cause**, not a creative-level one. Fatigue is creative-specific; this isn't.

3. **The frequency jump is mechanically explained by the budget, not by fatigue.** Frequency went 1.8→2.6 (+44%) in the same 11 days you added 75% more daily spend. Meta has to serve more impressions, and if audience size didn't grow, it re-shows the same people more often to absorb the spend — that raises frequency independent of anything about the creative itself.

4. **+75% in one step is well past Meta's own threshold.** Meta explicitly flags budget/bid changes above ~20–30% as likely to reset the ad set into (or back into) the learning phase. A learning-phase re-entry produces exactly this symptom cluster: CPMs up, CTR down, CPA up, for 5–10 days (sometimes more if it doesn't relearn cleanly at the new spend level) — with **no creative change required to explain it**.

🎯 **Most likely mechanism:** the budget jump pushed the ad set back into learning and/or forced it to spend into a saturated slice of the audience at the old audience size, driving frequency up and efficiency down across the whole set — hero included.

### What to check before writing any brief (today, cheap, fast)

- ℹ️ Ads Manager → ad set delivery status: does it currently say "Learning" or "Learning Limited"? If yes, that alone explains the numbers.
- ℹ️ Pull **CPM** for the same before/after windows. If CPM rose sharply too (not just CTR falling), that's auction/delivery-side, reinforcing budget shock over fatigue.
- ℹ️ Check estimated audience size vs. daily reach at $1,050/day. If daily reach is chewing through a big share of the audience, frequency-driven saturation is mechanical, not creative-driven.

### The test that actually settles it (run this before/alongside briefing)

1. **Step the ad set budget back down** to ~$750/day (a ≤25% move from $600, inside Meta's safe-change threshold) rather than reverting all the way — you want to remove the shock without losing all the extra spend.
2. **Hold for 5–7 days**, let it exit learning, then compare CTR/CPA/frequency to baseline.
   - If hero (and the other two) recover close to pre-change levels → ✅ budget shock confirmed, fatigue not the driver. Hero can keep running; the lesson is to scale in ≤20–25% steps next time.
   - If hero stays weak while the audience/frequency numbers normalize → ✅ now you have a real fatigue read, isolated from the budget confound, and the brief is justified by data.
3. Target dates from today (2026-09-12): drop budget **today/tomorrow (9/12–9/13)**, read results **9/18–9/20**.

### Refresh plan — do this in parallel, not instead of the test

Killing the hero ad now, mid-diagnosis, means you lose your best cell and still won't know what actually broke. Better sequencing:

- **Brief the 2 UGC videos today anyway** — production lead time (creator sourcing, script, shoot, edit) is typically 1–2 weeks regardless of what the test shows, so there's no cost to starting now.
- **Launch them in a separate testing ad set** at modest budget ($100–150/day), _not_ folded into the scaled ad set — you don't want a second confound (new creative + budget-shocked ad set) stacked on top of the first.
- **Angle the two videos to complement, not duplicate, the hero's before/after static**: e.g. (1) a real-customer testimonial walking through first-30-days results, spoken to camera; (2) a day-in-the-life/unboxing hook that gets to the before/after payoff by mid-video. Different format (video vs. static) and different hook mechanics reduce audience overlap with hero, so they're additive rather than cannibalizing.
- Treat these as **new-creative tests**, scored against fresh baselines — not as "replacements" justified by a fatigue diagnosis that the data doesn't actually support yet.

### Bottom line for the growth-lead conversation

Say this: "The drop starts exactly on the budget-change date and hit all three creatives equally — that's the signature of a budget/learning-phase shock, not hero fatigue. I'm stepping the budget down to $750 to confirm over the next week, and briefing the two UGC videos in parallel so we lose no time either way." That gives them the creative refresh they want without burning your best-performing static on a misread.
