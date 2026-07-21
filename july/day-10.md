# Day 10 — Chunk 2: Run end-to-end; dedup / idempotency

- [ ] Done

**After this you should know:** what idempotency means and why running the same pipeline twice must not create duplicate rows — real rows flowing into Postgres again.

## Do (~1 hr)
Run the full `pipeline/run.js` against the Browse scraper + fixed normalizer. Watch items get fetched → normalized → filtered → inserted. Then **run it again** and confirm the dedup check (`SELECT id FROM items WHERE source_url = $1`) skips everything — no duplicates. That "safe to re-run" property is **idempotency**.
Analogy: like guarding an integration against reprocessing the same record — upsert semantics, not blind insert.

## 3 flashcard ideas
- What does idempotent mean, and why does a pipeline need it?
- What field is dedup keyed on here, and why that one?
- What's the difference between insert and upsert?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
