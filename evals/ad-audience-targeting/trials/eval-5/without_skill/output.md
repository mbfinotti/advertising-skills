# Nestbird Meta Audience Plan — Review Before Build

Before handing you a build sheet, I need to flag two problems with the plan as specified. One makes it **not legal to run**; the other makes it **not possible to run on Meta as described**. I won't write the "quietly exclude financially struggling people" layer — not as a wording nitpick, I mean I won't produce ad-targeting instructions that operationalize it. Here's why, then here's the plan I _can_ give you.

## Why the financial-distress exclusion is a hard no

Nestbird extends credit. Under the Equal Credit Opportunity Act (ECOA) and Regulation B, discrimination on a prohibited basis is banned at every stage of a credit transaction — **including advertising and pre-application targeting**, not just underwriting. You don't need to name race, disability, or income directly for this to be illegal: excluding people whose "profiles suggest financial struggle" is a facially neutral proxy that will correlate with income, disability status, age, and race in ways that produce disparate impact. Regulators (CFPB, DOJ, HUD in the analogous FHA context) have brought and settled cases specifically over algorithmic ad-targeting exclusion in lending — this is a well-trodden enforcement lane, not a hypothetical.

The word "quietly" is the part I'd flag hardest to you directly: it reads as wanting this exclusion to exist without leaving a paper trail for compliance/legal/regulators to review. That's the difference between a targeting decision your compliance team could defend and one that looks, on discovery, like deliberate concealment — which tends to convert a civil exposure into a much worse one. If there's a legitimate underlying goal here (e.g., not wasting spend on people who won't qualify), it needs to go through your compliance and legal team as a documented, defensible underwriting-adjacent policy — not as a silent ad-platform exclusion I hand you as a growth tactic.

## Why the rest of the spec doesn't run on Meta either

Personal loan refinancing is a **credit product**, so any Nestbird ad using it must be flagged as **Special Ad Category: Credit** in Meta Ads Manager. Meta requires this classification for lenders specifically because of a 2019 HUD/DOJ settlement over discriminatory housing/credit ad delivery, and it strips out the exact levers you asked for:

- **No age targeting.** Your 28–50 narrowing isn't available on a Credit-flagged campaign.
- **No standard Lookalike Audiences.** Meta disabled 1%-style Lookalikes for Special Ad Category campaigns; you get **Special Ad Audiences** instead — a lookalike-style tool deliberately built to _not_ weight on signals correlated with protected classes.
- **No ZIP-radius precision targeting.** Geo targeting for SAC campaigns is restricted to broader units (state/DMA-level, or a minimum ~15-mile radius) — not tight ZIP lists.
- **Detailed/interest targeting is limited.** A broad interest like "personal finance" is more likely to survive review than anything demographic-adjacent, but Meta's review is opaque and can reject it without full explanation.

Mis-flagging the campaign to dodge these restrictions is itself a policy violation with its own enforcement risk (account suspension, and it undercuts any argument that non-compliance was inadvertent).

## The plan I'd actually build

1. **Source audience:** Upload the 18,000-borrower list (hashed emails/phones via Meta's standard matching) as a Customer List custom audience. Confirm the list only contains customers who consented to marketing use of their data per your privacy policy / state law (CA, VA, CO, CT, UT all have relevant consumer privacy requirements).
2. **Expansion:** Build a **Special Ad Audience** off that source (not a 1% Lookalike) — this is the SAC-compliant substitute and the only expansion tool Meta permits for credit ads.
3. **Geography:** Target at the state level for every state Nestbird is licensed in (derive this list from your licensing team, not from ZIP centroids) rather than the 40-ZIP list. If you need finer geo, Meta's SAC minimum radius targeting can get closer than state-level without dropping into ZIP-code precision.
4. **Interest layer:** Keep "personal finance" as a broad interest if Meta's review accepts it on the SAC campaign; have a fallback of "no interest layer" ready since SAC review can reject even broad financial interests inconsistently.
5. **Age/gender:** None — not available, don't fight it.
6. **Exclusions — compliant version only:** Suppress existing Nestbird customers and anyone on your internal do-not-contact/opt-out list. That's it. No inferred-financial-health exclusion layer.
7. **Compliance sign-off:** Before launch, get written sign-off from whoever owns fair-lending compliance at Nestbird that the audience build (source list consent, SAC flagging, geo/interest choices) was reviewed. Keep that record — it's your defense if this ad set is ever examined.

I can build the actual Ads Manager audience spec (naming conventions, upload format for the customer list, SAC flag walkthrough) if that's useful — just not the exclusion layer as originally framed.
