# Day 17 — Deepen: run ingestion on a schedule (workers)

- [ ] Done

**After this you should know:** how a pipeline goes from "I run it by hand" to "it runs itself," and why background work lives off the request path.

## 📖 Read first (~20 min)
An intro to **background jobs / message queues** — search "why use a message queue" or read the job-scheduling section of a backend primer. Get: why you move slow work *off* the user's request, and the difference between **scheduled** (cron) and **queued** (on-demand) work.

## Do (~30 min) — direct it, don't grind it
Make `run.js` runnable on a schedule (cron, `node-cron`, or a Railway scheduled job). Have it run the search config every N hours and log what it added. Confirm a scheduled run adds new rows and dedup keeps it clean.

## Understand & defend (~10 min, journal it)
Why does a *scheduled* pipeline absolutely need the idempotency from Day 10? Where would this run in production, and what could break overnight while you sleep?

## 3 flashcard ideas
- what turns a script into a scheduled worker?
- scheduled vs queued work — the difference?
- why does scheduling *require* idempotency?

_Journal: what "it runs itself" changes about how you think about the system._
