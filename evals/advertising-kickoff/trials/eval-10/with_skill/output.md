## Cold start — no `advertising-context.md` for Copperline Studio

No context artifact exists in this project, so this is a cold start. The routing question is unambiguous and time-sensitive, so I'm answering it directly rather than opening a 7-question interview first — but the fields a full interview would fix (business model, channel/spend band, hard date, effort ceiling) are logged as open below, not skipped.

## Route: `mbfinotti/advertising-skills@ad-account-diagnostic` — not all three

Don't run the three fixes. **Ship none of the three (new creative batch, tracking rebuild, page rollback) this sprint until the diagnostic returns a verdict.**

Here's why: your three team members aren't disagreeing about the fix, they're disagreeing about the diagnosis — and they've each independently named the layer they personally own. That's not evidence, that's priors. If you run all three in parallel and CPA recovers, you will never know which one worked, so the next time CPA drifts you're back to three guesses instead of a method. If you run all three and CPA _doesn't_ fully recover, you won't know which fixes to keep and which to revert. Worse, two of the three changes (new creative + a page rollback) landing in the same window as a tracking rebuild means any read you take afterward is confounded by construction — exactly the kind of multi-variable mess `ad-account-diagnostic` exists to cut through instead of add to.

`ad-account-diagnostic` implements nothing itself. It runs on the data you already have (spend, CPA trend, platform-vs-backend conversion counts, creative frequency/CPM, landing-page conversion rate — all segmented around the site-rebuild date) and localizes which layer actually broke, in a fixed check order: measurement first, because if the pixel is genuinely double-firing, every other number you're reading — creative frequency, page conversion rate, the CPA figure itself — is corrupted and any conclusion drawn from it is noise. Note the direction isn't obvious either: a double-fire that duplicates purchase events would typically _lower_ reported CPA (double-counted conversions), not raise it to $190 — which is itself a reason to verify rather than accept the dev's theory on priors, same as the other two.

## Conditional chain (dependency order — nothing here is optional or parallel)

```
mbfinotti/advertising-skills@ad-account-diagnostic
        │
        ├─ names creative as failing layer ──→ mbfinotti/advertising-skills@ad-creative-fatigue
        │                                       (checks for confounders — incl. tracking breakage —
        │                                        before crediting "fatigue"; only then feeds a real
        │                                        creative refresh)
        │
        ├─ names tracking as failing layer ──→ mbfinotti/advertising-skills@ad-conversion-tracking
        │                                       (GO/NO-GO on event config, single-fire, dedup —
        │                                        the actual test of the dev's theory)
        │
        └─ names post-click as failing layer ─→ mbfinotti/advertising-skills@paid-landing-page-audit
                                                 (message match, friction, speed — the actual test
                                                  of your theory)
```

The diagnostic can also name more than one layer at once (a rebuild is exactly the kind of event that can break two things simultaneously) — in that case, work the named layers in the order the diagnostic gives them, not all at once for the same reason above.

## Short-list (value ÷ effort, highest first)

| #   | Skill                                                                  | Bottleneck it attacks                                                            | Session cost                                          |
| --- | ---------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------- |
| 1   | `mbfinotti/advertising-skills@ad-account-diagnostic`                   | Which layer actually broke, instead of three competing opinions                  | One session, data already in hand, implements nothing |
| 2   | `mbfinotti/advertising-skills@cac-roas-benchmark`                      | Whether $190 CPA is "bad" against your own break-even/history, not just "up"     | Hours, same data pull as #1                           |
| 3   | `mbfinotti/advertising-skills@ad-conversion-tracking` _(conditional)_  | Confirms or kills the double-fire theory with a real GO/NO-GO instead of a hunch | Hours, mostly the dev's                               |
| 4   | `mbfinotti/advertising-skills@ad-creative-fatigue` _(conditional)_     | Genuine wear-out vs. a confounder the media buyer isn't accounting for           | One session, no production yet                        |
| 5   | `mbfinotti/advertising-skills@paid-landing-page-audit` _(conditional)_ | Turns "I think the redesign killed it" into a prioritized, evidenced fix list    | One session; page owner sets the pace                 |
| 6   | `mbfinotti/advertising-skills@ad-spend-guardrails`                     | No kill-switch stopped a 137% CPA drift from running three full weeks unflagged  | A session + sign-off, once the fire is out            |

Ranking note: with the conversion source of truth actively disputed, measurement stays pinned above diagnosis by the collection's own default — but here the diagnostic itself checks measurement first, so #1 and #3 aren't competing, #3 is what #1 triggers if it confirms the tracking theory.

## Not now

- `mbfinotti/advertising-skills@ad-creative-brief` / `ugc-ad-scripts` / `ad-copy-variants` — the "new creative batch" is paused, not cancelled. Unblocks only if `ad-creative-fatigue` returns a genuine-wear-out verdict.
- `mbfinotti/advertising-skills@ad-attribution-gap` — relevant if the diagnostic finds a platform-vs-backend reporting gap rather than a straightforward dedup bug; premature to route there before the diagnostic runs.
- `mbfinotti/advertising-skills@paid-media-scaling` / `ad-spend-allocation` — no budget decision belongs on the table while the account is actively bleeding CPA for an unconfirmed reason.

## Gap

None in-scope is missing here, but worth naming: once the diagnostic and the named-layer skill produce a fix list, this collection has no skill for _implementing_ it (writing the tracking fix, editing the landing page, producing the creative asset) — that execution stays with your dev, page owner, and media buyer respectively.

## Context artifact (bootstrapping `advertising-context.md`)

```markdown
# Advertising context

- **Updated**: 2026-09-12 (session 1)
- **Business model**: not yet asked
- **Offer / price point**: not yet asked
- **Channels / spend**: not yet asked
- **Conversion / source of truth**: disputed — dev suspects the pixel double-fires since the site rebuild; not yet confirmed
- **CAC-ROAS position**: CPA $80 → $190 over 3 weeks (+137%); no written guardrail policy on record
- **In-flight work**: three fixes queued and held — new creative batch, tracking rebuild, landing-page rollback — pending ad-account-diagnostic verdict
- **Decided**: none yet
- **Open**: (1) is the creative genuinely fatigued or confounded, (2) does the pixel double-fire and does it explain the CPA move, (3) did the landing-page redesign break conversion, (4) business model / spend band / hard date / effort ceiling not yet asked
- **Constraints**: this sprint (exact date not given); site rebuild and landing-page redesign both landed recently, overlapping the CPA jump
- **Horizon / effort ceiling**: not yet asked
- **Stakeholders**: media buyer (creative-fatigue theory) · dev (tracking theory) · you (landing-page theory) — decision owner not stated

## Session log

- 2026-09-12 - CPA jump ($80→$190), three competing team theories → mbfinotti/advertising-skills@ad-account-diagnostic routed; three layer fixes paused pending verdict
```
