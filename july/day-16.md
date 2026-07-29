# Day 16 — Data II: taste-reference photos (anchor each pole)

- [ ] Done

**After this you should know:** how *exemplar images* define a dimension better than a text label — your visual-first instinct, formalized.

## 📖 Read (~20 min)
AWS Builders' Library — *"Timeouts, retries, and backoff with jitter"* (aws.amazon.com/builders-library). Get: exponential backoff, jitter, retry storms — you'll need this when the classifier hits eBay at volume.

## 🛠️ Build (~20 min) — taste-map project
Add a handful of **taste-reference photos** — the images that anchor each axis pole (a *very feminine* example, a *very edgy* one). Store their URLs against the axis/pole in `taste_references`. Photos as data — exactly your instinct.

## Understand & defend (~5 min, journal)
Why does an exemplar image define an axis pole better than the word "edgy"? (Think about how the vision model *compares* against an anchor.)

## 3 flashcard ideas
- what is an exemplar/anchor?
- why images over words for a taste axis?
- what problem does jitter solve? (from the read)

_Journal: the two anchor images you chose for one axis, and why they're the poles._
