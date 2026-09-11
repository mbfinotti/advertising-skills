# Root-Cause Diagnostic — PetPal Box Paid Social, Q4 CPM/CPA

**Short answer: no, don't send that note as written.** The data you've given me contradicts the "industry-wide auction inflation" story rather than confirming it. This is a localized problem in one ad set, not a market-wide one. Sending the external framing to your CEO would be repeating the outgoing agency's unverified narrative, not confirming it.

## Why the story doesn't hold

The skill's discriminator for external vs. internal causes is the **uniformity test**: real auction-wide inflation (Q4 seasonality, category-wide competitor spend) hits every audience buying into the same auction pool roughly evenly. A cause concentrated in one branch of the account is not that.

Your own numbers fail that test hard:

| Ad set | CPM move | Signal |
|---|---|---|
| Main prospecting (narrow stacked-interest) | **+85%** | Frequency 2.1 → 4.8, unique reach flat for a month |
| Other four ad sets | **+2% to +6%** | — |

An 85% spike sitting next to four sibling ad sets moving 2–6% isn't "the auction went up" — if it were, all five would have moved together, because they're bidding in the same overall Meta auction during the same weeks. Instead, one specific audience is behaving completely differently from its neighbors.

The second piece of evidence points at exactly *why*: frequency climbing from 2.1 to 4.8 while unique reach has been flat for a month is the textbook signature of **audience saturation** — you've stopped reaching new people and are now just paying more to show the same shrinking pool of users the ad again and again. A "narrow, stacked-interest audience" is precisely the structure that runs out of new impressions first: stack enough interest layers and the addressable pool shrinks to the point where the algorithm is bidding against your own prior impressions to find anyone left. That's an internal targeting design problem, not a market condition.

The blended +34% CPM and the 30% CPA increase are consistent with this: CPM is the one link that moved (CPA tracks CPM almost 1:1 here, which suggests CTR/CVR held — no independent creative or landing-page collapse layered on top). The blended number is just the saturating ad set dragging the account average up; the other four ad sets show what the market is actually doing to you this quarter, and it's a mild 2–6%, not 34%.

## What I can't fully certify yet

Per the diagnostic standard I'm applying, a few things are still open before I'd call this "high confidence" instead of "medium":

- **Learning-phase / edit log**: was there a recent budget, bid, or audience edit to that ad set? A significant edit resets delivery and can itself produce a frequency/CPM spike that looks like saturation but is really a learning-phase reset. Need the dates.
- **CTR by ad set**: I only have CPM and frequency for the prospecting ad set, not CTR. If CTR is also falling there (not just CPM rising), that's a creative-decay signature layered on top of saturation, not saturation alone.
- **Conversion volume and tracking reconciliation**: I don't have conversion counts or a backend/CRM reconciliation check. If tracking is off, the CPA number itself isn't trustworthy yet, and everything above should be re-read once that's confirmed clean.
- **Exact windows**: "prior 60 days" needs to be lag-mature and matched day-of-week against the comparison period; recent days always under-report and can fake a bigger swing than is real.

None of these missing pieces change the headline finding (uniform-vs-concentrated is visible from the ad-set breakdown alone, independent of those gaps) — they'd only sharpen the mechanism and the confidence level.

## Verdict block

```
ROOT-CAUSE VERDICT - PetPal Box, 2026-09-12
platform(s)    : paid social | model: B2C
window         : current period vs prior 60 days (lag maturity: unconfirmed - need exact dates)
volume         : spend/conversions not provided | reconciliation gap: unverified (no backend check run)

decomposition  : CPA +30% tracks blended CPM +34% closely - CPM is the failing link, not CTR/CVR
localisation   : NOT uniform - concentrated in one ad set (+85% CPM) vs four siblings (+2% to +6%)

layer screen
  measurement/tracking : unknown - no backend/CRM reconciliation run yet                    [-, low]
  structure             : unknown - no overlap/campaign-count data provided                  [-, low]
  targeting              : FAIL - narrow stacked-interest audience saturating: frequency
                           2.1->4.8, unique reach flat 30 days, CPM +85% isolated to this
                           ad set while account's other audiences hold at +2-6%              [high, medium]
  creative               : unknown - no per-ad-set CTR data to separate saturation from decay [-, low]
  bidding/budget         : unknown - no edit log; can't rule out a recent bid/budget change
                           resetting learning on this ad set                                 [-, low]
  offer & downstream     : n/a - problem is cost-side (CPM), not conversion-side              [-, -]
  external               : RULED OUT as primary cause - uniformity test fails (85% vs 2-6%
                           is not what account-wide auction inflation looks like); a small
                           genuine external component plausibly explains the +2-6% baseline
                           move on the other four ad sets                                    [low, medium]

confidence     : medium - localisation math is solid on the data given; mechanism and full
                 gate (volume, edit log, tracking reconciliation, CTR) still open
verdict        : targeting (audience saturation in the narrow prospecting ad set) is the
                 dominant cause; a small genuine external/seasonal CPM drift (~2-6%) is real
                 but accounts for only a fraction of the blended move - compound verdict
evidence       : 14-40x differential between the failing ad set and its siblings; frequency
                 more than doubling while reach flatlined; CPA move fully explained by the
                 CPM move (no independent CVR/creative collapse implied)
findings       : 1) confirm no recent bid/budget/audience edit caused a learning-phase reset
                    [medium, -, rules in/out a false positive, near-zero, media buyer]
                 2) pull CTR by ad set for the same window
                    [medium, -, separates pure saturation from creative decay riding along
                     with it, near-zero, media buyer]
                 3) redesign or refresh the saturated audience (broaden the stack, rotate
                    in a lookalike, or let it cool while reallocating spend to the four
                    healthy ad sets)
                    [high, medium, recovers most of the excess CPM without touching budget
                    totals, about a week, media buyer]
                 4) run backend/CRM reconciliation before trusting the CPA number long-term
                    [medium, -, unquantified until run, an hour, whoever holds CRM access]
prediction     : once the saturated ad set is redesigned/refreshed, its CPM should fall back
                 toward the sibling ad sets' range (roughly +2-6% vs baseline) and frequency
                 should drop back toward ~2-3, within one full lag-mature comparison window
handoff        : audience redesign for the saturated ad set; tracking reconciliation before
                 the next CPA read is treated as ground truth
re-check       : one full comparison window after the fix ships, at matched attribution-lag
                 maturity
```

**What not to do:** the reflexive alternative here would be to "increase the budget to ride it out" on the theory that it's just the market. That would pour more spend into the same shrinking, self-competing audience pool, drive frequency even higher, and make the CPM problem worse while confirming nothing about the market.

## Note you can actually send

> Quick correction to the handover note: CPM being up isn't an industry-wide Q4 story here. When I break the account down by ad set, four of the five are only up 2–6%, which is a plausible seasonal drift. The fifth — our main prospecting ad set, running a narrow stacked-interest audience — is up 85%, with frequency nearly doubling (2.1 → 4.8) while unique reach has been flat for a month. That's audience saturation: we've stopped reaching new people and are now paying more to keep showing the same shrinking pool the same ad. It explains almost all of the blended CPM move and, in turn, the CPA increase.
>
> Plan: refresh/broaden that one audience (or rotate in a lookalike) rather than raising budget, confirm no recent edit to that ad set caused a learning reset, and re-check CPM/frequency there against the other four ad sets after one full reporting window. I'll also run a quick backend conversion reconciliation to make sure the CPA read itself is trustworthy before we call this closed.