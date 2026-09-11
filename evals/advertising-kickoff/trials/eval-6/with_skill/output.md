# Quillbrook paid-ads kickoff

I ran this through `advertising-kickoff` (the router for the 31-skill advertising-skills collection). Short version before the detail: **your friend's advice is aimed at the wrong step.** You can't benchmark a CAC you haven't generated yet, and you can't pace a budget against campaigns that don't exist. Both are good instincts — just for month 2, not month 1.

## Cold start — what I assumed vs. what's still open

No `advertising-context.md` exists for Quillbrook yet, so this is a cold start. I don't have interactive turns here, so instead of a 5-7 question interview I inferred what I could and flagged the rest — confirm these before I'd lock anything into the artifact:

| Field | Value | Source |
|---|---|---|
| Business model | B2C, self-serve, $12/mo subscription | stated |
| Spend | $0 today → $3k/mo starting next month | stated |
| Conversion event / source of truth | **unknown** | ⚠️ not stated — biggest open item |
| Creative capacity | **assumed none** (2-person, bootstrapped) | inferred, unconfirmed |
| Hard date / regulated vertical | none stated | assumed none |
| Effort ceiling | assumed "compounding, a few hours/week" — a recurring monthly budget implies an ongoing program, not a one-off | inferred |
| Decided | launch paid ads next month, $3k/mo | stated |

## Route

**`mbfinotti/advertising-skills@ad-platform-selection`** — before anything else, decide which channel families a $12/mo product with a $3k/mo budget can actually afford (payback period, funding floor per channel, disqualifiers). Everything downstream — tracking setup, guardrails, format, creative — depends on this answer.

Not `cac-roas-benchmark`: it computes CAC from **real spend data**, and you have none. Not `ad-budget-pacing`: it tracks spend against an **already-live** budget, and no campaign exists yet. Both are correctly-named goals, just premature — see "Not now" below.

## Short-list (ordered by value ÷ effort, for *this* project right now)

Re-rank note: "not spending yet" empties the normal diagnosis/tuning rungs and promotes platform-selection + conversion-tracking to the top regardless of the default class order. Assumed-no-creative-capacity pushes creative work off the list except the two entries that need no production capacity.

1. ✅ **`ad-platform-selection`** — which channels fit the economics. Costs one session, no data needed. *(promoted: no live account to diagnose or tune yet)*
2. ✅ **`ad-conversion-tracking`** — GO/NO-GO that the trial-start / subscription event fires once and dedupes, before dollar one spends. Costs hours, one engineer. *(promoted for the same reason)*
3. 🎯 **`ad-spend-guardrails`** — turn "$12/mo, 2-person bootstrap" into a written max-CAC ceiling and min-ROAS floor from margin and payback. This is what makes "is my CAC too high" answerable later — run it before you can benchmark anything. Costs one session; needs churn/margin inputs from you.
4. **`ad-copy-variants`** — search headline variants. One of two creative-cluster entries that need zero production capacity, so it survives the "no creative capacity" cut.
5. **`ad-swipe-file`** — pull competitor journaling-app ads into ranked test hypotheses while you wait on the three steps above. Also needs no capacity.

## Chain

This merges two of the collection's reference chains — "launch a new channel" and "the budget stack" — because Quillbrook is doing both simultaneously for the first time:

`ad-platform-selection` → `ad-spend-guardrails` → `ad-conversion-tracking` → *(spend launches)* → `ad-budget-pacing` → `cac-roas-benchmark`

Each hands the next something concrete: platform pick narrows format and tracking work; guardrails give the benchmark a target to judge against later; verified tracking is what makes any later CAC number trustworthy; pacing then benchmark only make sense once real spend exists.

## Not now (with the condition that unblocks each)

- ⏳ **`cac-roas-benchmark`** — after ~4 weeks of live spend + verified tracking.
- ⏳ **`ad-budget-pacing`** — once campaigns are actually live under the guardrail policy (i.e., next month, once steps 1-3 are done).
- ⏳ **`ad-spend-allocation`** — once platform-selection picks 2+ channels that need the $3k split.
- ⏳ **`paid-media-scaling`** — after `cac-roas-benchmark` returns a healthy verdict.
- ⏳ **`ad-creative-brief` / `ugc-ad-scripts` / `ad-hook-analyzer`** — deleted from the short-list, not ranked low, by the assumed no-creative-capacity constraint. Comes back once you confirm a contractor/freelancer or founder time exists, or the platform pick requires video/image assets Meta and TikTok will need.
- ⏳ **`ad-audience-targeting` / `lookalike-audience-seeds`** — once you have enough live customers and spend to size tiers against.

## Gap — nothing in the collection covers this

- **Installing the tracking itself.** `ad-conversion-tracking` verifies an event that's already wired up; it doesn't write the pixel/webhook code. That's on you or an engineer, before that skill can run its GO/NO-GO.
- **Your churn/LTV model.** `ad-spend-guardrails` needs a break-even CAC as input, but deriving it from your retention curve is a product-analytics task, not in this collection.
- **Proving ads (vs. word-of-mouth) actually caused signups at $3k/mo.** No incrementality/holdout skill exists here — worth knowing before you trust any CAC number this small a budget produces.

## Context artifact — `advertising-context.md`

Save this at Quillbrook's project root and commit it — it's what makes your next session warm instead of re-answering all this:

```markdown
# Advertising context

- **Updated**: 2026-09-12 (session 1)
- **Business model**: B2C, self-serve subscription
- **Offer / price point**: journaling app, $12/month
- **Channels / spend**: none live yet; $3k/month starting next month, no channel chosen
- **Conversion / source of truth**: TBD — confirm which system is authoritative (billing platform vs. analytics tool) before `ad-conversion-tracking` can run
- **CAC-ROAS position**: no data yet; no guardrail policy written yet
- **In-flight work**: pre-launch — channel selection, guardrail policy, tracking verification
- **Decided**: launch paid ads next month; $3k/month budget
- **Open**: which channel(s); conversion source of truth; creative capacity (assumed none, unconfirmed); break-even CAC (needs churn/margin input)
- **Constraints**: none stated (no fixed date, no regulated vertical)
- **Horizon / effort ceiling**: assumed compounding, a few hours/week, no headcount — confirm
- **Stakeholders**: TBD — name who decides platform choice and guardrail policy (both founders? one owns marketing?)

## Session log

- 2026-09-12 - kickoff: friend suggested CAC benchmark + pacing dashboard - routed to ad-platform-selection instead (no spend data or live budget exists yet) → next: run ad-platform-selection, ad-spend-guardrails, ad-conversion-tracking
```

## Routines — dry-run, nothing created yet

Default rungs 1-3 apply, but rungs 1-2 can't produce real output until spend starts next month:

```
Routine:    Weekly budget pacing check
Runs:       weekly, once campaigns go live next month (tighten to daily only during a flight's final week — not applicable yet)
Does:       ad-budget-pacing against the $3k/month budget
Outputs to: name a channel — Slack/Notion/shared sheet you two already use
First run:  first Monday after launch (date TBD — depends on when platform-selection finishes)
```

```
Routine:    Monthly CAC/ROAS health check
Runs:       monthly, before the following month's allocation decision
Does:       cac-roas-benchmark against the ceiling set by ad-spend-guardrails
Outputs to: same channel as above
First run:  ~30 days after launch (needs real conversion data first)
```

```
Routine:    Kickoff re-invocation
Runs:       monthly for now (new program, fast-moving); relax to quarterly once stable
Does:       re-run advertising-kickoff, refresh advertising-context.md, re-route
Outputs to: this session
First run:  ~4 weeks from today
```

Approve these and I'll note them as running in the artifact's in-flight work; otherwise the fallback is one calendar reminder: "Advertising check-in — re-run the advertising kickoff."

**Next concrete step:** run `ad-platform-selection` — that needs your margin per subscriber (or at least gross price minus payment-processor fees) and any early signal on where your existing organic users come from.