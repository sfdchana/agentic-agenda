# Day 13 — Chunk 3: Write-up — how the taste layer decides

- [ ] Done

**After this you should know:** you can explain your taste-ranking design *and* where it's confidently wrong — the staff-level habit, and the seed of your eval set.

## Do (~1 hr)
Short write-up (goes in the repo): how an item flows from listing → classification → taste score → ranked result. Then the honest part: pull 3–5 items the model ranked high but you'd reject (or vice-versa), and write *why*. That divergence is literally your future eval dataset (Month 4).
Analogy: like documenting a design decision + its known gaps in an ADR — the gaps are the roadmap.

## 3 flashcard ideas
- Trace one item end-to-end through the taste layer.
- What does "confidently wrong" mean, and why capture it?
- How does today's write-up become an eval set later?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
