# Day 12 — Chunk 3: Rank by taste *fit*, not price

- [ ] Done

**After this you should know:** the difference between *filtering* and *ranking*, and how a taste read becomes an ordering — the thing that actually cuts through thousands of listings.

## 📖 Read first (~20 min)
A recsys/relevance primer — Eugene Yan's *"System Design for Recommendations"* (eugeneyan.com) or any solid **retrieval-vs-ranking** explainer. Get: retrieval casts a wide net, **ranking orders the survivors by relevance**, and ranking is driven by *signals*. Your taste read is a signal.

## Do (~35 min) — direct it, don't grind it
Look at `rules.js` `score()`. Extend the scoring so the **taste read** drives the order — reward pieces whose classification matches the taste you're curating for, not just cheap ones. Sort, then eyeball the top 10: right *kind* of thing? Note where it's wrong.

## Understand & defend (~5 min, journal it)
Filtering vs ranking — why do you need both? Which signal *should* dominate the ranking for taste, and what happens if price dominates instead?

## 3 flashcard ideas
- filtering vs ranking — the difference?
- what is a "ranking signal," and what's yours?
- why is "sorted by taste fit" the core of the product?

_Journal: a piece the taste-ranking surfaced that price-ranking would have buried._
