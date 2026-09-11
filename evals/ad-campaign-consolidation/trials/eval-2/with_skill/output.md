# Kestrel Shield — Campaign Consolidation Plan

*(via `ad-campaign-consolidation` skill)*

## Headline answer first, because it's not what you asked for

You asked how to combine 11 campaigns so the algorithms get enough data. The honest answer, from the arithmetic below: **consolidation alone will not get you there.** Even the best-case, fully-merged structure (one LinkedIn campaign + one Google campaign) still won't clear either platform's practical volume floor. At 6 demos/month, you don't have a structure problem you can merge your way out of — you have a volume problem, and merging is necessary but not sufficient.

So the plan below leads with the move the skill this runs on calls `up-funnel`, normally ranked *last* for efficiency — promoted to first because your numbers trigger the one condition that overrides the default order.

## The math that decides this

| | |
|---|---|
| Total spend | $7,000/month |
| Total conversions (demo requests) | ~6/month |
| Campaigns | 11 |
| **Current blended cost/demo** | **≈ $1,167** |
| **Avg conversions per campaign** | **≈ 0.55/month** (one demo every ~2 months, per campaign) |

Now the best case — full consolidation to 2 campaigns, one per platform, rough even split of spend:

| | LinkedIn (merged) | Google Search (merged) |
|---|---|---|
| Est. monthly spend | ~$3,500 | ~$3,500 |
| Est. monthly demos | ~3 | ~3 |
| Platform's own benchmark | No documented conversion threshold; AJ Wilcox's practical floor is **$3-5K/month for usable data** | No hard tCPA gate documented (the "15-30 conversions/30 days" rule is Target *ROAS*-by-campaign-type folklore when misapplied to tCPA) — but the practitioner starting point for merging search into automated bidding is **~15-30 conversions/month** |
| Verdict at merged scale | Sitting right at the *floor*, not past it | Still 5-10x under the practitioner benchmark |

That's the trigger condition from the skill: *"the volume test shows that even the fully merged structure would not clear the platform's threshold."* When that's true, `up-funnel` gets promoted straight to first, ahead of `prune`. That's your situation.

## Evidence Gate status ⚠️

Before this becomes a fully numbered merge plan, a few things are missing — this is a real, named state ("insufficient evidence"), not me stalling:

| Gate criterion | Status |
|---|---|
| Per-branch conversion/spend export | ❌ Not provided — I only have account totals |
| Real target CPA from unit economics | ❌ Not provided — your current blended $1,167/demo is a *fact*, not a target |
| Which of the 11 splits are deliberate vs. archaeological | ❌ Not provided |
| LinkedIn vs. Google spend split | ❌ Not provided (assumed ~even above) |
| Active cost spike or reactive panic right now | ❌ Unconfirmed |
| Tracking/CRM owner available for an up-funnel proxy event | ❌ Unconfirmed |
| Hard deadline / peak season | ❌ Unconfirmed |

None of this blocks the structural and up-funnel recommendations below — those follow from totals alone. It does block a precise per-branch classification table. Send me, per campaign/ad set: daily budget, bid strategy, optimization event, audience/keyword theme, and 30-60 day conversions, and I'll turn the table below into exact merge groups.

One thing *is* already dispositive without an export: **100% of your branches are symptomatic** (every LinkedIn campaign, "terrible delivery"; every Google campaign, stuck in Learning). Normally I'd worry about restructuring reflexively mid-learning-phase — but nothing here is stable to begin with, so there's no stable baseline a merge would be resetting. This isn't a panic reflex; it's a chronic never-exits account. Restructuring is warranted, not premature.

## Recommended moves, in order

**1. `up-funnel` (promoted to first) — move the bid-optimization event off "demo request"**

- On both platforms, pick a higher-volume proxy up top of the funnel: qualified form-open, pricing-page view, a gated technical asset download, or a chatbot/qualification-flow completion.
- Feed CRM outcomes (demo → SQL → closed-won) back into the platform so the proxy stays honest — this needs whoever owns your CRM/marketing-ops stack. If nobody currently owns that pipeline, fall back to manual bid strategies on both platforms and judge on leading metrics (CTR, cost/click, proxy-conversion rate) instead — cheaper to start, but it's a settings change, not a fix that restores an automated signal.
- This is the only move in the whole ladder that works when the fully-merged structure still can't clear threshold — merging further just spends another learning cycle re-proving what you already know.

**2. `prune`, in parallel — near-zero cost, do this immediately**

- Pause any of the 11 campaigns nobody can currently justify with a live business reason ("we haven't touched it since an agency set it up" counts as unjustified). Shift their budget to survivors in ~20% steps.
- Pausing doesn't reset learning, needs no sign-off beyond budget ownership, and is instantly reversible. I need the "why does each one exist" answer from you to actually tag which of the 11 qualify — my best guess without that data is that a fair share are archaeological, given nobody escapes Learning today.

**3. `merge` — target end-state structure**

- **Google Search:** Hagakure-style — collapse toward 2-3 intent-themed campaigns max (e.g., Brand, Category/Solution, Competitor if you run one), each getting real budget instead of splinters. Keep **Brand and non-brand structurally separate with distinct bid strategies** — this is a hard preserve rule. Pooling them lets automation eat the cheap brand clicks and blind you to non-brand growth exactly when you can least afford it.
- **LinkedIn:** one well-funded campaign beats three thin ones — that's a documented practitioner pattern at low audience penetration, which is exactly your symptom ("terrible delivery"). If you're running separate campaigns per buyer persona (CISO / security engineer / compliance), don't rebuild that as separate campaigns — see below.

**4. Keep segmentation, lose the structure**

- If those 11 campaigns encode persona or ICP-tier targeting (a common B2B pattern), don't preserve that as campaign splits. Move it into creative variants inside the merged campaigns — one variant per persona, same budget pool, let delivery match variant to viewer. Stacked narrow filters on thin B2B audiences are a big part of why delivery is "terrible" right now.
- Exception: if you run account-based marketing against a named target-account list, that *does* need structural separation (guaranteed frequency), not a creative variant — tell me if that's the case.

**5. What's explicitly *not* on the table**

- `big-bang` (whole-account rebuild at once) — ruled out. It relearns everything simultaneously and the outcome can't be attributed to anything. You have a 4-month sales cycle; you cannot afford to lose the ability to read what worked.

## Migration sequence

1. **Phase it** — highest-confidence/archaeological merges first, not everything at once.
2. **Build new, don't edit in place** — build merged campaigns fresh, shift budget over, then pause (never delete) the old ones. Editing targeting/bid/event/budget beyond ~20% inside a live campaign resets its learning; pausing doesn't.
3. **Keep a control** — run legacy structure at reduced budget alongside the new one where volume allows, so the before/after is attributable.
4. **Time it off your peak**, if you have one — flag if there's a seasonal pattern in your pipeline.
5. **Pre-commit the no-touch window, in writing, before phase one:** no meaningful edits for at least 14 days for a real read; because of your 4-month sales cycle, the real verdict (does this actually produce more closed-won, not just more demos) needs a full sales cycle after the final phase.

## Measurement plan

- **Baseline:** current blended cost/demo (~$1,167) and the fact that 100% of spend currently sits in Learning-limited/never-exits territory.
- **Pass threshold at re-check date** (1 learning cycle + up to 1 sales cycle after final phase, ~4-5 months out):
  - Surviving branches clear their volume/budget floor, or the up-funnel proxy is doing the work instead.
  - Blended cost/demo at or better than baseline.
  - If still failing after two iterations, that's evidence consolidation isn't this account's fix — route to root-cause diagnostic work instead of a third restructuring pass.
- **Rollback trigger, set now, before phase one:** blended cost/demo worse than ~$1,750 (1.5x baseline) once the no-touch window has matured. Rollback = shift budget back to the paused legacy structure, which is exactly why it stays paused, not deleted.
- **For the real verdict, don't trust platform-reported numbers alone** — with a 4-month sales cycle and $30K ACV, the thing that matters is closed-won at the end, not demo volume in month one. Prefer a lift read (in-platform, one cycle) over raw platform ROAS; only escalate to a geo holdout if this consumes a large share of your budget.

## What I need from you to finish this

Send per campaign/ad set: platform, spend/day, bid strategy, optimization event, audience or keyword theme, 30-60 day conversions, and the one-line reason it was split out. With that I'll turn "11 campaigns" into an exact classification table (merge / keep / keep-but-re-parent / insufficient evidence) and name the specific merge groups instead of the directional plan above.