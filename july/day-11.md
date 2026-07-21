# Day 11 — Chunk 3: Wire the Day-5 classifier onto incoming items

- [ ] Done

**After this you should know:** how to put your structured-output classifier (Day 5) onto real ingested data — AI *on* clean data, the whole thesis.

## Do (~1 hr)
Take the Pydantic-style classify step from Day 5 and call it inside the pipeline (or as a follow-up pass) on each new `items` row: send the item's name/brand/description, get back a validated taste read (role / era / magnitude / vibes), and store it on the row. Start small — classify 5 real items, print machine output next to the listing.
Analogy: the "AI second, clean data first" rule — you only classify *after* ingestion has given you tidy rows.

## 3 flashcard ideas
- Why classify *after* ingestion, not during the API fetch?
- What makes the classifier's output safe to store (vs. raw model text)?
- Where does the taste read live — same table or a new one?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
