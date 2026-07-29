# Day 14 — Taste schema III: lock it in (the migration)

- [ ] Done

**After this you should know:** how to turn a schema *design* into real DDL and apply it safely to a live database.

## 📖 Read (~20 min)
*Refactoring UI* (refactoringui.com) — hierarchy + whitespace (prep for the map viz later this month).

## 🛠️ Build (~20 min) — taste-map project
Write the migration DDL for yesterday's design: `CREATE TABLE IF NOT EXISTS designers / axes / item_axis_scores / taste_references`, plus any `ALTER TABLE items` you need. Review it, then run it (`node src/db/schema.js` or a migration file). Schema **locked**.

## Understand & defend (~5 min, journal)
Why `IF NOT EXISTS` and *additive* migrations (never drop a column on a live DB)? What makes a migration safe to run twice?

## 3 flashcard ideas
- what is a migration?
- why additive + idempotent migrations?
- DDL vs DML?

_Journal: the tables you created; one design choice you'd defend in review._
