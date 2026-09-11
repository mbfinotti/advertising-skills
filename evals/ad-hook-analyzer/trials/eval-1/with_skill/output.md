# Brimstone Coffee — Hook Batch Scorecard

**Direct answer to "which gets the highest hook rate":** this method can't produce that number honestly — see below — but it can tell you what to fund. **B ranks first, C is a close second, A is gated out until a 5-minute caption fix, D is not a real third test cell as submitted.**

## Two things flagged before scoring (not answered in your brief)

I proceeded rather than blocking on these, but they change the qualification band and the variation call if I've guessed wrong — correct me and I'll re-band:

- **Buyer / disqualifier**: assumed = people who already drink cold brew or iced coffee and are dissatisfied with speed, strength, or mess of their current method; disqualified = non-coffee-drinkers and people happy with their current brew who aren't price-sensitive.
- **Already-running creative**: assumed none of these four visuals are already live. If A, B, or C overlaps a currently-running ad, the variation gate needs a second pass.

Production capacity is answered well enough to work with: in-house editor + raw shoot footage confirms **rungs 1–3** (text rewrite, caption fix, re-cut) are available for this batch. No shoot slot was mentioned, so rung 4 (new opening beat) isn't used below — it isn't needed anyway.

## Why no "/10" score

You asked for a score out of 10 per hook. I'm not giving one, and here's the actual reason, not a hedge: hook rate is a practitioner-built ratio with no fixed definition, and the one outside dataset that's actually measured this — 3,859 ads across 11 brands — found hook rate correlates **-0.19 with ROAS**. A 7.4-vs-7.1 decimal would claim precision that data doesn't support and would steer your test budget on a number two analysts wouldn't reproduce. What follows instead: pass/fail gates (absolute), strong/adequate/weak bands (relative, no arithmetic), and a pairwise fund-this-first ranking — which is what actually predicts what deserves budget.

```
HOOK BATCH SCORECARD — Brimstone Coffee $34 starter kit, Meta feed, 2026-09-12
batch        : 4 candidates | input: shot/concept descriptions (first 3 seconds each)
hook window  : first 3s | audience: cold B2C
dashboard    : hook rate = 3-second video plays / impressions (Meta standard construction — confirmed)

gates
  A: sound-off FAIL (the glass-shatter IS the punchline; "enough." alone doesn't carry it muted)
     | promise-payoff pass (vague but not contradicted — "enough" plausibly resolves in the brewing demo)
     | qualification pass (French press is a named, specific rejected method — not pure spectacle)
     | variation pass
  B: sound-off pass | promise-payoff pass | qualification pass | variation pass
  C: sound-off pass | promise-payoff pass | qualification pass | variation pass
  D: sound-off pass | promise-payoff pass | qualification pass
     | variation FAIL — merged with C (identical footage; text-only difference is not a test cell)

bands (gate-passing candidates only)
  B: time-to-signal strong | sound-off strong | qualification adequate | specificity strong
     | brand timing strong — DR objective, the actual product bottle is the opening frame, no logo card
     | continuity strong — the ad's payoff IS the 3-second claim, literally the offer in miniature
     | placement fit strong
  C: time-to-signal strong | sound-off strong | qualification strong — dilution is a pain only
     cold-brew drinkers recognise; iced-coffee-only viewers have less reason to stay
     | specificity adequate — the visual is checkable but "here's why" defers the actual mechanism
     | brand timing adequate — no Brimstone product/brand cue anywhere in this window
     | continuity strong — *if* the demo explicitly shows the concentrate isn't diluted; flag this
     assumption, it's the one place the promise depends on footage I haven't seen
     | placement fit strong

ranking (pairwise, valid within this batch only — not a performance prediction)
  1. B — vs C: both land the promise instantly and survive muted. B wins because its promise
     is the payoff with nothing to prove later (10 seconds, $34, done) — C opens a gap
     ("here's why") that only pays off if the demo explicitly resolves dilution. Motion's 2026
     data is a tiebreaker only, not proof: "offer only" was its top-performing category by hit
     rate in a BFCM-window dataset that skews toward offer/urgency framing.
  2. C — the sharper qualifier of the two (names a felt problem specific to cold-brew drinkers)
     but carries a continuity dependency B doesn't have, and shows no product/brand cue at all
     in the window.
  3. A — cannot rank above a gate-clean candidate regardless of how visceral the smash is;
     the punchline living entirely in the crash sound is the textbook audio-dependent failure
     on a platform that autoplays muted.
  (D not ranked — merged with C, a cosmetic-only-variation failure, not a fourth concept.)

  raise-the-rank (cheapest rung that removes the failure)
  A: [rung 2, caption/text-layer fix] the sound design carries the entire payoff — add or
     expand on-screen text that states what's being rejected and why ("no more glass. no more
     30 minutes." or similar), so the meaning survives muted instead of living only in the crash.
  D: [rung 3, re-cut from footage already shot] open on a different frame than C's — e.g. the
     concentrate pouring, or a side-by-side with a diluted cup — to get the visual difference
     the variation gate requires. A pure text swap on C's exact shot will keep merging.
  rungs used: 2 and 3 only, both confirmed available (in-house editor + raw footage).
  rung 4 (new opening beat) not needed for either fix — don't spend a shoot slot here.

shipping check : 2 openings (B, C) clear all gates cleanly as submitted — BELOW the 3-opening
                 floor. Do not launch as a 4-cell test yet: apply A's caption fix and D's
                 re-cut first to get three genuinely distinct, gate-clean concepts (offer,
                 confession, rejection-of-old-method) before spending budget.

calibration    : after launch, compare this order (B, C, then revised A/D) against the
                 measured 3-second-plays/impressions order on the same placement; log rank
                 agreement. Over a rolling 5-batch window, treat the rubric as working only if
                 the top-ranked opening lands in the measured top half at least 3 times —
                 below that, re-derive dimension weighting from Brimstone's own past winners
                 instead of this generic rubric.
```

One more honesty note since you asked "which will get the highest hook rate" specifically: even a clean B>C prediction, if it lands, is a scroll-stopping ranking — not a sales one. The same dataset behind the -0.19 correlation is why a hook-rate winner still needs the guarantee card and the demo to actually carry the sale. Track ROAS on these independently of which one wins the hook-rate test.