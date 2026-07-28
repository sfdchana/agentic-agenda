# Day 10 — Chunk 2: Run end-to-end; dedup / idempotency

- [x] Done

**After this you should know:** what idempotency *really* means and why a re-runnable pipeline is a hard requirement, not a nicety — with real rows landing in Postgres, safely.
* idempotency key: the reason why this makes failures that could occur safe is because this is a unique id that is passed with every transaction so to say, and that is unique so if it knows if it's a duplicate means it's processed and shouldn't be processed again if it's not it isn't. 
* exponential backoff: if a system is continously down the and the client keeps trying backoff is a way of waiting exponentially longer between each try (i.e. 1, 2, 4 seconds) to give the system time to recover. Capping retries is another safegaurd that protects additional damage caused by further retries to a broken system.
* thundering herd problem: when a server is down, we anticipate that once its back up the retries will come in from the client all at once. Therefore assigning randomness or jitter to client requests allows breathing time in between so the server can recover instead of all the retries coming at once.


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
