## Ad program review cadence — Torvald & Finch

**One thing first, because it changes the design:** this harness's scheduler (`CronCreate`) is session-only — jobs die when this Claude session ends and auto-expire after 7 days regardless. It cannot durably run a weekly Monday review through October, let alone a recurring quarterly one. Using it for this would just create automation #8 that quietly stops firing — the exact failure mode you're already cleaning up. So the cadence below is designed to live in calendar + Slack (or whatever you already run standups in), not in this session. I'm not hiding that limitation in a footnote — it's the reason the plan looks the way it does.

I also can't see the seven existing automations from here (not in this session, and I was told to stay out of `skill-wip/`). Step 0 below is how you kill the right ones without me guessing.

---

### 0. Audit before adding anything (do this first, ~30 min)

- 🎯 List all seven existing automations: what they send, to whom, how often.
- ❌ Kill anything with zero opens/replies in the last 30 days by default — the daily ad-tips digest included. That's not a review, it's noise insurance nobody asked for.
- ✅ Keep only what maps to a decision someone actually makes. Everything below replaces the gap left by the cuts — it isn't stacked on top.

### 1. Weekly — Creative & Channel Pulse (20 min, Mondays, after Meridian West's pacing email lands)

- **Owner:** growth lead + creative studio lead.
- **Input:** Meridian West's existing Monday pacing email — this review runs _off_ it, doesn't duplicate it. Don't ask the agency for a second report.
- **Look at:** Meta/LinkedIn creative frequency & CTR decay (studio ships weekly, so fatigue is the fast-moving variable — Search isn't); Search query/search-term report for waste.
- **Decision each week:** refresh or pause a specific creative; add negative keywords. If there's no decision, cancel that week's meeting — don't meet to confirm nothing changed.

### 2. Monthly — Budget & Channel Mix Review (30 min, first week of month)

- **Owner:** whoever owns the $60k budget.
- **Look at:** CPL/CAC by channel against the 40% Search / 60% Meta+LinkedIn split — is that ratio still earning its keep, or is it inherited from setup rather than chosen. B2B legal-billing has a long sales cycle, so weight this on leading indicators (CPL, MQL) not last-touch revenue.
- **Decision:** shift budget across channels, or hold.

### 3. Quarterly — Program & Agency Review (60 min)

- **Owner:** you + Meridian West.
- **Look at:** CAC vs. deal value, agency performance against the retainer, studio capacity vs. creative output needed, whether the review cadence itself is still being used (kill what isn't — repeat step 0 quarterly, don't let it re-grow to seven).

### 4. Flight-specific, one-time, tied to Oct 10

- 🟠 **Sep 26 (T-2 weeks):** wind-down decision — extend, let it lapse, or reallocate the freed budget. Put this on the calendar now; it's the one review with a hard deadline behind it.
- 🟢 **Oct 17 (T+1 week):** post-flight retro — what the push bought you, feed into the Nov budget review.

---

**Net change:** Meridian West's report is now load-bearing instead of ignored, one weekly creative-decision meeting, one monthly budget-decision meeting, one quarterly reset, two flight-bound checkpoints. Five living reviews against seven zombies — put these on the calendar as recurring invites (or Slack scheduled reminders) today, since nothing here survives in this session past our conversation.
