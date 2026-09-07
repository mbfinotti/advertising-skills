# Advertising agent skills

> A bunch of skills for spending paid media budget on purpose.

A collection of **agent skills for paid advertising**: channel selection, budget policy, audience design, creative development, and measurement, across search, paid social, video, native, and AI-answer surfaces.

Built for **media buyers, performance marketers, PPC specialists, and growth leads** running real budgets in B2B and B2C.

## Install

Install every skill in this repo, not just one. Skills here are atomic by design and reference each other freely — picking a single skill leaves its sibling skills uninstalled, so cross-references and routed handoffs go nowhere.

**skills.sh (universal)** — works with any Agent Skills-compatible tool:

```bash
npx skills add mbfinotti/advertising-skills
```

**Claude Code** — install the plugin:

```bash
/plugin marketplace add mbfinotti/mbfinotti
/plugin install advertising-skills@mbfinotti
```

**Codex (OpenAI)** — install via the Codex CLI:

```bash
codex plugin add github:mbfinotti/advertising-skills
```

**Cursor** — copy into Cursor's skills directory:

```bash
git clone https://github.com/mbfinotti/advertising-skills.git ~/.cursor/skills/advertising-skills
```

Cursor auto-discovers skills from `.agents/skills/` and `.cursor/skills/`.

**Gemini CLI** — install as a Gemini extension:

```bash
gemini extensions install https://github.com/mbfinotti/advertising-skills
```

Update with `gemini extensions update advertising-skills`.

## Skills

This collection covers the full advertising surface. Start here:

- [`advertising-kickoff`](./advertising-kickoff) — Routes a paid advertising task to the right skill in this collection and bootstraps a shared project context artifact reused across sessions.
- [`advertising-career`](./advertising-career) — Plans a paid media career from the candidate side — the junior-to-lead ladder, interview formats, an NDA-safe portfolio, and pay conversations.
- [`advertising-hiring`](./advertising-hiring) — Builds the employer-side hiring packet for a paid advertising role — outcome scorecard, interview loop, work sample, and a 30-60-90 ramp.
- [`advertising-radar`](./advertising-radar) — Assembles a time-budgeted watch list of newsletters, podcasts, platform release notes, communities, and people, with a method for keeping it fresh.

Browse all skills and their descriptions in [`references/skill-catalog.md`](./references/skill-catalog.md).

## Related Collections

Other Nativa Labs skill repositories:

- [`partnerships-skills`](https://github.com/mbfinotti/partnerships-skills) — Partner ecosystem operations — _for partner managers, BD leads, ecosystem heads_
- [`revops-skills`](https://github.com/mbfinotti/revops-skills) — Revenue operations — _for RevOps managers, sales ops, marketing ops, CRM admins_
- [`sales-skills`](https://github.com/mbfinotti/sales-skills) — Sales execution — _for SDRs, AEs, sales managers, heads of sales_

## License

MIT © 2026 Maya-Beth Finotti
