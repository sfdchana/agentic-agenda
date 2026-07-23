# Week 2 flashcards — my own pipeline: architecture + auth

Covers days 06–07 (Chunk 0: understand + defend the eBay pipeline I already built).
Q on top, A below. Review by covering the answer.

---

## Day 06 — Architecture of my own pipeline

**Q:** Name the pipeline stages in order, search → stored row.
**A:** searchConfig (what to hunt) → scraper (talk to eBay) → normalizer (messy → clean) → rules `passes`/`score` (filter + rank) → dedup → INSERT into `items` (status `pending`) → admin review UI.

**Q:** Why does the normalizer exist — why not store eBay's raw JSON?
**A:** It's the **boundary** between eBay's world and mine. It translates eBay's ugly nested shape into my clean, flat schema, so everything downstream speaks *my* language, not eBay's. Store raw and every consumer has to re-learn eBay's format.

**Q:** Dedup is "keyed on `source_url`" — what does that mean, and why that field?
**A:** "Keyed on X" = X is the fingerprint for "same item." `source_url` because a dedup key must be **unique + stable**: names collide, prices change, but every listing has exactly one URL.

**Q:** `passes()` vs `score()` — why have both?
**A:** `passes()` = the bouncer (yes/no gate: over budget, blocklisted brand → rejected). `score()` = ranking the ones who got in (0–100). Filter out garbage first, then rank what's left. Price is used in both: a hard cutoff in `passes`, a quality signal in `score`.

**Q:** Why does every new row land as `status = 'pending'`?
**A:** Human-in-the-loop. The pipeline curates a shortlist; it doesn't publish. I review each `pending` item and mark approved/rejected/held — and every decision is a labeled example of my taste (the future classifier's dataset).

---

## Day 07 — Defending the auth layer

**Q:** What does client-credentials OAuth prove, and how does it differ from "log in with Google"?
**A:** The **app** proves who it is (base64 `APP_ID:CERT_ID` → bearer token) — machine-to-machine, no user. "Log in with Google" is the **authorization-code** grant: a *user* consents to share *their* data. Client-credentials has no user and touches only public data.

**Q:** Why cache the eBay token instead of fetching one per request?
**A:** Minting a token is a slow, rate-limited round-trip. Caching and reusing it until expiry avoids doubling latency and burning the rate limit.

**Q:** Why expire the token ~60 seconds early?
**A:** Safety margin against the clock/latency gap — a token valid when you *check* it could be dead by the time your request *lands*. Expiring early forces a refresh before that can bite.

**Q:** In one line, why did eBay retire Finding in favor of Browse?
**A:** Browse uses a short-lived **OAuth token in a header** (REST, secure, standard); Finding put a **static app key in the URL** — less secure and non-standard.
