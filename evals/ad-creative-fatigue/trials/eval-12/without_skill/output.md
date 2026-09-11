# Diagnosis: creative wear-out, not a tracking/audience/LP problem

The data pattern is textbook fatigue, and the metrics you listed happen to rule out every other explanation:

- **CVR steady** → people who click still convert the same. Landing page, offer, and audience quality are fine. This isn't a funnel problem, it's a top-of-funnel attention problem.
- **Hook rate down 24%** → people who've seen the video before are skipping it in the first seconds. That's the fingerprint of fatigue, not targeting drift.
- **First-time impression ratio 71%** → 29% of impressions are repeat views. With flat budget and clean change history, you're re-showing the same creative to a capped pool often enough that recognition (not disinterest in the offer) is killing hook rate.
- **Spend share falling with no manual change** → Meta's auction is already detecting the relevance decay and quietly de-prioritizing the ad. This is the algorithm agreeing with your diagnosis before you asked it to.
- **CPM in line, tracking reconciles, LP untouched, budget flat** → nothing external broke. This is the ad, specifically the video asset, wearing out on its own audience.

Conclusion: this is a **creative refresh problem**, not a targeting, tracking, or landing page problem. That matters because it tells you which of your constraints are actually irrelevant — the legal/audience-list block, for instance, doesn't matter here. You don't need a new audience, you need new (or refreshed) stimulus for the same one.

# What to do in the next 4 days

**1. Shift budget weight toward the static now, deliberately.**
Don't wait for the algorithm to keep bleeding spend away from the video — reallocate the split yourself within the existing total budget. The static is your only asset not showing fatigue; let it carry more of the load while you patch the video. This is the direct lever on blended CPL before the demo.

**2. Cap frequency on the video ad set, or lower its budget share, rather than pausing it.**
Pausing kills your only other live channel's diversification and resets delivery/learning. Throttling frequency (or letting the static absorb more spend) reduces repeat-impression fatigue without giving up the format entirely.

**3. Force a creative reset without new footage.**
You don't need a new video to reset the algorithm's freshness signal — you need a new *variant*:
- Swap primary text, headline, and CTA on the existing video. Meta treats copy changes as a distinct creative test and this alone often revives hook rate/CTR.
- Change the thumbnail/cover frame.
- If any alternate cuts, b-roll, or unused footage exist from the original shoot, do a quick re-trim (Ads Manager's built-in editor, or any freelancer, 24-48h turnaround) for a new opening 3 seconds — the hook is what's fatigued, so a new hook is the highest-leverage low-effort fix.
- Avoid spinning up a brand-new ad ID 4 days before a board readout — it re-enters learning phase and adds volatility right when you need stability.

**4. Do not touch the audience/list.**
Your diagnosis doesn't call for it (CVR is steady, 71% first-time ratio isn't alarming), so the legal blocker this month is a non-issue here, not a gap in your plan. Don't let anyone push you toward "just upload a new list" as a fix — it wouldn't address the actual cause.

**5. Start the agency clock today regardless.**
Five weeks won't help the demo, but the CEO's real ask is "get this moving," not "fix it in four days." Kicking off the agency brief now shows a real fix is in motion, separate from the stopgap. In parallel, get a short-term freelance editor (Upwork/Fiverr, 48-72h) for the hook re-cut in point 3 — cheaper and faster than the agency, and enough to buy weeks.

# What to tell the board

Frame it as caught-early, not broken: you identified creative wear-out via leading indicators (hook rate, CTR, delivery share) four weeks before it would have shown up in CPL or CVR, reallocated spend to the unaffected static ad to protect cost-per-lead, and already have a creative refresh in motion. That's a rigor story, not a fire drill — use the clean change history and stable CVR as the evidence.