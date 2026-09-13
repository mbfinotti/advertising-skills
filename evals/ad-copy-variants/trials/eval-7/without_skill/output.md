# Threadgold Ad Naming Convention

## Root cause

Three people independently typed the same ad's name into three systems (ad platform, UTM parameter, analytics label). Nothing forced them to match. The fix isn't picking prettier casing — it's making one name the source of truth and copy-pasting it everywhere else, never retyping it.

## The naming template

```
{angle}_{variant}
```

- **angle** — the creative concept/positioning being tested (e.g. `cool-sleep`, `luxury-hotel`). This is what changes when your teammate has a genuinely new idea.
- **variant** — a sequential number for executions _of that same angle_ (different hook, visual, or copy testing the same underlying claim). Resets to `v1` for every new angle.

Rules:

1. **Lowercase, always.** Analytics tools and UTM parsers often lowercase automatically — if you don't, you get silent duplicates (`Sleep_Cool_V1` vs `sleep_cool_v1` is exactly this bug).
2. **Underscore as the only separator.** Hyphens inside UTM values sometimes get parsed as word boundaries by BI tools; underscores don't. Pick one and ban the other — this is precisely how you ended up with `sleep_cool_v1` and `sleep-cool-v1` as "different" ads.
3. **One name, copy-pasted three times.** Whoever sets the UTM `content` parameter decides the canonical name. The ad platform's ad name and the analytics label are literal copies of that string — not re-entered, not reformatted, not abbreviated.
4. **`vN` means "same angle, new execution" — never "new angle."** A new positioning idea always starts a new angle slug at `v1`. It does not inherit the previous angle's version count.

## Immediate cleanup

| Old name(s)                                         | New canonical name | Why                                                                                                                                                                                                                                                                                         |
| --------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Sleep_Cool_V1` / `sleep_cool_v1` / `sleep-cool-v1` | `cool-sleep_v1`    | Same ad, three spellings — collapse to one.                                                                                                                                                                                                                                                 |
| `sleep_cool_v2` (the new hotel-luxury ad)           | `luxury-hotel_v1`  | It's not iteration #2 of the cooling angle — it's iteration #1 of a brand-new angle. Renaming it now prevents your reporting from ever implying it's a variant of `cool-sleep`, which would hide the fact that it's an entirely different value proposition with its own performance curve. |

Action: rename the ad in the platform, update the UTM `content` value, and fix the label in the analytics tool for all three rows so they collapse into one line of history.

## Going forward

- Before launching an ad, agree on the full name (`angle_variant`) once, in one place (a shared sheet or the campaign brief) — then whoever builds the UTM, whoever names it in the ad platform, and whoever labels it in analytics all pull from that same cell. No independent typing.
- When your teammate has a new idea, ask one question first: _"Is this a new hook for an existing angle, or a genuinely new positioning?"_ That answer decides whether it's `{same-angle}_v{n+1}` or `{new-angle}_v1`. That single check is what broke down last time.
- If you want a bit more structure later (multiple formats, multiple brands, date batches), extend the template rather than replacing it: `{brand}_{angle}_{format}_{variant}` — but don't add dimensions you don't need yet; the two-part version above is enough to fix your current mess.
