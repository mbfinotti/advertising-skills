# Metriq Systems — Buying Committee Map & Campaign Sequencing

Two things up front, because they change what "build a campaign" should mean here:

1. **300 named accounts is an ABM list, not a lead-gen funnel.** Form-gating everything and running countdown ads at that volume treats a known, finite universe like an anonymous top-of-funnel problem. It isn't one.
2. **Both failure modes are committee/process problems, not urgency problems.** Countdown messaging pressures people who are already engaged — it does nothing for a security reviewer who was never looped in until month 5, and it does nothing for a champion who lost the room because no economic buyer ever showed up. Fix the committee sequencing first; use urgency messaging only where a real deadline exists.

I don't have the 30 call recordings/win-loss notes in front of me, so the committee map below is a standard enterprise-manufacturing buying-committee model for a $150K supply-chain-planning purchase, not something mined from your actual transcripts. Treat it as the skeleton — Phase 0 below is explicitly the step where you populate it with real data before spending ad budget.

---

## 1. Buying Committee Map

| Role | Who | Enters deal | Core question | Veto power | What kills the deal if mishandled | Proof they need |
|---|---|---|---|---|---|---|
| **Economic Buyer** | CFO (sometimes COO) | Should be month 1–2; often actually month 4+ | "What's the payback period and what's my risk if this fails?" | Yes — budget sign-off | Deal fizzles: no EB ever engaged, champion negotiating alone, no forcing deadline | ROI model tied to their own numbers, peer reference from a similar-size manufacturer |
| **Champion / Initiator** | VP/Director Supply Chain or Planning | Month 0 | "Can I build a business case that survives the committee?" | No, but deal dies without one | Loses internal credibility if security/legal surprises appear late — you're currently doing this to them at month 5 | Internal business-case toolkit, ROI calculator, committee sign-off checklist |
| **Security Reviewer** | CISO or delegated IT security lead | **Should be month 1; currently month 5** | "Does this vendor introduce risk I have to own?" | Yes — hard blocker, resets the clock | Late entry = re-litigating scope, timeline, sometimes price, after everyone else is already sold | SOC2 report, subprocessor list, architecture/data-flow diagram, pen-test summary |
| **IT / Integration Owner** | ERP/IT architecture lead | Month 2–3 | "Does this fit our ERP and who maintains the integration?" | Soft veto (can stall indefinitely) | Ambiguity on integration effort surfaces late, adds unplanned IT budget ask | API docs, integration case study with similar ERP stack |
| **End Users** | Planning managers/analysts | Month 2–4 | "Will this actually be usable day to day?" | No formal veto, but weak bottom-up validation reads as risk to the CFO | Champion can't point to user buy-in when challenged | Demo/sandbox access, workflow walkthrough |
| **Procurement** | Procurement/sourcing lead | Month 4–5 | "Are terms competitive, is paper standard?" | Yes — can stall close indefinitely | Enters after security review reopens things, compounding delay | Standard MSA/DPA ready in advance, no surprises on contract terms |
| **Legal** | Legal/compliance | Month 4–5 (should overlap with security, not follow it) | "Data residency, liability, export control exposure?" | Yes | Sequenced after security instead of parallel, adding weeks | DPA, data residency statement |
| **Executive Sponsor** | CEO/COO on transformation-scale deals | Variable, often absent | "Does this matter to the business, not just to Ops?" | Tiebreaker on stalled deals | Absence is exactly why "no decision" deals fizzle — no one above the champion is accountable for a decision | Business case framed as strategic initiative, not a tool purchase |

**The two failure modes mapped onto this table directly:**

- **Security review blowing up month 5** = the Security Reviewer row is engaging 3–4 months later than it should, in parallel with Procurement/Legal instead of ahead of them, so every finding reopens EB and Champion conversations that were already closed.
- **No-decision fizzle** = the Economic Buyer and Executive Sponsor rows are frequently empty. Champion is carrying the deal alone with no one who can actually say yes or no.

---

## 2. Root-cause fixes (these have to happen before the campaign will work)

1. **Pull the Security Reviewer to Stage 1.** Add "who owns security sign-off" as a mandatory qualification field at SQL stage, same as "who's the economic buyer." If sales can't name that person by month 2, the deal isn't qualified — regardless of how warm the champion is.
2. **Publish a self-serve security packet, ungated.** SOC2 summary, subprocessor list, architecture overview. A security reviewer researching a vendor mid-eval and hitting a lead-gen form reads as a vendor with something to hide — that's friction you're currently paying for at month 5 instead of month 1.
3. **Require a named Economic Buyer and a mutual close plan before a proposal goes out.** This is the actual fix for "fizzles with no decision" — not urgency copy, a hard qualification gate.
4. **Run Legal and Security in parallel, not sequentially after Procurement.** Sequencing, not intensity, is what's costing five months.

---

## 3. Campaign Sequencing

Because this is 300 named accounts, paid media plays a support role at each stage of an ABM motion — it doesn't drive the motion. Countdown/urgency creative is used exactly once, in Phase 3, and only against a verified real deadline, not a manufactured one.

### Phase 0 — Committee intelligence (Weeks 1–3, before any ad spend)
- Mine the 30 call recordings/win-loss notes against the committee map above: which roles were present/absent in wins vs. losses, when security actually entered each deal, whether an EB was ever named.
- Segment the 300 accounts by likely committee shape (discrete vs. process manufacturing tends to differ on who owns security sign-off — IT vs. a dedicated CISO).
- Output: a validated, evidence-backed version of the table above, plus a per-segment "who to find first" playbook for sales.

### Phase 1 — Pre-engagement trust building (all 300 accounts, top of funnel)
- **Channel:** LinkedIn account-based ads targeting Champion + Economic Buyer titles at the 300 named accounts.
- **Message:** category/ROI thought leadership. No urgency, no countdown — there's no relationship yet, so pressure reads as spam.
- **Gating:** none. Security trust page (SOC2 badge, security overview, architecture summary) live and crawlable — this is the single highest-leverage move against the month-5 problem, because it lets a security reviewer self-serve before they're ever formally looped in.
- **Success metric:** account-level engagement (site visits, security page views) from target accounts, not raw form fills.

### Phase 2 — Active opportunity enablement (accounts in open pipeline)
- **Channel:** retargeting ads + direct outreach to named committee members.
- **Champion track:** gated ROI calculator / internal business-case toolkit — legitimate value exchange with a known contact, progressive profiling not a cold form.
- **Security-reviewer track, starting here (not month 5):** architecture whitepaper and compliance packet served directly once the reviewer is identified per the Stage 1 qualification rule above. Deeper technical doc can be lightly gated (known contact, one field); the core SOC2/subprocessor material stays ungated from Phase 1.
- **Sales motion, not ads:** rep explicitly asks "who signs off on security" and "who owns budget" as qualification questions — this is the actual fix, ad spend just supports it.

### Phase 3 — Decision-forcing (accounts with a live proposal, confirmed EB engaged)
- This is the only phase where urgency creative is appropriate, and it must be tied to a **real, confirmed deadline** — the account's own fiscal year-end or budget cycle, gathered from champion/EB conversations — never a generic countdown.
- **Message to CFO:** cost-of-delay framed against their own numbers (from the ROI calculator they already used in Phase 2), tied to their actual budget cycle date.
- **Message to security reviewer:** none — by this stage they should already be signed off from Phase 2. If they're not, that's a qualification failure, not a targeting opportunity.
- **Gating:** none. This is one-to-one selling supported by ads, not lead capture — you already have every contact on the committee by this stage.

### Phase 4 — Stalled / no-decision recovery
- Ads play a minor, warm-retargeting role only.
- Primary motion: executive sponsor letter (your exec to their exec), re-qualification of whether an EB still exists and whether budget still exists.
- **Trigger rule:** if a deal has had no committee movement in 45 days, it moves here automatically rather than staying in generic nurture — this directly targets the "embarrassing share that just fizzle out" problem by forcing an explicit re-qualify-or-close-lost decision instead of letting it drift.

---

## 4. Gating policy (single rule, applies across all phases)

Gate by **funnel depth and relationship**, never by role:
- Top-of-funnel trust content (security overview, SOC2 summary) — **always ungated**. This is the direct fix for the month-5 blowup.
- Mid-funnel tools with a known contact (ROI calculator, benchmark report) — **gated with progressive profiling**, not a fresh form every time.
- Late-funnel — **no gates**. By Phase 3 you have the full committee identified; a form at this stage only adds friction to people you already know.

---

## 5. What "success" looks like

- Security Reviewer identified by end of Stage 1 qualification, not discovered in Stage 4 — track median month-of-entry per deal, target < month 2.
- Economic Buyer named before proposal stage on 100% of deals that reach proposal — this is the actual anti-fizzle metric, not ad CTR.
- Reduction in deals that reopen after security review, tracked as a distinct loss reason in the CRM going forward.
- Phase 4 recovery rate (stalled deals forced to an explicit close-won/close-lost decision within 45 days) replaces "still in pipeline, no activity" as a tracked state.