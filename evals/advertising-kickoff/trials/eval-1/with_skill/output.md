A few things before the actual kickoff content — worth flagging up front, then the deliverable follows.

**ℹ️ Repo check:** I looked for the README and `docs/media-plan-draft.md` you mentioned. This sandbox only has access to `/home/user/skills-affiliation`, and that repo is your affiliate-program knowledge base for Claude skills — unrelated to Fernhollow, no invoicing-SaaS README, no `docs/` folder, no `advertising-context.md`. If this is meant to run inside Fernhollow's actual repo, point me at it next time so I read the files directly instead of working from what you typed. For this session I'm treating the facts you stated inline as the detected content, which is enough to skip two interview questions below.

---

## Advertising kickoff — Fernhollow

**Cold start confirmed** — no `advertising-context.md` anywhere in the accessible repo.

**Detected from what you already told me** (skipping these, not asking again):
- Business model → B2B, mixed: self-serve ($49/mo) + sales-assisted enterprise tier
- ICP → bookkeepers, 5–50 person firms
- Channels + spend band → Google Search + LinkedIn, ~$8k/month on Google (that's the "$5k–50k" band)

**Still open** (this is the capped, one-at-a-time interview — 5 questions left, max):
1. Session goal
2. Conversion event + source of truth
3. Hard constraints / landing date
4. One-off vs. compounding + effort ceiling
5. Decided vs. open items

### What to do first

Answer this one:

**What's the goal of *this* session** — is it the same as the project's overall goal of "take paid ads seriously," or something narrower (e.g. just get LinkedIn live, or get a measurement baseline before spending more)?

I'm asking this one alone, not the whole list — that's deliberate, so you're tapping through one decision at a time rather than filling a form.

### Draft context artifact (not yet written to disk)

```markdown
# Advertising context

- **Updated**: 2026-09-12 (session 1)
- **Business model**: B2B, mixed — self-serve ($49/month) plus a sales-assisted enterprise tier
- **Offer / price point**: invoicing SaaS; $49/month self-serve; enterprise tier price TBD
- **ICP**: bookkeepers at 5-50 person firms
- **Channels / spend**: Google Search + LinkedIn; Google ~$8k/month (established); LinkedIn spend band TBD
- **Conversion / source of truth**: TBD — open interview question
- **CAC-ROAS position**: not yet established
- **In-flight work**: TBD — pending session-goal answer
- **Decided**: none yet — first session
- **Open**: session goal; conversion source of truth; constraints/date; effort ceiling; enterprise-tier price; LinkedIn spend band
- **Constraints**: TBD
- **Horizon / effort ceiling**: TBD
- **Stakeholders**: growth lead (you) — decides; others not yet named

## Session log
- 2026-09-12 - kickoff started, cold start - mbfinotti/advertising-skills@advertising-kickoff - detection from stated facts; interview in progress
```

Tell me where your actual Fernhollow repo root is (or confirm this sandbox is it) and I'll write this file for real, then patch it as your answers come in — never rewriting it wholesale.

### One thing already worth knowing

Your conversion source of truth is unconfirmed — that alone pins **measurement integrity** (`mbfinotti/advertising-skills@ad-conversion-tracking` or `mbfinotti/advertising-skills@ad-attribution-gap`) at the top of whatever short-list comes out of this, regardless of what else you tell me. Worth having that answer ready: is it the platform pixel, an analytics tool, or your CRM/billing system (Stripe?) that's authoritative for "this became a paying customer"?

Once you answer the session-goal question, I'll ask the remaining 4, then deliver the full route + ranked short-list + routine proposals in one pass.