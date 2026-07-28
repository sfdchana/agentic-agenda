# Day 10 — Chunk 2: Run end-to-end; dedup / idempotency

- [ ] Done

**After this you should know:** what idempotency *really* means and why a re-runnable pipeline is a hard requirement, not a nicety — with real rows landing in Postgres, safely.

## 📖 Read first (~20 min)
Stripe's idempotency writeup — *"Designing robust and predictable APIs with idempotency"* (stripe.com/blog) or their idempotency docs. Pull out the core idea: **at-least-once vs exactly-once**, and how an *idempotency key* makes a retry safe. Then map it home: `source_url` **is** your idempotency key.

## Do (~35 min) — direct it, don't grind it
Run `run.js` end-to-end against the Browse scraper + fixed normalizer; watch rows land in `items`. Then run it **again** and confirm the dedup check skips everything. The win is *seeing idempotency hold*, not typing loops — you're directing the wiring and verifying the property.

## Understand & defend (~5 min, journal it)
If two runs overlap, or one crashes halfway, why does keying on `source_url` still keep the table clean? What breaks if you key on `name` instead?

## 3 flashcard ideas
- at-least-once vs exactly-once — the difference?
- what is an idempotency key, and what's yours?
- insert vs upsert — when does each matter?

_Journal: the moment a second run added zero dupes — why that property matters at scale._
