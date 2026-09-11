# Meta Brief — Specs Section Review (Pattern & Pine)

## 🔴 Fix before sending

**"Text under 20% of image area or Meta throttles delivery"**
This is outdated. Meta retired the strict 20%-text delivery penalty in 2020 — the old grading tool (low/medium/high) no longer gates reach or cost. Sending this to the designer as a hard technical constraint will make them over-restrict layout for no reason.
- Replace the delivery-risk framing with a readability rule instead: keep text concise and high-contrast, since dense text still hurts CTR and gets flagged on Feed/Stories previews.
- Don't drop the caution entirely — just re-label it as a design best practice, not a platform penalty.
- I can't verify this against a live source right now (no web access this session) — before you ship the brief, have someone confirm current policy at the Meta Business Help Center rather than take my word for it.

**Safe zone: 250px top / 310px bottom on 9:16**
The asymmetry (250 vs 310) is plausible but suspicious as written — it reads like two different specs got merged.
- Meta's placements differ: Stories vs. Reels have different UI overlays (Reels adds caption + like/share/comment rail on the right and a larger bottom band for captions), so a single "9:16" number can be wrong for one of the two even if right for the other.
- Ask the media buyer which placements this creative actually runs in (Stories only? Reels too? Both?) and get per-placement safe-zone numbers instead of one blended rule — otherwise the designer is guessing which spec wins where they conflict.
- Flag this for verification the same way as the 20% rule — pixel specs are exactly the kind of thing Meta revises without much announcement.

## 🟠 Tighten before sending

**Style: "premium, aspirational, authentic"**
All three words are the most overused triplet in DTC furniture briefs — every competitor's brief says this too, so it gives the designer nothing to differentiate on.
- Attach 2-3 reference images (competitor ads, Pinterest board, or past Pattern & Pine creative you consider "on-brand") — adjectives without visual anchors get interpreted differently by every designer.
- If "authentic" means "not staged/showroom-glossy," say that directly — it's a specific art-direction instruction, not a vibe word.

**"9 do's and 7 don'ts from our brand book"**
Nothing pasted here actually reached me — only that count was mentioned in your message, not the list itself. I can't review content I don't have.
- Paste the actual 16 items and I'll check them for: contradictions between do's and don'ts, overlap/redundancy, and anything that conflicts with the safe-zone or style guidance above.
- Common failure mode worth checking once I see them: brand-book rules written for static Feed images don't always survive translation to 9:16 video/motion — worth a quick pass if any don'ts assume a static frame.

## ⚠️ Don't skip: the Midjourney disclosure question

"I assume that's nobody's business" — worth challenging before this goes out, on three separate grounds:

1. **The designer's business, practically.** They need to know the background plates are AI-generated regardless of any policy question — Midjourney output has known failure modes (warped geometry, inconsistent light sources, seam artifacts under close crop) that a designer will handle differently if they know going in vs. discover mid-composite. Withholding this just costs you a revision round.
2. **Meta's business, possibly.** Meta requires an "AI-generated" / "digitally created or altered" disclosure on ads for realistic synthetic content in specific categories (social issues, elections, politics) and is expanding disclosure expectations for photorealistic AI content more broadly. A furniture background plate is low-risk if it's inanimate (a room, a texture) — it gets materially riskier if the plates depict a photorealistic person, real-looking testimonial, or implied real setting. Worth a 5-minute check against current Meta ad policy for your specific plates rather than assuming exemption.
3. **Yours, legally.** Commercial use of Midjourney output requires a paid plan, and if Pattern & Pine (or its parent) has >$1M annual revenue, Midjourney's terms require the Pro/Mega tier specifically — confirm which plan generated these. Ownership/IP terms also vary by plan; if you plan to trademark or heavily reuse these plates, check the terms rather than assume.

Recommendation: add one line to the brief telling the designer the backgrounds are Midjourney-generated plates, not a disclosure decision — that's separate and worth 10 minutes with whoever handles paid-media compliance before the ad runs, not before the brief goes to the designer.

## Not flagged (looks fine as-is)
- Structuring the brief around style / safe-zone / brand rules is a sound shape for a designer handoff — no structural change needed there.

## What I need to finish this
Paste the actual 9 do's / 7 don'ts and tell me which placements (Stories, Reels, or both) this 9:16 export targets — I'll fold both into a redline of the rest of the section.