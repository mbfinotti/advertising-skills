No — biggest number first is the wrong heuristic here. It conflates dollar size with priority and ignores three things: fix effort, whether engineering is even the bottleneck, and whether you can trust the number yet. Three of your four findings are measurement bugs; only one (cross-device) is a structural gap. Fix your measurement layer before you act on — or even fully trust — an estimate that depends on it.

**Fix in this order:**

**1. Duplicated purchase tag ($29k/mo over-reported)** — first, fast

- Root cause of active daily harm: every ad platform's auto-bidding (tROAS, Advantage+, PMax) is optimizing against inflated conversion values right now. Every day this stays live, spend keeps misallocating.
- Likely a tag-container config fix (GTM), not a dev sprint item — probably doesn't even compete for your "fully booked" engineering time. Route to marketing ops/analytics, not the eng queue.
- Also: this number pollutes any ROI calculation you'd use to judge the other three fixes. Kill it first so your baseline is real.

**2. Internal test orders (~220/mo, ~$6k)** — same wave as #1

- Same profile: cheap, fast, low/no engineering lift (add a test flag/filter in the order system and exclude in reporting).
- Corrupts AOV, conversion rate, and revenue baselines — same reason to clear it before evaluating anything else.

**3. UTM stripping on email links ($9k/mo misattributed to direct)** — third

- Real bug, clear causal fix (configure the shortener to pass query params through, or swap redirect method), moderate effort, high confidence.
- Do this before touching cross-device — it's a bounded fix with a known mechanism, unlike #4.

**4. Cross-device attribution ($55k/mo estimated)** — last, and scope it, don't rush it

- It's a vendor's statistical estimate, not a confirmed bug — and that estimate was almost certainly computed on top of the same platform data being distorted by #1 and #3. Re-measure it after fixing those; the real gap may be smaller.
- "Stable for four months" means it's not urgent-urgent — no fire, no trend getting worse.
- Fixing it properly (identity resolution, server-side tracking, login incentives, probabilistic modeling) is a multi-sprint engineering investment — exactly the kind of work that shouldn't get squeezed into a fully-booked quarter as a reaction to one big number. Scope it as a proper project for next quarter's roadmap instead.

**Net effect:** #1–#3 are execution this quarter (mostly ops/analytics, minimal engineering), recover ~$44k/mo in reporting accuracy and true attribution, and give you a clean baseline. #4 gets scoped properly and re-measured before you commit real engineering time to it — which may turn out to be less than $55k once the tagging bug and UTM leak are fixed.
