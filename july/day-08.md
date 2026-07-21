# Day 08 — Chunk 1: Revive the pipeline on the Browse API

- [ ] Done

**After this you should know:** how to move working code from one place to another and prove it runs — one live eBay search printing real items.

## Do (~1 hr)
First code of the build. Lift the working OAuth + Browse call out of `routes/ebay.js` into `scrapers/ebay.js`: replace the dead Finding-API `fetchEbay()` with a Browse version that gets a token and hits `/buy/browse/v1/item_summary/search`. Don't wire the whole pipeline yet — just call it once with a hardcoded query (e.g. "rodarte dress") and `console.log` the raw items. Confirm real listings come back.
Analogy: same instinct as extracting shared logic into a helper class — one source of truth for "talk to eBay."

## 3 flashcard ideas
- What endpoint does the Browse search hit, and what header identifies the marketplace?
- Why lift the eBay call into the scraper instead of duplicating it?
- How do you prove an API call works before wiring it into everything?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
