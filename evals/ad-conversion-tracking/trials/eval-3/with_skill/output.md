# Pre-Launch Tracking Verification — Brindlewick Outdoor Gear

## 1. The gap math, run against actual thresholds (not "must match")

| Comparison            | Values     | Gap   | Skill threshold                                      | Read                                           |
| --------------------- | ---------- | ----- | ---------------------------------------------------- | ---------------------------------------------- |
| Google Ads vs GA4     | 412 vs 486 | 15.2% | Platform-vs-analytics: 10–20% is normal              | 🟢 Within band                                 |
| GA4 vs backend        | 486 vs 502 | 3.2%  | Analytics-vs-backend: <25% healthy, >35% investigate | 🟢 Healthy — GA4 is basically tracking reality |
| Google Ads vs backend | 412 vs 502 | 17.9% | (diagnostic — backend is ground truth)               | 🟠 This is the real number to close, not GA4   |

**The CMO's "hold until they match" bar contradicts the benchmark this space runs on.** A 10–20% platform-vs-analytics discrepancy is structural — cookie loss, attribution-window mismatch, iOS/Safari ITP, consent differences between tags. Ruler Analytics' own guidance, and this skill's own failure-mode list, calls chasing a zero gap explicitly out: _"spending the pre-launch window eliminating it delays launch for nothing."_ At 15.2%, Google Ads vs GA4 is inside that band already. Asking for parity is asking for a number that healthy setups don't produce.

**What actually deserves attention:** GA4 (486) sits almost exactly on backend truth (502, 3.2% off — that residual is likely just refunds/cancellations/test orders, not a tracking defect). Google Ads (412) is the outlier, under-capturing ~18% of real orders. So the fix target isn't "make Google Ads = GA4," it's "find why Google Ads is undercounting against reality" — closing that closes the GA4 gap as a side effect.

## 2. Your dedup evidence doesn't answer this question

Two problems with citing the 9.1/10 match quality score as proof dedup is solid:

- **Wrong metric, right platform or not.** Event Match Quality (Meta Events Manager) measures how well hashed customer data matches Meta's identity graph — payload _completeness_, not measurement _accuracy_. Per this skill's own ranking, match quality is the least useful of the three dedup confirmations and should never stand in for the dedup rate. A duplicated event can score a beautiful EMQ.
- **Wrong platform, full stop.** EMQ is a Meta number. It says nothing about Google Ads' conversion tag, GA4's event stream, or the relationship between them. There is no cross-platform signal here at all — this is the "reading match quality as accuracy" failure mode, plus a category mismatch on top of it.

If you want Meta's own dedup confirmed, pull the actual **dedup rate** in Events Manager (target ~90%+) — but that's a separate check from the Google/GA4 question and doesn't move this gate.

## 3. What actually needs verification before scaling

The aggregate gap sitting in a "normal" band doesn't prove the setup is clean — it just means you don't need to force it to zero. You still owe the sequence real evidence on Google Ads, since that's the underperforming source:

| #   | Check                                                       | Result     | Evidence needed                                                                                                                                                                                                                                                       |
| --- | ----------------------------------------------------------- | ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Settings — primary conversion action = Purchase, count-once | ❓ unknown | Confirm no secondary/micro-actions marked primary                                                                                                                                                                                                                     |
| 2   | Tag debug/preview                                           | ❓ unknown | Google Ads Tag Assistant / GTM preview, live site (not preview-only)                                                                                                                                                                                                  |
| 3   | Real test conversion, click ID (`gclid`) present end to end | ❓ unknown | Place a low-value test order from a real Google Ads click; capture the order ID                                                                                                                                                                                       |
| 4   | Payload inspection                                          | ❓ unknown | Confirm `transaction_id`, value, currency in the network request                                                                                                                                                                                                      |
| 5   | Platform UI status                                          | ❓ unknown | Conversion action status = "Recording conversions," not "No recent conversions"/"Needs attention"                                                                                                                                                                     |
| 6   | Consent path — accept AND reject                            | ❓ unknown | Run test order on both paths; Google's tag is often the one silently dropped under Consent Mode, while GA4 keeps firing (analytics_storage granted, ad_storage denied) — this is the single most likely explanation for GA4 tracking near-perfectly while Ads doesn't |
| 7   | Click-identifier persistence                                | ❓ unknown | Check that `gclid` survives your checkout redirect chain and any cross-domain hop                                                                                                                                                                                     |

Per this skill's evidence gate: none of these clear on a settings screenshot alone. `unknown` is not `pass`.

## 4. Ranked hypotheses for the Google Ads under-count (18% vs backend)

Ordered by what's cheapest to check first, given GA4 is already clean (so the drop is Ads-specific, not a shared tag/event problem):

1. **Consent Mode asymmetry** — ad_storage blocked while analytics_storage allowed. Near-zero effort to check (run the reject-path test), but a legal-sign-off item if you need to change it.
2. **Google Ads conversion action status** — check for "Needs attention"/limited status in the UI. Near-zero effort.
3. **Attribution/conversion window mismatch** — if the window is set shorter than your typical click-to-purchase lag, late conversions land in GA4 (which isn't gclid-gated the same way) but miss the Ads window.
4. **gclid loss in the redirect/checkout chain** — cookie caps, a tracking redirect, or a cross-domain checkout hop stripping the click ID before it reaches the order. A week-of-dev-effort item if confirmed — this is the one to risk-accept explicitly if the launch date is hard, not to silently drop.

Do **not** chase this by making Google Ads count more loosely (e.g., widening match/import rules) just to hit 486 — that manufactures the parity the CMO wants without fixing what's actually broken, and risks trading an under-count for the over-count failure mode (phantom conversions, bad bidding signal).

## 5. Decision

```
PRE-LAUNCH TRACKING VERIFICATION — Brindlewick Outdoor Gear, 2026-09-12
platform(s): Google Ads, Meta | funnel: B2C ecommerce | server-side: unknown — confirm
launch: soft-launch window, full launch pending | budget at risk: unknown — confirm

gap summary
  Google Ads vs GA4      : 15.2%  → 🟢 within normal 10–20% band, not a blocker
  GA4 vs backend          : 3.2%   → 🟢 healthy
  Google Ads vs backend   : 17.9%  → 🟠 real target — diagnose, don't force-match to GA4

DECISION: NO-GO on "numbers must match" as framed — that bar is wrong.
          GO is reachable once steps 1–7 above return real evidence for
          the Google Ads tag specifically (consent path first).

blockers   : none confirmed yet — open items above are unverified, not failed
deferred   : click-identifier chain across checkout, pending a hard/movable
             launch-date call — risk-accept in writing if the date is fixed
deleted    : none yet — no constraint has ruled anything out
re-verify  : steps 3–6 on Google Ads (real test order, both consent paths)
             before reporting back to the CMO
approver   : <name>    date: <TBD>
```

## 6. What to tell the CMO

Reframe the ask: not "make Google Ads and GA4 match" (they structurally won't, and forcing it wastes the launch window), but "confirm Google Ads isn't under-reporting for a fixable reason." GA4's 3.2% gap to backend is your real signal that tracking works — Google Ads' 18% gap to the same backend is the one open question, and Consent Mode is the first thing to rule out.
