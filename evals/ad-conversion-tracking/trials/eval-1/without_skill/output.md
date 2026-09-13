I can't sign that line off yet — "No recent conversions" is the actual problem, not a side detail explained away by "we haven't launched."

**Why this is a real red flag, not noise**

Google Ads conversion actions can show "No recent conversions" for two very different reasons:

1. **Benign**: the tag genuinely hasn't fired yet because there's no traffic (plausible if the site is pre-launch, no ads running, low organic volume).
2. **Broken**: the tag _looks_ installed but isn't actually firing/recording — wrong trigger, GTM published to a different environment than the live site, a consent-mode block, a URL-match condition that doesn't match the real confirmation page, duplicate/old tag interfering, or the page never actually loads in a real user flow (e.g., redirect changes, form JS error only in prod).

Tag Assistant showing "green" only proves the tag _fires when you manually trigger it in test mode on that page_. It does **not** prove:

- The tag fires the same way for real users (ad blockers, consent banners, different browsers).
- The confirmation page is actually reached in the real conversion flow (not just loaded directly by URL).
- The conversion is being recorded server-side by Google (network/console errors can block this silently).
- GTM/gtag changes were actually **published**, not just saved as a draft version.

Given this is a **$38k/month** budget and Target CPA / Smart Bidding will lean entirely on this one conversion action being accurate from day one, an unverified tracking pipeline is a high-blast-radius risk: broken tracking here doesn't just lose a few conversions, it can make automated bidding optimize toward the wrong signal or waste budget with no feedback loop for days before anyone notices.

**What "verified" looks like — pick at least one, ideally two:**

- **Send one real test conversion end-to-end**: submit an actual demo request through the live site (not a direct hit on the thank-you URL), then confirm it appears in Google Ads under Conversions → Demo Request within 24h (Ads conversions are not instant — allow up to a day).
- **Cross-check in GA4** (if linked): confirm the same event/session shows up as a conversion there too — a second independent system agreeing is strong evidence.
- **Check GTM publish status**: confirm the container version with this tag is the _live_ published version, not just saved in workspace.
- **Check for consent-mode gating**: if a cookie banner is in place, confirm the conversion tag isn't waiting on `ad_storage`/`analytics_storage` consent that most visitors won't grant in test conditions.

**Recommended checklist line:**

> 🔴 **Tracking — NOT verified.** Tag installed and configured correctly (Tag Assistant green, correct primary action). However, zero real conversions recorded since creation last Tuesday — this is expected only if there's been zero real traffic through the funnel; not yet confirmed. **Action before launch:** run one real end-to-end test conversion (not a direct URL hit) and confirm it lands in Google Ads Conversions within 24h. Sign-off pending that confirmation.

Once you run that real test and see the conversion register in the Ads UI, I'll happily sign off the line — that's a 10-15 minute check, not a blocker to Monday, but it's the one piece of evidence that's actually missing.
