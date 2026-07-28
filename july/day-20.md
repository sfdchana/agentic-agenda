# Day 20 — Deepen: testing strategy (what to test, and why)

- [ ] Done

**After this you should know:** *where* tests earn their keep — the risky boundaries — so a changed API field can't silently break ingestion. Strategy over coverage.

## 📖 Read first (~20 min)
Martin Fowler — *"The Practical Test Pyramid"* (martinfowler.com). Get: many fast unit tests, few slow end-to-end ones, and **test the risky boundaries** rather than chasing a coverage number.

## Do (~30 min) — direct it, don't grind it
The normalizer is where external chaos meets your schema — the highest-value thing to test. Direct a couple of tests: given a saved sample Browse item, assert the normalized object has the right fields/types; feed a *malformed* item, assert it fails loudly not silently. Decide *what* to assert; let the syntax be assisted.

## Understand & defend (~10 min, journal it)
Why is the normalizer the highest-value thing to test in this whole system? What's a test that would have caught the `brand: null` bug you already hit?

## 3 flashcard ideas
- why test the boundary, not everything equally?
- what should a normalizer test actually assert?
- unit vs end-to-end — when each?

_Journal: the one test you'd write first, and what it protects._
