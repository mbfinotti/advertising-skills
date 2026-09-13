# NorthPeak Analytics — Ad Account Diagnostic

## Headline

Don't tighten targeting yet. The data you've described is a near-exact match for the most common B2B failure mode: **the account is optimizing to the wrong conversion event**, not pulling in the wrong audience. Tightening targeting under the current setup will very likely make cost-per-SQL worse, not better, while looking on the dashboard like it's "working" (CPL will just climb back up).

Here's the reasoning, the verdict, and what to do instead.

## What your own numbers already show

Decomposing CPL = CPM / (1000 × CTR × CVR-to-form) tells you _where_ the 28% CPL improvement came from: some mix of cheaper impressions, higher click-through, or a higher form-fill rate. I don't have your platform-level CPM/CTR breakdown, so I can't localize which lever moved — that's the first export I'd want. But I don't need it to see the actual problem, because you've already supplied the metric that matters more: **cost per SQL**, reconstructed from what you gave me.

Assuming spend was roughly flat at ~$30K/month in both quarters:

|                     | Last quarter     | This quarter |
| ------------------- | ---------------- | ------------ |
| CPL                 | ~$86 (62 / 0.72) | $62          |
| Leads (≈ spend/CPL) | ~1,047           | ~1,452       |
| Lead→SQL rate       | 12%              | 4%           |
| SQLs                | ~126             | ~58          |
| **Cost per SQL**    | **~$714**        | **~$1,552**  |

CPL fell 28%. Cost per SQL more than **doubled**. The platforms did exactly what you told them to do — find the cheapest people who'll fill out the whitepaper form — and they found them. Those people just aren't buyers. This is the same shape as the classic "leads look great in the dashboard, sales says trash" pattern: cheap-to-acquire, high-volume, low-intent.

Critically, this collapse is **concentrated in exactly the campaigns you shifted budget into** — not spread evenly across the account. That localization matters: a uniform decline would point outward (market, seasonality); a concentrated one points at what's specific to those campaigns, which here is "more budget chasing the same cheap-form-fill optimization target."

## Layer screen

| Layer                    | Verdict                           | Evidence                                                                                                                                                                                                                                                           |
| ------------------------ | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Measurement/tracking** | pass (with a caveat)              | Form-fill event reconciles against CRM within a few percent — the _tracked_ event is accurate. But nothing downstream of that (SQL, closed-won) is ever fed back to the platforms — that's not a tracking bug, it's the actual gap (see Structure).                |
| **Structure**            | **FAIL — this is the root cause** | Campaigns optimize to raw whitepaper form fills, an event chosen for trackability, not business value. CPL down + cost-per-SQL up, concentrated in the budget-shifted campaigns, is the signature of a platform rewarded for junk volume.                          |
| **Targeting**            | pass, with a note                 | The "broad audience pulling junk" story is the _symptom_ of the event choice, not an independent cause. If those campaigns broadened, that's the auction finding the cheapest path to the same wrong goal — not evidence the audience definition itself is broken. |
| **Creative**             | unknown                           | No creative-level data supplied; nothing here implicates it. Not ruled in, not ruled out.                                                                                                                                                                          |
| **Bidding/budget**       | unknown                           | No impression-share split or edit log supplied. Worth checking once the event is fixed, not before.                                                                                                                                                                |
| **Offer & downstream**   | pass, tentatively                 | The click-to-form funnel reconciles fine. Worth separately asking whether a free gated whitepaper is simply a low-friction magnet for tire-kickers — that's a related but secondary question, not today's root cause.                                              |
| **External**             | pass                              | No market signal claimed or evident, and can't be invoked anyway while Structure is unresolved — external is a diagnosis of exclusion.                                                                                                                             |

## Evidence gate — read this before acting

Volume is fine (hundreds of leads and dozens of SQLs per quarter clears any reasonable noise band). But two things could still soften this verdict, and you should check them before locking in any plan:

1. **Lag maturity.** B2B lead→SQL conversion typically takes 30–90 days. If "this quarter" isn't fully closed out yet, the 4% is a low-ball number that will drift upward as pipeline matures — you'd be comparing a fully-matured 12% against a still-maturing 4%. Confirm this quarter is either complete or you're comparing equal-maturity windows before treating the gap as final. (This wouldn't explain why the drop concentrates specifically in the budget-shifted campaigns, so I don't think it's the whole story — but it could be inflating the size of the gap.)
2. **Definition consistency.** Confirm "SQL" was defined and scored the same way in both quarters, and that nothing changed in the CRM stage-gate logic between them.

Confidence: **medium-high**. The mechanism (cheap CPL + collapsing SQL rate, localized to budget-shifted campaigns, clean top-funnel reconciliation) is a textbook match for a wrong-optimization-event failure. It's not "high" only because I don't have per-campaign/per-platform breakdowns or confirmation on lag maturity.

## Why _not_ to tighten targeting first

The mechanism, spelled out: the algorithm has no way to know a $62 lead is worthless unless something tells it. Narrowing the audience doesn't change what it's being asked to optimize for — it will keep hunting for the cheapest form-fillers inside a smaller pool. Two likely outcomes, both bad:

- CPL rises (smaller pool, same bidding target) while SQL rate stays broken — it'll look like the fix "didn't work," inviting the next reflex ("okay, then increase budget").
- Or the algorithm just finds a different cheap-but-low-intent segment inside the narrower audience, and you've spent a rebuild cycle for nothing.

Targeting only becomes the right lever _after_ the platform is optimizing toward something correlated with quality. Right now it's aimed at the wrong target with excellent precision.

## What to do instead, in order

1. **Confirm window maturity** (near-zero effort, do this today). Don't finalize any budget/targeting decision until you know the 4% is a mature or fairly-compared number.
2. **Build the CRM feedback loop.** Feed SQL (and ideally closed-won) status back to LinkedIn and Google as offline conversions, and shift bidding optimization toward that event instead of raw form fill. This is the single highest-leverage fix here — it's what actually corrects the auction's incentive. Expect roughly a week of marketing-ops/CRM wiring, then it keeps paying without further work. Before wiring this, get a quick privacy/consent check — pushing CRM outcome data into ad platforms is a data-processing decision, not just a plumbing one, and it's not easily undone once fired.
3. **Adopt cost-per-SQL as the campaign scorecard metric now**, even before the feedback loop lands. Stop steering budget by CPL — it's rewarding exactly the behavior that's hurting you. Near-zero effort, immediate.
4. **Give the offline loop 4-8 weeks to accumulate enough conversions to actually shift delivery**, then re-screen bidding and only then consider targeting — and if you do touch targeting, redesign it around whichever segments the feedback loop shows actually convert to SQL, not a blind "narrow the broad stuff."
5. **Shelve the targeting-tightening plan** for now — not deleted permanently, just parked until step 2 has had a chance to work and you have real signal on which audiences are producing SQLs, not just leads.

## What I'd expect to happen, and when to check

**Prediction:** once the offline-conversion feed and optimization-event switch are live, CPL will likely rise back up somewhat (that's expected and fine), lead→SQL rate should recover toward or above the prior ~12% baseline, and cost-per-SQL should fall back below the ~$714 prior-quarter level within roughly two SQL-maturity cycles.

**Re-check date:** given a ~30-90 day SQL lag, don't judge this before **8-12 weeks post-launch** of the offline feedback loop. If you ship it in the next couple of weeks, plan the re-check for around **late November to early December 2026**.

## What would sharpen this further

If you can pull these, I can tighten the verdict from "medium-high confidence" to "high":

- Per-campaign, per-day export (spend, impressions, CTR, form-fills) for both quarters, so I can localize which lever (CPM, CTR, or form-CVR) actually moved and confirm the concentration pattern precisely.
- Confirmation of whether the shifted budget went to LinkedIn, Google, or both.
- Confirmation that "this quarter" in your SQL numbers is closed/lag-mature, or the actual date range being compared.
- Any edit log of targeting or budget changes and their dates, in case a large single edit (>20%) also triggered a delivery-learning reset that's compounding the read.
