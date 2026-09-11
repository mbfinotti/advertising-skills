# Fernhollow Petcare — Swipe File Read & Sprint Test List

## Scope note (assumptions, since not all interview fields were given)

- Competitors: 3 direct rivals, unnamed — tagged Rival A / B / C below. Channel, geography, and exact run dates weren't specified, so those fields are `unknown` rather than guessed, per the schema's hard rule.
- Spend tier and paid channel: not given — flagged `unknown`. Doesn't block hypothesis ranking, but you'll want it before sizing sample for the test plan.
- Decision context, effort ceiling, and mandate *were* given inline: no agency, no in-house editor, no hard deadline, and explicitly "a durable creative library, not a one-off" (compounding asset). That re-ranks the list below — noted where it applies.

## Competitor pulse — entries from this month's pull

| Field | Rival A | Rival B | Rival C |
|---|---|---|---|
| competitor_tier | direct | direct | direct |
| format | video, UGC-style testimonial | video, UGC-style testimonial | video, motion graphic |
| hook_type | proof-first (expert authority) | proof-first (expert authority) | countdown/gamified |
| concept | vet-testimonial endorsement | vet-testimonial endorsement | urgency/scarcity timer |
| longevity_signal | inference — active 40+ days | inference — active 40+ days | inference — pulled within ~2 weeks |
| variant_count | 4 concept variants | 3 concept variants | unknown, appears single-shot |
| confidence | high | high | medium (single advertiser, no repetition) |
| why_it_might_work | Hypothesis — vet authority lowers safety-purchase anxiety | Hypothesis — same insight | Hypothesis — urgency mechanic underperforms in this category |
| test_status | hypothesized | hypothesized | saved |

Provenance gap: `first_seen`, `last_seen`, `channel`, `placement`, `geography`, and `landing_destination` are all `unknown` for these three — the description you gave carries longevity and variant counts but not the underlying dated fields. Worth a rung-1 (surface, EU-filtered) or rung-3 (manual pull) pass next session to backfill dates and anchor the longevity read properly rather than resting on "40+ days" as reported.

**Deleted, not entered as a hypothesis:** the arthritis-reversal chew claim. Category rules forbid it outright — struck from the list per the skill's rule on permanently unproducible hypotheses, so it doesn't sit on the bench inflating the pipeline. `test_status: dropped`, reason: `category-prohibited health claim`.

## Reading the signals

- **Vet-testimonial concept**: cross-competitor repetition (2 of 3 direct rivals, independently) is the single strongest corroborator this file can produce — it can't be one advertiser's neglect. Stacked with variant duplication (3–4 variants each) and a 40-day run, confidence is high. It also **persisted at the top of last month's review and was skipped** — that's two consecutive sessions in the top band, which is one of the two explicit conditions the skill uses to promote a hard-to-produce hypothesis past the ratio.
- **Countdown-timer hook**: pulled inside ~2 weeks, on one rival only, no variant duplication. Under-14-days is the "testing, or failing" band — a soft negative signal, not proof, and it's uncorroborated (single advertiser). Read as "don't chase this," not as a test worth spending your only production hours on.
- **Picky-eater objection**: nobody in the category is running it. That's a gap, not a performance signal — no competitor has proven it converts. Worth naming honestly: this is the exact shape the skill warns about ("an untouched gap with no signal behind it is a guess with a hypothesis template wrapped round it").

## Ranked hypotheses

| # | Hypothesis | Signal | Gap | Ease | Value |
|---|---|---|---|---|---|
| H1 | We believe a vet-testimonial UGC concept will outperform our current creative on trust/safety objections, because 2 of our 3 direct rivals have run it 40+ days with 3–4 concept variants each, it topped last month's review too, and we've never tested testimonial anything. | 3 | 3 | 1 | 6 |
| H1b | We believe an ingredient/formulation-credential proof static (same "reduce safety anxiety" insight, no vet required) will beat our current creative while the vet deal is being negotiated, because it borrows H1's insight and ships from existing assets this week. | 2 | 3 | 3 | 5 |
| H2 | We believe a "picky eater" objection-first static will open an untapped angle, because no rival in the pulled set addresses it and we haven't either — flagged as a guess: no competitor has proven this converts, this is whitespace, not a signal. | 1 | 3 | 3 | 4 |
| H3 | We believe a countdown-timer urgency hook will underperform here, because the one rival who tried it pulled it inside two weeks — worth a cheap disconfirming test only if capacity ever frees up; not this sprint. | 2 | 3 | 3 | 5 (held, not queued) |

**H1 is explicitly promoted past its Ease=1 score.** Two separate promotion conditions both hold — say which: (a) it survived two consecutive sessions in the top band, and (b) you told me the mandate is a durable creative library, and the shoot you'd commission also produces reusable vet-authority footage for every later hypothesis in that family. Either alone would promote it; having both makes it unambiguous.

**H2 does not get promoted by the near-date exception** — you told me there's no hard deadline, so "shippable this week" alone doesn't buy it a top-band seat on value grounds. It moves up for a different, legitimate reason: no agency and no in-house editor means production capacity is tight, and the skill's guidance for that case is explicit — ship what you can while briefing the rest. So it's in this sprint's list, but labeled honestly as a low-confidence filler test, not a strong bet.

**H3 stays off the sprint.** With zero spare production capacity, spending it disproving a hook one rival already dropped is the wrong trade against sourcing a vet creator and shipping a static. Logged to the pattern library as a "don't chase" note, `test_status: saved`.

## This sprint's test list

1. **Start now, runs long: vet-testimonial UGC video** (H1). Kick off creator sourcing and rights negotiation immediately — this is the lead-time item, not a "later" item. Treat the shoot as building reusable authority-angle footage, not a one-off.
2. **Ship this week: authority/credential proof static** (H1b). Same underlying insight, no creator dependency — keeps the pipeline moving while H1's production track is in motion.
3. **Ship this week: picky-eater objection static** (H2). Cheap, fast, honestly labeled as a whitespace test — treat its result as a genuine new data point, not a confirmed opportunity, since nothing in the pulled data corroborates it yet.
4. **Held, logged, not tested: countdown-timer urgency** (H3). Revisit only if production capacity changes.
5. **Deleted:** arthritis-reversal claim — struck for category-rule violation, not benched.

## Compliance flags to carry into the brief

- **Vet testimonial (H1):** get real rights, not a recreation — script your own vet's own words, don't reproduce a rival's testimonial content or visual structure. Any vet-credential or health-adjacent claim in the ad needs substantiation and (in most jurisdictions) an endorsement/material-connection disclosure. This isn't legal advice — route the specific script and any comparative language to counsel before shooting.
- **Formulation-credential static (H1b):** same substantiation bar applies to any ingredient/efficacy claim, even without a vet on camera.
- **Arthritis claim:** already correctly killed by your own category rules — no further action beyond recording the deletion.

## Handoff

Ranked hypotheses stop here. Brief H1 and H1b through `mbfinotti/advertising-skills@ad-creative-brief`; size and sequence both (plus H2 if you want it as a genuine test rather than a filler) through `mbfinotti/advertising-skills@ad-creative-test-plan`.

## What to backfill next session

- Real dates (`first_seen`/`last_seen`) and channel/geography for Rivals A–C — currently inferred from your description, not observed directly. An EU-filtered surface pass would anchor the "40+ days" claim in actual data instead of a secondhand read.
- Advertiser identities, if you want the file queryable by name later.
- Spend tier, so the outcome gate (5–9% win rate band) means something once these tests report back.