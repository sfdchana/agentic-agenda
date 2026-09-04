# Day 5 — Harden: the architecture write-up

- [ ] Done

**After this you should know:** how to explain your own system — boundaries, idempotency,
what breaks at 10×. Ships August's `archive-ingest` deliverable, documented.

## 📖 Read (~15 min)
[Architecture Decision Records](https://adr.github.io/) (skim). Get: a lightweight way to
write down a design and the reasoning behind it.

## 🛠️ Build (~20 min)
Write `ARCHITECTURE.md`: the stages (scrape → normalize → dedup → store → classify), where
the boundaries are, why the dedup key is stable, and what breaks at 10× (throughput —
your Day 23 read).

## 🤖 Claude-craft (~10 min)
Refine your `houseofsof-ingest` skill's **description** so it triggers reliably.

## 🔗 Network (if Monday)
Research: another company + one person.

## ✍️ Journal
One line: the one architectural decision you're most confident about, and why.
