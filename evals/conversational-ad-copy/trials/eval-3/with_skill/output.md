Here's the sponsored-card package for Quillhatch, following `conversational-ad-copy`.

**Two things I did not include, on purpose**

You asked for "trusted by 20,000 freelancers" and a customer quote, but flagged yourself that neither is real. This skill treats that as a hard stop, not a style note: *"no invented claims, statistics, or testimonials — ever… a claim without a source gets labelled `UNSOURCED` and held, not written around."* A made-up adoption number and a fabricated quote are exactly the failure mode the skill calls out as the highest regulatory exposure on this surface (FTC "clear and conspicuous" + substantiation duties apply the same as any other ad). So both are held below as `UNSOURCED`, not shipped. The one number you *do* have — the July 2026 support-ticket analysis — carries the ad instead, and it's a better ad for it: specific and sourced beats round and vague, especially since the assistant's own answer can sit right next to this line and contradict a puffed-up one in the same turn.

**Assumptions I made without an interview** (correct me and I'll redraft): placement = OpenAI ChatGPT ads' advertiser-written `chat_card` — the only surface with vendor-published field limits, which is what "standard limits everyone publishes" points to; reader = the freelancer themself deciding (B2C-shaped, even though the buyer is a small business); thread stage unknown → soft ask, no explicit CTA copy; no account baseline yet.

---

### Placement + control axis
In-assistant sponsored card, **verbatim** surface (OpenAI ChatGPT ads `chat_card`), advertiser-written, owned by paid media. Fields: Title, Copy, no separate CTA — ask folds into copy if used.

### Situation description (Persona + Intent + Scope)
**Primary:** "A freelancer about to sign a client contract, unsure which clauses carry real risk, asking for a fast way to check before signing." (130/280 chars)

Alternates for delivery diagnosis:
- "A freelancer reviewing a client contract before signing, wanting to know quickly which clauses could hurt them." (111 chars)
- "A freelancer who just received a contract and wants to catch risky clauses before signing." (90 chars)

### Slot copy
- **Title:** "Spot risky clauses fast" — 23 chars (target 16–24, max 50 ✓)
- **Copy:** "Quillhatch flags risky contract clauses in a median 6 minutes." — 62 chars (target 32–48, max 100 ✓ — over the *recommended* band, well inside the hard cap; see trimmed alternative below)
- **Trimmed alternative** (closer to recommended, drops "contract" for brevity): "Quillhatch flags risky clauses in a median 6 minutes." — 53 chars. Your call — I'd keep "contract" since the line has to stand alone with zero surrounding chrome, and "clauses" alone is a beat more ambiguous.
- **Ask:** none folded in. Thread stage unknown, so defaulting to the early-exploratory case (soft ask, implied by the landing page) rather than guessing at a hard "start a trial." Tell me the stage and I'll fold in an explicit ask.

### Grounding table
| Claim | Source | Status |
|---|---|---|
| "flags risky contract clauses" | product function, as described in your brief | sourced |
| "median 6 minutes" | support-ticket analysis, July 2026 (supplied) | sourced, dated 2026-07 — **review date: 2027-01-31** or sooner if a newer ticket analysis lands |
| "trusted by 20,000 freelancers" | none supplied | **UNSOURCED — held.** Get this from active users/logins/paid seats if you want to run it next cycle |
| customer quote | none supplied | **UNSOURCED — held.** A real, permissioned quote can go in on the next iteration |

### Compliance note
Platform "Sponsored" label handles disclosure; that's the platform's job, not a substitute for your own duties. Not in this skill's named regulated categories (health/medical/financial), but contract-risk assessment is legal-adjacent — worth a quick look from whoever owns compliance before this scales past one card, independent of this skill's scope.

### Quotability gate — 9/10, one open item
1. Self-contained ✓ 2. Product named, no pronoun ✓ 3. One idea ✓ 4. Claim first ✓ 5. Specific detail, not adjectives ✓ 6. Every claim sourced ✓ (the two unsourced claims simply aren't in the slot) 7. Time-bound claim dated, review date set ✓ 8. Recommendation register, no manufactured urgency ✓ 9. Narrow, survives sitting beside the model's own answer ✓ 10. **Verified against your live ads manager today — open.** I used the vendor-documented spec since you don't have it open; re-paste the current numbers before this ships, they go stale weekly.

### Measurement plan
No account baseline on this surface yet → first 30 days sets it. Attribution window: 14 days minimum (most conversions land outside the click window). Read order: delivery across the three situation descriptions first (free, days not weeks — weak delivery means re-frame the situation before touching the copy again), then click-through against the baseline once it exists, then trial/signup quality. No deadline was given, so this is the unmodified default order — a hard deadline or a "compounding asset" answer from you would re-rank it.