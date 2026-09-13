# PRE-LAUNCH TRACKING VERIFICATION — Fernhollow Analytics "Demo Request", 2026-09-12

**platform(s):** Google Ads | **funnel:** B2B lead gen | **server-side:** unknown — not stated, needs confirming
**launch:** Monday | **budget at risk:** $38,000 (first month)

| #   | check                            | result                                           | impact   | fix effort | evidence                                                                                           |
| --- | -------------------------------- | ------------------------------------------------ | -------- | ---------- | -------------------------------------------------------------------------------------------------- |
| 1   | settings & designation           | pass (reported, not independently reviewed here) | —        | —          | "Demo Request" created, set primary; count-once vs count-every not confirmed from your description |
| 2   | tag debug / preview              | pass                                             | —        | —          | Tag Assistant shows tag green on demo confirmation page                                            |
| 3   | real test conversion, end to end | **not done**                                     | critical | near-zero  | no test lead submitted with a unique QA value, no confirmation it landed in the CRM                |
| 4   | payload inspection               | **not done**                                     | critical | near-zero  | event name/value/currency/event ID never read from the actual request                              |
| 5   | platform UI + status             | **fail**                                         | critical | —          | conversion action status: **"No recent conversions"**                                              |
| 6   | deduplication                    | unknown                                          | —        | —          | depends on whether a server-side/Conversions API path exists — not stated                          |
| 7   | test-data exclusion              | n/a yet                                          | —        | —          | nothing to exclude — no test conversion has run                                                    |
| 8   | soak                             | n/a yet                                          | —        | —          | blocked upstream                                                                                   |
| 9   | sign-off                         | blocked                                          | —        | —          | blocked by checks 3, 4, 5                                                                          |

## DECISION: NO-GO

I can't sign this off. Here's why "we haven't launched yet" doesn't cover it, in the skill's own terms:

- **A green tag in Tag Assistant is not proof of measurement.** It tells you the tag fires — it tells you nothing about whether the value, currency, or event ID are correct, or whether Google actually received and is recording it. Screenshots of settings screens are the same category of non-evidence: reviewed, not traced.
- **"No recent conversions" is an automatic NO-GO**, independent of everything else — the skill treats a primary action in a misconfigured or waiting status as a hard blocker, full stop.
- The one exception that would let a status like this slide — a brand-new property with no traffic yet — still requires debug-mode evidence **plus a correct payload**, and even then only earns a _provisional_ PASS, not a GO. You don't have the payload check, so the exception doesn't apply as-is.
- The action being 6 days old with zero recorded conversions most likely means: no one has actually walked the funnel and confirmed the event lands, not that Google just hasn't gotten around to updating a status page.

## Fix order (near-zero effort, fits before Monday)

1. **Submit one real test demo request** with a unique identifiable value (e.g. a QA-tagged email/company name), confirm it lands wherever demo requests go (CRM/inbox/whatever "Demo Request" feeds).
2. **Inspect the payload** — browser network tab or Tag Assistant's event detail: correct event name, value/currency (or confirmed intentionally valueless), a stable event ID.
3. **Recheck the conversion action status in Google Ads.** It should flip off "No recent conversions" within a few hours of that test firing. If it doesn't, the tag isn't actually reaching Google despite showing green locally — that's a trigger or container-publish problem, not a waiting-period problem.
4. **Exclude the QA record** — delete/flag the test lead in the CRM once step 3 confirms it counted, so it doesn't pollute the first week of real data.
5. Only after 1–4 hold: let a few days of real signal accumulate before trusting bid optimization on it.

## Open questions before I can rank the rest

- Is anything server-side (offline conversion import, Enhanced Conversions) also feeding this action, or is it browser-tag only? Determines whether step 6 is a real dedup check or N/A.
- Is a consent banner live for EU traffic, and did you test the **reject** path, not just accept? Signal silently dies there and it's the check most often skipped.
- Who fixes this if it's not just a settings toggle — you directly, or does it need dev/tag-manager access?

**blockers:** conversion status unhealthy (fix owner: TBD — likely you, this is a same-day fix); real test conversion + payload trace never run
**deferred:** none yet — nothing has cleared the gate to defer from
**deleted:** n/a
**re-verify:** full sequence from step 3, once the test conversion is run and the status flips
**approver:** — (withheld) **date:** 2026-09-12

Run the test conversion today, and paste me the status + payload once you have it — this is genuinely a same-day fix, not a schedule risk to Monday.
