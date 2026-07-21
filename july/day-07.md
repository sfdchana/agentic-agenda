# Day 07 — Chunk 0: Defend it (Browse + OAuth vs the dead Finding API)

- [ ] Done

**After this you should know:** *why* the two eBay integrations differ, and be able to defend every boundary out loud — the thing you couldn't do before.

## Do (~1 hr)
Reading + writing, still no code. Read: eBay **Browse API** `item_summary/search` docs, the **OAuth client-credentials** flow, and why eBay **retired the Finding API** (early 2025). Then look at `routes/ebay.js` `getAccessToken()` — trace how it gets a token, caches it, and calls Browse. Write a short "defense": for each boundary in yesterday's diagram, one sentence on *why it's there and what breaks without it* (e.g. "token caching — because minting a token every request is slow and rate-limited").
Analogy: like justifying why a piece of logic is a Flow vs a trigger vs Apex — you own the reasoning now.

## 3 flashcard ideas
- What is the OAuth client-credentials flow, in one line?
- Why is the token cached with an expiry instead of fetched each call?
- Finding API vs Browse API — what changed and why does it matter for my pipeline?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
