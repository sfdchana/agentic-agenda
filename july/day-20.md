# Day 20 — Deepen: test the normalizer (pytest + type hints)

- [ ] Done

**After this you should know:** how to test the riskiest part of the pipeline — the mapping — so a changed API field can't silently break ingestion.

## Do (~1 hr)
The normalizer is where external chaos meets your schema, so it's the highest-value thing to test. Add type hints to the classify/normalize functions, then write tests: given a saved sample Browse item, assert the normalized object has the right fields and types. Feed it a *malformed* item and assert it fails loudly, not silently. *(pytest fundamental, applied to real code.)*
Analogy: Apex test methods — but local, fast, and run on every change.

## 3 flashcard ideas
- Why is the normalizer the highest-value thing to test?
- What does a good test assert about a mapped object?
- What do type hints buy you if they don't enforce at runtime?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
