## Diagnosis

Two separate problems, both covered by the skill's Labelling and Traceability rule:

1. **Fragmented reporting** — `Sleep_Cool_V1` / `sleep_cool_v1` / `sleep-cool-v1` are one variant, but because the ad platform name, tracking parameter, and analytics label were each typed by a different person, casing and separators drifted. GA4 (and most analytics tools) treat differently-cased or differently-separated values as distinct rows — that's exactly the failure mode the skill calls out.
2. **A new angle wearing a version number** — `sleep_cool_v2` is not a V2 of anything. Per the skill: _"v2, v3 are wording iterations of that same angle after it wins — never new angles. A new angle gets a new ID at v1."_ Hotel-quality luxury positioning argues a different thing (aspirational status/identity) than cooling technology (mechanism/pain). Naming it `_v2` will make your reporting silently blend two unrelated angles' results into one "campaign," and hide the fact that a new angle was even tested.

## The fix: one ID, one glossary, three mirrors

**Rule going forward:** every variant gets one stable ID, built as `<angle>_<awareness>_<seq>_v<N>` — lowercase, underscore-separated, no other punctuation. That exact string is pasted, unedited, into all three places: the ad platform name, the click-tracking parameter, and the analytics label. One person signs off on the ID before it goes live in any of the three systems — that's the actual root cause here (three people, three independent naming decisions).

**Awareness-stage codes:** `ua` unaware / `pa` problem-aware / `sa` solution-aware / `pra` product-aware / `ma` most-aware.

## Corrected IDs

| Ad                            | Angle family                                                                                 | Why this family                                                                                | ID (canonical — use everywhere) | Human name (free to change)      |
| ----------------------------- | -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------- | -------------------------------- |
| Original "sleep cool" ad      | **mechanism** — "here's why this works" (cooling fabric technology solving overheated sleep) | Names _how_ the product solves the problem, not just the felt pain                             | `mechanism_pa_01_v1`            | Cooling fabric mechanism         |
| New "hotel-quality luxury" ad | **identity** — "this is what people like you use"                                            | Aspirational/status positioning is a different reader motivation entirely, not a wording tweak | `identity_sa_01_v1`             | Hotel-quality luxury positioning |

⚠️ **Open item — confirm before you launch, don't guess:** I assigned awareness codes (`pa` for the cooling ad, `sa` for the luxury ad) as a reasonable placeholder based on what you've described, but I wasn't given your actual audience/targeting data for either ad. Per the skill's grounding rule, I won't fabricate that — swap the code if it's wrong; nothing else in the ID scheme changes.

## Rename mapping (apply identically in all three systems)

| System             | Old value                  | New value            |
| ------------------ | -------------------------- | -------------------- |
| Ad platform name   | `Sleep_Cool_V1`            | `mechanism_pa_01_v1` |
| Tracking parameter | `sleep_cool_v1`            | `mechanism_pa_01_v1` |
| Analytics label    | `sleep-cool-v1`            | `mechanism_pa_01_v1` |
| Ad platform name   | _(new ad's current name)_  | `identity_sa_01_v1`  |
| Tracking parameter | _(new ad's current param)_ | `identity_sa_01_v1`  |
| Analytics label    | _(new ad's current label)_ | `identity_sa_01_v1`  |

Also rename `sleep_cool_v2` → `identity_sa_01_v1` wherever it currently lives — it was never a version of the cooling ad and should stop reporting as one.

## Historical data note

Your three existing `sleep_cool_v1`-family rows already collected spend/CTR/conversions under three different labels. Before you evaluate that test's results, reconcile those three rows into the new canonical `mechanism_pa_01_v1` in your analytics tool (sum, don't just relabel one and discard the others) — otherwise the test looks like it underperformed when it was really just split three ways.

## Handoff block (keep this with your matrix)

- **Naming/tracking glossary:** lowercase, underscore-separated, `<angle>_<awareness>_<seq>_v<N>`, one approver before any new value ships.
- **Rejected/retired name forms:** `Sleep_Cool_V1`, `sleep_cool_v1`, `sleep-cool-v1`, `sleep_cool_v2` — all retired, mapped above. Log this so nobody reintroduces title-case or hyphens next round.
- **Next new angle** (whatever comes after luxury) gets its own `<angle>_<awareness>_01_v1` — it does not become `_v3` of either existing ad unless it's a wording rewrite of an angle that already won.
- For sizing/duration/significance on the next round, that's `ad-creative-test-plan`, not this cleanup.
