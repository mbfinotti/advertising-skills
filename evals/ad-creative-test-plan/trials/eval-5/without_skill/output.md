# Brightlark — New-Ad Kill Rules (6-ad batch, launching Monday)

**Context:** CPA target $30 · ~$18k/mo account spend · solo operator, checks ~2×/week · winning batch locked in 4 weeks for App Store feature window.

## Confirm before Monday
- Assuming test budget ≈ $20–30/day per ad (6 ads ≈ $120–180/day, ~$3.6–5.4k/mo of your $18k). Adjust if you want it tighter or looser.
- Rules below are **spend-milestone-based**, not calendar-based — they work regardless of your exact budget split.
- Which platform(s)? Rules are written generically (Meta / Google UAC / Apple Search Ads / TikTok all support automated rules) — say which one(s) if you want exact click-paths.

## 1. Core rule table

| Spend vs. CPA target ($30) | Installs | Action |
|---|---|---|
| < 1× ($30) | any | **No judgment.** Sample too small — let it run. |
| ≥ 1× ($30) | ≥ 1 | Provisional read only. Watch CPA trend, don't act. |
| **≥ 2× ($60)** | **0** | **Hard kill.** Automated, no exceptions. |
| ≥ 3× ($90) | CPA ≤ $45 (1.5×) | Extend to 5× ($150) — it's trending toward target, give it room. |
| ≥ 3× ($90) | CPA > $45 | **Kill.** |
| ≥ 5× ($150) | CPA still > $30 | **Kill**, regardless of trend. Hard ceiling. |

This is Barry Hott's 1×/3× framework plus two additions you asked for: a zero-install hard stop at 2×, and a bounded extension (capped at 5×) for ads that are clearly converging on target instead of a binary miss.

**Why 2× with zero installs is a legitimate hard rule, not just paranoia:** if an ad were actually performing at your $30 target, spend of $60 implies an expected 2 installs (Poisson, λ=2). Getting exactly zero at that point has ~13.5% probability of still being a fair ad — not proof, but a strong enough smell to cut given you're not staring at the dashboard daily. At $90 (3×, λ=3), zero installs has only ~5% probability of being a fair ad — that's Hott's threshold and it's solid. The 2× rule exists to catch obvious duds ~33% earlier, which matters because you check twice a week, not continuously.

## 2. Automated backstop (do this Monday, before ads go live)

Set platform-native automated rules so losers get paused without you watching:

1. **Rule A — Hard kill:** IF spend ≥ $60 AND installs = 0 → pause ad.
2. **Rule B — 3× kill:** IF spend ≥ $90 AND cost-per-install > $45 → pause ad.
3. **Rule C — Ceiling:** IF spend ≥ $150 AND cost-per-install > $30 → pause ad.
4. **Rule D — Notify only:** IF spend ≥ $30 (1×) → email/push notification, no action. This is your cue to glance at it on your next check, not a trigger.

Notes:
- Meta Ads Manager and Google Ads (UAC) both support spend + CPA compound conditions natively under "Automated Rules" — set frequency to check every few hours, not daily, so you're not exposed on the days you don't log in.
- Apple Search Ads and TikTok have thinner native rule engines — if you're on either, set Rule D notifications and treat A–C as manual actions to execute on your twice-weekly check (budget caps at the campaign level as a partial substitute for A/C in the meantime).
- These rules are a **floor**, not a replacement for your judgment on the trend-extension case (3×–5× zone) — that one stays manual since it needs a look at creative/CTR context.

## 3. Your twice-weekly checklist

1. Pull spend + installs per ad since last check.
2. Flag anything that crossed a threshold since last visit (rules 1–4 above already acted on most of it — you're auditing, not firing in real time).
3. For anything in the 3×–5× extension zone: eyeball CTR and install trend line — accelerating or flat? Keep or kill.
4. Reallocate budget from killed ads into surviving ads same day — don't let dead budget sit idle, you have 4 weeks.
5. Log the check (see template below) — 2 minutes, keeps your kill decisions auditable when you pick the final batch.

## 4. 4-week timeline

| Week | Target state |
|---|---|
| 1 | Most ads cross 1×–3× spend. First kills land (mostly via automation). |
| 2 | Survivors pushed toward 5× ceiling. Clear losers all gone by end of week. |
| 3 | Only real contenders left. Scale winners' budget up for volume. |
| 4 | **No new kill decisions** — this week is for confirming the pick has enough volume, not for testing. Lock the batch with margin before the feature-window deadline, don't cut it to the wire. |

## 5. One caveat on picking the final winner

CPA alone tells you acquisition cost, not whether those users convert to paying subscribers. Before locking the App Store feature pick, pull trial-start rate or D7 retention (whatever's available in your subscription funnel) for the surviving ads — a $25 CPA ad feeding low-intent users can lose to a $32 CPA ad with better downstream conversion. Use CPA as the kill filter (per above), but let LTV signal break ties among survivors, not raw CPA rank.

## 6. Tracking log template

| Ad | Launch date | Spend | Installs | CPA | Threshold hit | Action | Date |
|---|---|---|---|---|---|---|---|
| Ad 1 | Mon 9/15 | | | | | | |
| Ad 2 | Mon 9/15 | | | | | | |
| Ad 3 | Mon 9/15 | | | | | | |
| Ad 4 | Mon 9/15 | | | | | | |
| Ad 5 | Mon 9/15 | | | | | | |
| Ad 6 | Mon 9/15 | | | | | | |