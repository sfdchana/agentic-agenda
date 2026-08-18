# Day 13 — Taste schema II: objects + relationships

- [x] Done

**After this you should know:** how to model new objects (designer, axis, taste reference) and *relate* them to items — real relational data modeling.

## 📖 Read (~20 min)
Hamel Husain — *"Your AI Product Needs Evals"* (hamel.dev/blog/posts/evals). Get: your corrections are the dataset; disagreement is signal.

## 🛠️ Build (~20 min) — taste-map project
Design (don't build yet) the new objects and how they link:
- `designers` (name, notes)
- `axes` (name, low-pole label, high-pole label)
- `item_axis_scores` (item_id, axis_id, value) — the **junction** table
- `taste_references` (an exemplar image per axis pole)
Draw the **ERD** — boxes + the lines between them.

## Understand & defend (~5 min, journal)
Why a separate `item_axis_scores` table instead of one column per axis on `items`? (Hint: many axes, sparse, and you'll add more.)

## 3 flashcard ideas
- one-to-many vs many-to-many?
- why a junction table?
- what is an ERD?

_Journal: your ERD sketch — the objects and how they connect._
