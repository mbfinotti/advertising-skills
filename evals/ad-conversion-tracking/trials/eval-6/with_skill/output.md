## Short answer: No — this is not verified yet, and "Events Manager shows nothing" is not a detail to wave off.

What you ran was step 2 of a 9-step sequence (tag debug/preview) plus a partial step 3 (a real test order — good). You have **not** done step 4 (payload inspection), and step 5 (confirmation in the platform UI) **failed**. Per the evidence gate this skill enforces: *"a tag firing green in a debugger is not proof of accurate measurement."* A GTM preview showing the tag "fire" only tells you the trigger rule matched — it does not tell you the request actually left the browser, reached Meta, or was accepted.

Miravelle does qualify for the skill's one named exception (brand-new property, no traffic yet → **provisional PASS** is possible instead of waiting for a full platform-UI confirmation). But that provisional path still requires **debug-mode evidence *plus* a correct payload** — you have the first, not the second. So you're not even at "provisional PASS" yet. You're at unverified, with one concrete anomaly (nothing in Events Manager) that needs a root cause before you can move forward.

---

```
PRE-LAUNCH TRACKING VERIFICATION - Miravelle Skincare, 2026-09-12
platform(s): Meta Pixel (Ads Manager) + GA4 | funnel: B2C ecommerce | server-side: unknown - ASK
launch: next week (~7 days) | budget at risk: unknown - ASK

check                          result       impact     fix effort        evidence
1 settings & designation       unknown      -          -                 Purchase event standard-mapped? not confirmed
2 tag debug (GTM preview)      pass         -          -                 purchase tag fired on confirmation page
3 test conversion              partial      -          -                 real €12 order placed w/ discount code; no
                                                                          order ID / event ID recorded; no click ID
                                                                          (expected pre-launch, no ad click yet)
4 payload inspection           FAIL         critical   near-zero         not done - network request never inspected
5 platform UI + status         FAIL         critical   near-zero to      Meta Events Manager shows nothing; root
                                                                          an hour            cause not yet diagnosed
6 deduplication                unknown      -          -                 depends on whether CAPI/server-side exists
7 test-data exclusion          FAIL         medium     near-zero         €12 order not refunded; test event not
                                                                          excluded/deleted
8 soak                         not started  -          -                 blocked
9 sign-off                     -            -          -                 blocked by checks 4, 5, 7

dedup rate : n/a (unknown if server-side sender exists)
gaps       : platform vs analytics n/a | analytics vs backend n/a | server vs browser n/a

DECISION: NO-GO (provisional PASS not yet earned - payload unverified, platform-UI check failed)
```

---

## Why "Events Manager shows nothing" isn't automatically OK — and isn't automatically a disaster either

Before treating this as a real defect, rule out the cheap explanations first (near-zero effort, do these today):

1. **You may be reading the wrong screen.** Events Manager's main Overview tab can lag; use **Test Events** (with a test event code) for near-real-time confirmation instead. If Test Events shows the purchase and Overview doesn't yet, that's just lag — not a defect.
2. **Confirm the GTM container is actually published**, not just previewed. This is the single most common cause of "works in preview, nothing live" — a checklist Critical defect fixed by one click (publish), but invisible until you specifically test the *live* site with preview mode closed.
3. **Check for an ad blocker / browser tracking protection** on your test device — a pixel call can be silently dropped client-side while GTM's own preview session (which isn't the same delivery path) still shows the tag as "fired."
4. **Confirm it's the right Pixel ID** — a copy-paste into the wrong Business Manager asset produces exactly this symptom.

If none of those explain it, it's a genuine tag/consent/payload defect and needs debugging before re-test — not a "wait it out" situation.

## What's still missing before this can even be a provisional PASS

- **Payload inspection (step 4, not done):** open the network tab, find the actual request to Meta (and the GA4 `purchase` hit), and confirm: event name = `Purchase`, **value = the amount actually paid after the discount code (not the €12 list price)** — discount-code flows are a classic source of hardcoded/pre-discount values — currency = EUR, an `event_id`, and `fbp`/`fbc` cookies present.
- **Reject-path test, not just accept (untested):** you only tested consent-accept. France and Germany are both consent-regulated (CNIL / TTDSG); if the pixel fires on the reject path too, that's a compliance problem, not just a measurement one. Test both paths before launch — this is a hard skill requirement, not optional polish.
- **Test-data cleanup:** refund the real €12 order in the backend, and delete/exclude the test Purchase event in Meta so it doesn't quietly count toward the ~50 optimization events/7 days Meta needs to exit learning phase — you don't want your very first campaign learning from a QA order.
- **Server-side / Conversions API — ask, don't assume:** if you're only running browser pixel with no CAPI, dedup is n/a but you're also fully exposed to iOS/browser signal loss on a France+Germany audience from day one. Since this is Miravelle's *first-ever* tracking setup, not just a one-off campaign, it's worth building the CAPI + shared `event_id` now while the funnel is still simple, rather than retrofitting it later under campaign pressure.

## Fix order (cheap → expensive)

1. Check Meta **Test Events** tool instead of Overview, and confirm the GTM container is published — near-zero effort, likely resolves "shows nothing" outright.
2. Inspect the payload (network tab) for event name / value-after-discount / currency / event_id.
3. Re-run the test purchase with consent **rejected**, confirm nothing fires.
4. Refund the €12 order, delete/exclude the test event.
5. Once a real event lands in Events Manager with correct value, re-run the full sequence once more using an actual campaign click (after launch, in the first hours) to confirm the click identifier (`fbclid`) survives to the order.

**Re-verify:** full sequence from step 3 once the above is resolved, then issue GO.
**Approver:** pending — name whoever signs off once re-verification clears.

I need three answers to finish the report cleanly: is a server-side Conversions API planned or live, is Google Ads also running alongside Meta, and who owns the fix if step 4/5 turns out to be a real defect (you, or a dev)?