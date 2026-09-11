## Install it

I couldn't write directly into `~/.claude/skills/` from this sandbox — you'll need to run this yourself (the files are attached above, or grab them from the scratchpad path):

**`mkdir -p ~/.claude/skills/ppc-platform-watch && mv /tmp/claude-0/-home-user-skills-affiliation/7575e12d-9985-5af8-9526-441c7647c126/scratchpad/ppc-platform-watch/*.md ~/.claude/skills/ppc-platform-watch/`**

Once installed, say "ppc watch" or "what changed this week" in any Claude Code session to run it.

## The system: 3 layers, not 1 automation

Automation alone decays — nothing forces a decision on what it finds. This has:
1. **Capture** — the skill searches Google/Meta/Microsoft/LinkedIn/Amazon Ads for recent official changes, filters out noise, rates impact.
2. **Triage** — a fixed 20-min weekly slot (Monday, first thing) where you only look at High-impact items and decide: notify a client, act in-account, or ignore.
3. **Compound** — every kept item lands in `~/ppc-changelog/CHANGELOG.md`, a running table that doubles as searchable memory *and* client-facing proof you're actively monitoring their platforms.

Quarterly (2h), you do a deeper pass: read each platform's full update page for the quarter (weekly search is deliberately shallow), catch what was missed, renew lapsing certs (Google Ads certs expire yearly), and re-check whether your Tier-1/Tier-2 platform split still matches your actual client mix.

No URLs are hardcoded anywhere — platform blog slugs get reshuffled on redesigns, so the skill re-resolves each source by name via search every run instead of trusting a stored link that might already be dead.

## `SKILL.md`

```markdown
---
name: ppc-platform-watch
description: Monitor PPC ad platform changes across Google Ads, Meta, Microsoft, LinkedIn and Amazon Ads, then emit a weekly digest and append to a running changelog — use for "check platform updates", "ppc watch", "what changed this week", ad platform changelog, policy or algorithm update tracking.
---

# PPC Platform Watch

## Platform tiers

Tier-1, always searched:

- Google Ads
- Meta Ads
- Microsoft Advertising
- LinkedIn Ads
- Amazon Ads

Tier-2, opt-in — search only when the user names them or an active client spends there:

- TikTok Ads
- Pinterest Ads
- Snapchat Ads
- Reddit Ads
- X Ads

Edit both lists directly when the client mix changes. A platform with no active client produces noise the consultant learns to skip, and skipping becomes the habit.

## Workflow

1. Read `~/ppc-changelog/CHANGELOG.md`. Create the directory and the file from `CHANGELOG-template.md` when absent.
2. Take the newest date already logged as the lower bound. Default to 14 days back when the log is empty.
3. Confirm the Tier-2 list with the user only when the invocation is ambiguous. Otherwise run Tier-1 alone.
4. Run one WebSearch per platform: platform name plus `official`, plus `update`, `changelog`, `policy` or `announcement`.
5. Add a recency term to every query — the current month and year, or `last 7 days`.
6. Resolve every source from search results. Never reuse a remembered URL.
7. Drop items matching the discard rules. Keep items matching the keep rules.
8. Deduplicate against existing rows by platform plus change summary.
9. Rate each kept item High, Medium or Low on the impact scale.
10. Append one table row per kept item to `~/ppc-changelog/CHANGELOG.md`.
11. Emit the digest, High items first, capped at ten bullets.
12. Name every platform that returned nothing new, in one closing line.

Platform blog slugs move on every redesign, so a hardcoded URL rots silently and a dead link discredits the whole log.

## Keep rules

- Bidding, auction or algorithm changes
- New, changed or deprecated ad formats
- Policy, compliance or advertiser-verification changes
- Tracking, measurement, attribution or conversion API changes
- Reporting, scripts or public API breaking changes
- Account structure, campaign type or forced-migration deadlines

## Discard rules

- Cosmetic UI restyling with no workflow consequence
- Regional rollouts outside the consultant's client markets
- Case studies, award announcements, event promotion
- Third-party posts restating an announcement already logged
- Betas closed to new advertisers

## Impact scale

- **High** — requires client notification or account action within days
- **Medium** — worth knowing, no immediate action
- **Low** — FYI, context only

Rate for a solo consultant running SMB and mid-market accounts. Enterprise-only changes rate Low however loudly the platform announces them.

## Changelog row format

Append to the table in `~/ppc-changelog/CHANGELOG.md`:

```
| YYYY-MM-DD | Platform | Change in one line | High/Medium/Low | Source name | Y/N — one-line note |
```

- Date: the announcement date, not the run date
- Change: one line, no marketing adjectives
- Source: publication name only, never a URL
- Client action: `Y` or `N`, then one line naming the affected client type

## Digest format

- Cap at ten bullets
- Order High, then Medium, then Low
- One line per item: platform, change, impact, action
- Close with the platforms that returned nothing
- Size for a twenty-minute read, decisions included

## Constraints

- Never invent a change, a date or a source
- Never output a URL for a platform blog or changelog
- Report an empty platform as empty
- Stop at ten bullets even when more were logged, and state how many were logged
```

## `PLAYBOOK.md`

```markdown
# PPC Platform Watch — Playbook

## Three layers

1. **Capture** — the `ppc-platform-watch` skill searches, filters, rates and logs.
2. **Triage** — a fixed 20-minute weekly slot turns logged items into client decisions.
3. **Compound** — the changelog accumulates into a searchable record and client-facing proof.

Automation alone decays because nothing forces a decision. The fixed slot is the part that survives a busy quarter; the log is what makes month eleven cheaper than month one.

## Weekly ritual — 20 minutes

Slot it Monday first thing, before client work claims the day. A slot tied to a weekday survives; a slot tied to "when I have time" does not.

1. Invoke `ppc-platform-watch` (say "ppc watch" or "what changed this week").
2. Skim High items only. Ignore Medium and Low on the first pass.
3. For each High item, name the affected clients out loud or in the log.
4. Decide one of three outcomes per client: notify, act in-account, or ignore.
5. Draft notification lines for clients needing one — two sentences each, no jargon.
6. Queue in-account work into the normal task list with a deadline.
7. Skim Medium items for sixty seconds. Skip Low entirely.
8. Confirm the changelog rows landed, and fix any wrong impact rating.
9. Stop at twenty minutes. Unfinished items wait for next week.

- Cap the client-notification step at five clients per week.
- Write "no action" explicitly rather than leaving a row undecided.
- Treat an empty week as a valid outcome, not a failed run.

## Quarterly recertification — 2 hours

Weekly search coverage is shallow by design; the quarterly pass is where anything the searches missed surfaces.

1. Open each Tier-1 platform's official update page and read the full quarter.
2. Compare against the changelog and add every missed item, backdated.
3. Re-rate any item whose real-world impact differed from the original rating.
4. Renew expiring platform certifications — Google Ads certifications lapse annually.
5. Rebuild the Tier-1 and Tier-2 lists from the current client roster.
6. Drop any platform with no active client; promote any Tier-2 platform that gained one.
7. Update the source list below when a publication dies or a better one appears.
8. Export or summarise the quarter's High items into a one-page client-facing note.

- Book it as a calendar event on the first working day of each quarter.
- Run it even when the weekly ritual was skipped for weeks — it catches up the backlog.

## Keeping the platform list honest

- Match tiers to spend, not to industry hype.
- Demote a platform the moment its last client account pauses.
- Promote a platform before the first campaign launches, not after.
- Cap Tier-1 at six platforms; more than that breaks the twenty-minute budget.
- Record each tier change in the changelog so the rationale survives.

## Sources by platform

Locate every source by name through search at run time. Platform blogs are re-slugged and merged regularly, so a stored URL is a future dead link — this is why the skill searches by name and why no URLs appear here.

**Google Ads**
- Primary: Google Ads Help > What's New
- Independent: Search Engine Land > PPC

**Meta Ads**
- Primary: Meta for Business news page
- Independent: Jon Loomer Digital

**Microsoft Advertising**
- Primary: Microsoft Advertising Blog > release notes
- Independent: Search Engine Roundtable

**LinkedIn Ads**
- Primary: LinkedIn Marketing Solutions Blog
- Independent: Search Engine Journal > PPC

**Amazon Ads**
- Primary: Amazon Ads Advertising API release notes
- Independent: PPC Hero

Cross-check a High-impact item against the independent source before notifying a client. Official pages announce intent; aggregators report the rollout actually landing.

## Scheduling the weekly run

Option A — Claude Code `/loop`:
- Run `/loop 7d ppc-platform-watch` in a session left open.
- Read the digest whenever the session is next opened.
- Accept that a closed laptop or ended session stops the loop.

Option B — calendar reminder:
- Create a recurring Monday event titled "PPC watch — 20 min".
- Open Claude Code and invoke the skill manually from the event.
- Keep the reminder even after the habit sets, as the recovery path after holidays.

Both produce the same digest. The choice is only whether a session stays open.
```

## `CHANGELOG-template.md`

```markdown
# PPC Platform Changelog

Running record of ad platform changes, appended by the `ppc-platform-watch` skill. Newest rows at the bottom.

Columns:

- **Date** — announcement date, not the date the run happened
- **Platform** — Google Ads, Meta Ads, Microsoft Advertising, LinkedIn Ads, Amazon Ads, or a Tier-2 platform
- **Change** — one line, no marketing adjectives
- **Impact** — High (client notification or account action within days), Medium (worth knowing, no immediate action), Low (FYI)
- **Source** — publication name only, no URL
- **Client action** — `Y` or `N`, then one line naming the affected client type

This file doubles as client-facing proof of active monitoring, so keep every row defensible and never backfill a change that was not published.

| Date | Platform | Change | Impact | Source | Client action |
| --- | --- | --- | --- | --- | --- |
```

**One caveat**: the source names in the playbook (e.g. "Jon Loomer Digital", "PPC Hero") are from memory, not verified live — web search was unavailable in this sandbox. Sanity-check that list once before relying on it; everything else (the skill's search-by-name approach, the ritual, the changelog format) doesn't depend on those specific names being current.