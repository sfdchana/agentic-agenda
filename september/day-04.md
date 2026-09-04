# Day 4 — Harden: a scheduled worker

- [ ] Done

**After this you should know:** how the pipeline runs *on its own* on a schedule instead
of only when you run it by hand.

## 📖 Read (~15 min)
[Railway — Cron jobs](https://docs.railway.com/reference/cron-jobs) (or a short "what is
cron" primer). Get: how a scheduled job fires a process on an interval.

## 🛠️ Build (~20 min)
Turn the pipeline into a scheduled run: a worker/cron that scrapes + scores on a schedule.
Start with "runs once when triggered," then set the schedule.

## 🤖 Claude-craft (~10 min)
Create a small skill (e.g. `houseofsof-ingest`) that captures how to run the pipeline.

## 🔗 Network
—

## ✍️ Journal
One line: what schedule makes sense, and what happens if a run overlaps the previous one?
