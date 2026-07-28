# Day 13 — Chunk 3: Write-up — how the taste layer decides

- [ ] Done

**After this you should know:** how to explain your taste-ranking design *and* where it's confidently wrong — the staff-level habit, and the seed of your eval set.

## 📖 Read first (~20 min)
Hamel Husain — *"Your AI Product Needs Evals"* (hamel.dev/blog/posts/evals). Get the mindset: LLMs are **confidently wrong**, "vibes" don't scale, and your own corrections *are* the eval dataset. This is the north star for Month 4.

## Do (~35 min) — direct it, don't grind it
Write the short repo write-up: how an item flows listing → classification → taste score → ranked result. Then the honest part — pull 3–5 items the model ranked high but you'd reject (or vice-versa) and write *why*. That divergence is your future eval set.

## Understand & defend (~5 min, journal it)
What's the difference between "wrong" and "confidently wrong," and why is the second one the dangerous kind to capture?

## 3 flashcard ideas
- what is an eval set, and where does yours come from?
- "confidently wrong" — what does it mean and why capture it?
- trace one item end-to-end through the taste layer.

_Journal: the most surprising thing the model got confidently wrong._
