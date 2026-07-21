# Day 17 — Deepen: run ingestion on a schedule

- [ ] Done

**After this you should know:** how a pipeline goes from "I run it by hand" to "it runs itself" — the archive filling on its own.

## Do (~1 hr)
Make `run.js` runnable on a schedule: a cron entry, a `node-cron` loop, or a Railway scheduled job. Have it run the search config every N hours and log what it added. Confirm a scheduled run produces new rows (and dedup keeps it clean). *(This is the async/worker fundamental, applied.)*
Analogy: a Scheduled Apex job — but you own the scheduler and the runtime.

## 3 flashcard ideas
- What turns a script into a scheduled worker?
- Why does a scheduled pipeline *need* idempotency (Day 10) to be safe?
- Where would this run in production, and what could break overnight?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
