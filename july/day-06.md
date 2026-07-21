# Day 06 — Chunk 0: Architecture tour (read + diagram your own pipeline)

- [ ] Done

**After this you should know:** the shape of the eBay pipeline you already have — the pieces, how data flows, and where the boundaries are — well enough to redraw it from memory.

## Do (~1 hr)
No code. Read your own `houseofsof-api`, following the data: `src/pipeline/run.js` → `src/scrapers/ebay.js` → `src/pipeline/normalizer.js` → `rules.js` → the `items` table → `src/api/routes/ebay.js` (the live admin search). For each file, write one sentence: *what it owns.* Then draw the flow as boxes-and-arrows (paper or Excalidraw): search config → fetch → normalize → filter/score → dedup → insert → review UI.
Analogy: you're reverse-engineering someone else's Salesforce org — read the triggers/flows before you touch anything.

## 3 flashcard ideas
- Name the stages of the pipeline in order, from search to stored row.
- Which file owns "talk to eBay," and which owns "shape the data"?
- Where does dedup happen, and on what field?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
