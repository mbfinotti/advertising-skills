# Bramwell Software — Customer Acquisition Cost (CAC) Policy

*(Formal draft for board approval — v1.0)*

I don't have your existing rules document in this workspace, so I've formalized it from what you described (a $310 CAC ceiling, self-approved overages, zero breaches in three quarters) and built out the pieces a board-facing policy needs but an informal rule usually skips. Placeholders `[ ]` mark facts only you can fill in.

---

## 1. Purpose

This policy governs paid customer acquisition spend to ensure it remains consistent with unit economics and company financial targets.

## 2. Scope

Applies to all paid acquisition spend (paid media, sponsorships, paid partnerships/affiliates, lead-gen fees) attributed to new customer acquisition. Excludes organic, referral, and brand spend not tied to a CAC calculation.

## 3. Definitions

- **CAC** = total attributed acquisition spend in period ÷ new customers acquired in period.
- **Attribution window**: `[ define — e.g. 30/60/90-day last-touch ]`
- **Cost basis**: `[ confirm — media spend only, or fully loaded (media + tooling + agency fees + comp)? ]`
- **Measurement cohort**: `[ blended across all channels, or per-channel/per-segment? ]`

These three definitions are currently undefined in the informal version. A CAC ceiling means nothing to a board or auditor unless the formula behind it is fixed — same $310 figure can be hit or missed depending on what's included.

## 4. Policy Statement

- Target CAC ceiling: **$310** per acquired customer, measured as defined in §3.
- Spend that would push CAC above $310 requires an approved exception before it is committed.
- The $310 ceiling is derived from `[ LTV, gross margin, and target payback period — insert the underlying math ]`. **Action item**: this number should be traceable to unit economics, not fixed by convention — if LTV or margins have moved since the ceiling was set, $310 may already be stale.

## 5. Approval Authority

| Overage size | Approver |
|---|---|
| Up to `[X]%` over ceiling | Head of Growth |
| `[X–Y]%` over ceiling | Head of Growth + CFO |
| Above `[Y]%`, or cumulative overages exceeding `[$Z]`/quarter | CEO or Board notification |

**This is the one substantive change I'd make before this goes to the board.** Today, the same person who sets the ceiling also approves every exception to it — that's a single point of control with no check, and a board reviewing this policy will likely ask about it directly. It doesn't mean the Head of Growth has done anything wrong; it means the policy as described has no structural separation between rule-setter and rule-waiver. A tiered table like the one above (or at minimum, a second signer above some threshold) fixes that without slowing down day-to-day approvals.

## 6. Reporting & Audit Trail

- Every approved exception is logged: date, channel/campaign, CAC achieved, approver, reason.
- Quarterly summary to the board: count of exceptions, total $ over ceiling, trend vs. prior quarters.
- This log doesn't exist yet as a formal requirement — "zero breaches in three quarters" is currently an informal claim, not an auditable one. Formalizing the log is what actually lets you say that with evidence in a board deck.

## 7. Review Cadence & Change Control

- Ceiling reviewed **quarterly**, alongside LTV/margin inputs.
- Changes to the $310 figure itself require `[ CFO sign-off / board notification — pick one ]`. This is distinct from approving an individual overage (§5) — one person shouldn't be able to both waive the rule and quietly reset it.

## 8. Exceptions

- Exceptions are approved **per campaign, with an end date** — not standing. `[ confirm this matches current practice ]`

## 9. Ownership

- Policy owner: Head of Growth
- Approved by: `[ CFO / Board ]`
- Effective date: `[ ]`
- Next review: `[ Q+1 ]`

---

## Worth adjusting — and one thing worth challenging

**On "we haven't breached it once in three quarters, so it clearly works":** that's not actually evidence the ceiling is right — it's evidence it's either well-calibrated *or* never binding. A ceiling nobody bumps into for a year could mean acquisition spend is comfortably efficient, or it could mean the number was set loose enough (or gets waived easily enough by the same person who set it) that it never functions as a real constraint. Before this goes to the board as proof the policy "works," it's worth pulling how close actual CAC has run to $310 each quarter — if it's consistently $180–220, the ceiling is decorative, not operative; if it's consistently $295–309, it's a live constraint that's holding.

**Ranked, the adjustments that matter most:**

1. **Separate setting the ceiling from approving overages of it** (§5) — the single biggest governance gap for a board-facing document.
2. **Define CAC precisely** (§3) — fully-loaded vs. media-only and the attribution window change what "$310" even means.
3. **Tie the number to unit economics explicitly** (§4) — a flat CAC ceiling with no visible link to LTV/margin looks arbitrary to a board, even if it isn't.
4. **Start logging exceptions** (§6) — needed to keep making the "never breached" claim credibly, and needed for the quarterly review to mean anything.
5. **Consider segmentation** — one ceiling across all channels/customer segments is usually blunter than needed once volume justifies splitting it out; not urgent for v1, worth flagging as a fast-follow.

Everything above is drafted to be board-ready as-is; items 1–3 are the ones I'd genuinely push back on rather than just formalize verbatim, since "formalizing" a self-approval loop without noting it is likely to draw a direct question in the room.