# Day 4 — Portal: corrections as a dataset

- [ ] Done

**After this you should know:** how to store every correction so it accumulates into a
labeled dataset you could later evaluate or tune against.

## 📖 Read (~15 min)
[Stripe — Idempotent requests](https://docs.stripe.com/api/idempotent_requests) (recap).
Tie it to writes: saving a correction should be safe to repeat, never double-counted.

## 🛠️ Build (~20 min)
Persist corrections to a `corrections` table: `item_id`, `axis`, `model_score`,
`human_score`, `corrected_at`. Every edit = one labeled example of your taste.

## 🤖 Claude-craft (~10 min)
Create a tiny skill (e.g. `houseofsof-build`) that captures how to run your pipeline
(migrate → scrape → score). Small and real.

## 🔗 Network
—

## ✍️ Journal
One line: why is *disagreement* the valuable signal, not agreement?
