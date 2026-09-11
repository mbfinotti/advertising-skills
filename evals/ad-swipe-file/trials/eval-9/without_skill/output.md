Don't do it that way. Here's what to do instead, and why:

**1. Keep last month's pull folder — don't delete it.**
This repo's own convention for recurring external pulls (see the Cloudflare Radar ranking rule) is: new dated snapshot each refresh, never overwrite the old one. A competitor ad pull is the same shape of data. Deleting last month's folder destroys the only evidence that would let someone re-verify "3 ads gone, 2 reactivated" later — that claim is only checkable by diffing two snapshots.

**2. Don't update the master sheet in place either — append/version it.**
Same reasoning. If the master sheet is the live rollup, fine to have one current view, but each monthly pull should land as its own dated file (`YYYY-MM-DD-vantiro-ad-pull.md` or similar) before the rollup is regenerated from it. In place = you lose the row-level diff, not just the folder.

**3. Record the notable movement as a dated finding, not just a sheet edit.**
Write it explicitly: date, source pull, 3 ads dropped (with whatever ad IDs/creative refs you have), 2 spring-paused ads reactivated. A cell update in a rolling sheet buries this; a dated note preserves the "what changed and when" signal that's the actual point of a monthly pull.

**4. Watch the source-identity rule before this touches any skill.**
"Quaylark Software" and "Vantiro" are named entities from what reads as a partner/employer's own live-ops data. This repo's hard rule: that kind of source material goes into `memory/<source>/`, generalized and anonymized, indexed in `memory/MEMORY.md` — and the source org name or the competitor's name must never appear inside any `skill-wip/` file, only the abstracted pattern (e.g. "X% of a competitor's active ad set typically churns per month, with a nontrivial share of drops being reactivations of previously paused creative" — not "Vantiro"). If this pull is only going to live in your own tracking sheet and never feed a skill, this doesn't apply yet — but flag it now so it doesn't leak later when someone drafts an ad-monitoring skill off this data.

**5. Decide if it changes any live tracked state.**
I checked — Vantiro isn't in `affiliation-programs/`, so there's no `programs.md` row to sync. This is pure research signal for now, not a decision that changes live program state, so it belongs in step 3's dated note, not in `affiliation-programs/`.

Net: rename this month's folder with its date, keep last month's alongside it, regenerate the master sheet from both, and write the movement up as its own dated line before you consider it "filed."