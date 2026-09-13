# Kindra Systems — Buying Committee Map for ABM (6-Week Build)

## The core problem with your plan

Your three inputs land in the wrong order for a 6-week launch:

- **Intent feed** tells you which accounts are in-market and sometimes who at the account is engaging with content — it does not tell you who is _on the committee_ or what role they play. Treat it as a targeting signal, not a committee-mapping source.
- **15 interviews** won't return usable data before your ads go live next quarter. They're a v2 validation loop, not v1 input.
- **72 deals with clean stage history + call recordings** is your only source that can ship a committee map in 6 weeks. Everything else is confirmation, not construction.

Build v1 from the CRM + calls now. Launch on it. Use the interviews and the intent feed to correct it in ~90 days.

---

## Step 1: Mine the 72 deals for committee structure (Weeks 1–2)

For each of the 42 won and 30 lost deals, extract from CRM activity + call transcripts:

| Field                                                                                                           | Source                                     |
| --------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| Every contact who attended ≥1 call, was CC'd on a stage-changing email thread, or is listed on the opportunity  | CRM contact roles + call attendee lists    |
| Job title as stated on the call (not just CRM title field — CRM titles are stale/wrong often)                   | Transcript, first 2 minutes of intro calls |
| Which stage each person first appeared (discovery, demo, security review, procurement, contract)                | Stage history + call date correlation      |
| Who asked pricing/ROI questions vs. security/compliance questions vs. implementation/data-integration questions | Transcript content                         |
| Who signed, and who is listed as the internal champion in rep notes                                             | CRM opportunity fields, rep notes          |

Have a rep or ops analyst listen to/skim transcripts (or run them through your call-recording tool's AI summary if it extracts speaker titles) — don't try to do this by hand across 72 deals in week 1. If you have Gong/Chorus/similar, use its speaker-role tagging and topic filters (pricing, security, competitor mentions) to shortcut this.

**Output of this step:** a flat table, one row per person per deal, with title, department, stage-of-first-appearance, and topic-focus.

## Step 2: Roll up into a role taxonomy (Week 2)

For workforce-analytics into 500–2,000-employee healthcare orgs, expect a committee that clusters into roughly these functions — confirm the exact titles from your own data rather than assuming:

- **Economic buyer** — typically CHRO/VP HR or CFO/VP Finance depending on who owns the budget line. At $90K ACV in healthcare, this is very likely a committee decision, not a single signer — check whether both show up.
- **Champion** — usually Director/Sr. Director of People Analytics, HR Ops, or Workforce Planning. The person who requested the tool and drives internal momentum.
- **Technical/security evaluator** — IT Security or Compliance, elevated in healthcare because of HIPAA/PHI-adjacent data handling even though workforce data isn't clinical PHI. This role often appears _late_ and correlates with deal velocity — check if its absence predicts losses.
- **End users** — HR Ops managers, People Ops analysts, sometimes department-level Ops leads. Rarely a blocker, but their sentiment on demo calls often predicts champion strength.
- **Procurement/Finance** — appears at contract stage in most $90K+ deals; look for whether procurement involvement correlates with longer cycles or lower win rate.
- **Compliance/Privacy officer** — healthcare-specific; check whether this role's presence (or a late-surfacing legal review) correlates with your 30 lost deals.

Build the actual table from your data, not this list — the value of the exercise is finding out, e.g., that your losses cluster around deals where security evaluation happened _after_ verbal commitment (re-litigating a decision) versus wins where it happened _during_ evaluation.

**Output of this step:** a Role × Deal-Stage × Won/Lost matrix — presence rate, average stage of entry, typical title variants, and topic focus per role.

## Step 3: Layer in closed-lost as a distinct signal (Week 2–3)

Don't just merge lost deals into the same taxonomy — pull out what's _different_:

- Which role shows up in lost deals that's _absent or minimized_ in won deals? (Common pattern: a security/compliance stakeholder surfaces late in losses and never gets addressed.)
- Which role is _missing_ in lost deals that's present in wins? (Common pattern: no identifiable champion, or champion outranked by a skeptical economic buyer who never got engaged directly.)

This gives you a second, more valuable output: not just "who's on the committee" but **which roles to prioritize in ad spend and messaging because their absence/lateness kills deals**, and which roles to pre-empt with security/compliance-specific creative before they become late-stage blockers.

## Step 4: Use the intent feed correctly (Week 3)

Once you have a role taxonomy with real titles from your own data, use the intent feed to:

- Check whether it's account-level only or contact-level (many "account-intent" feeds are account-level aggregate — confirm with the vendor before assuming you'll get named contacts and titles).
- If contact-level: cross-reference the titles/seniority it surfaces at your target accounts against your taxonomy — this tells you which roles are actively researching at specific target accounts _right now_, which is your targeting list, not your committee definition.
- If account-level only: use it purely for account prioritization/tiering, and target the roles from Step 2 via firmographic/title-based ad targeting (LinkedIn Campaign Manager job title + seniority + company size, not the intent feed) at those accounts.

Don't let the intent feed's coverage gaps quietly narrow your committee map — it will show you whoever happens to be active in a syndication network, which is a biased sample of your real committee.

## Step 5: Build the per-role messaging/targeting brief (Week 3–4)

For each role in your matrix, define:

- Ad platform + targeting parameters (title/seniority for LinkedIn; account list + role overlay for intent-based display)
- Message angle tied to what Step 1–3 showed they actually care about on calls (ROI/economic buyer, implementation risk/champion, HIPAA-adjacent data handling/security, ease-of-rollout/end-user)
- Sequencing — which roles get hit first vs. reactively (e.g., pre-empt the security stakeholder before late-stage review, since that's a loss pattern)

## Step 6: Launch, then correct with interviews (Week 5–6 and beyond)

Launch the campaign on the CRM/call-derived map. When the 15 interviews run next quarter:

- Weight them toward recent closed-lost deals — they'll surface objections and blockers your call recordings and CRM notes didn't fully capture (the reason a deal died is often _not_ said on a recorded call).
- Use won-deal interviews to sharpen champion narrative and internal-selling materials (the champion is usually the one who needs help selling internally — arm them).
- Treat the interviews as a 90-day correction to the map, not a delay to launch.

## One caveat to hold onto

72 deals split across ~5 committee roles is a thin sample once you cut it by role and by won/lost — patterns here are directional, not statistically robust. Don't over-fit ad targeting to a razor-thin distinction between two roles; group anything with fewer than ~8–10 data points into a broader bucket rather than treating it as a confirmed persona.
