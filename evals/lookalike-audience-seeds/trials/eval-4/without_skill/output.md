This is a legal question dressed up as a marketing task, and the agency's framing is wrong on the fact that matters most. Here's my complete answer.

## The agency's core claim is false

Hashing ≠ anonymization under GDPR. SHA-256 of an email address is **pseudonymization**, not anonymization, because:

- The output is deterministic — same input always produces the same hash, with no salt mentioned.
- Google and Meta (and anyone with a large email corpus) can pre-compute hash tables of common addresses and match them back. This is exactly how Customer Match / Custom Audiences work — the platform re-hashes its own user database and joins on the hash. That joinability is the entire mechanism, and it's also what makes it personal data.
- Regulators have already ruled on this: CNIL (France) and other EU DPAs have stated hashed identifiers used for ad-matching remain personal data because the process is designed to be reversible-by-matching. There is no exemption in GDPR for "hashed" data — Article 4(1)'s definition of personal data turns on identifiability, not on the format of the identifier.

So this isn't a grey area you can wave off — "hashed therefore anonymous therefore GDPR doesn't apply" is a claim that would not survive a DPA inquiry, and it's the kind of thing that shows up in enforcement actions specifically because agencies say it confidently to clients.

## What GDPR actually requires here

Uploading 30,000 EU customer emails (hashed or not) to Google/Meta for ad targeting is a **disclosure to a third party for a new purpose** (advertising, not the purpose the data was collected for — presumably order fulfillment/account management). That requires its own legal basis:

- **Consent is the only realistic basis** for using customer data for ad-platform matching/lookalikes. Legitimate interest doesn't clear the bar here — the EDPB and multiple DPAs treat ad-tech audience matching as high-impact processing that data subjects wouldn't reasonably expect from a supplement purchase, and legitimate interest also loses automatically for anything touching **health inference**.
- **The sleep-and-anxiety segment makes this materially worse, not incidental.** A list of "people who bought our sleep-and-anxiety product line" is a customer list built from data that lets Google/Meta infer something close to a health condition (sleep disorder, anxiety) about named individuals. Article 9 GDPR classifies health-related data as a **special category**, requiring explicit consent (Art. 9(2)(a)) — the ordinary Art. 6 bases don't apply at all. This isn't a "consent isn't a big issue" situation; it's the single highest-risk segment you could have picked to seed a lookalike with, and using it for ad targeting without explicit, specific consent is a clear violation, not a judgment call.
- Meta's and Google's own Custom Audience / Customer Match terms additionally require you to represent that you have the necessary consents and legal basis before upload — so this isn't just a regulator risk, it's a platform ToS violation, and Meta in particular has faced regulatory scrutiny specifically over health-adjacent audience targeting.

## Answer to "can we upload now and let legal review in parallel"

No. Concretely:

1. **Do not upload the sleep-and-anxiety segment at all** until legal has confirmed the consent language covers explicit consent for special-category data used in ad targeting. This one needs sign-off before anything, not in parallel.
2. **Do not upload the general 30,000-customer list** for Customer Match / Custom Audiences until you've confirmed the legal basis. Check now, before uploading, whether your checkout/marketing consent already covers "sharing with third-party ad platforms for audience matching" — most standard "we'll email you about orders" consent does not cover this, and if it doesn't, you need a fresh, specific opt-in (or to filter the list down to only customers who gave that specific consent).
3. **Lookalikes inherit the seed's problem.** If the seed audience was uploaded without valid consent, everything built off it downstream (Google Similar Audiences equivalent, Meta Lookalike) is also tainted, so this isn't something you can quietly unwind later — better to not start the clock.
4. **"Legal is backed up a month" is a scheduling problem, not a reason to change the risk calculus.** Ask legal for a 15-minute fast-path check specifically on: (a) does existing consent language cover ad-platform data sharing, and (b) is there any special-category carve-out for the health-adjacent segment. That's a much smaller ask than a full review and could unblock the general list this week without the health segment.

## What you can do this week without waiting

- Build and upload Customer Match / Custom Audiences using only customers whose consent language **already** explicitly covers sharing data with advertising partners — pull that subset now, it needs no new legal work.
- Build the general lookalikes off that consented subset.
- Hold the sleep-and-anxiety seed and its lookalike until you have explicit, specific consent for that segment — this is the one to flag most urgently to legal, precisely because it's higher-value to you and higher-risk under Art. 9.
- If most of the 30,000 aren't covered by existing consent language, consider a fast, targeted re-consent email/banner ("optimize your ads experience / limited-time offers") rather than waiting a month for a full review to greenlight the whole list.

**Bottom line: the agency's "hashed = anonymous = GDPR doesn't apply" line is incorrect and shouldn't be relied on. Upload now only for the subset with consent that actually covers this use; don't touch the sleep-and-anxiety segment until legal has specifically cleared it as special-category data.**