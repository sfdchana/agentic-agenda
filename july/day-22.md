# Day 22 — Deepen: cost + context awareness on batch classify

- [ ] Done

**After this you should know:** what it costs to classify at scale, and the levers (model choice, caching, prompt size) that control it.

## Do (~1 hr)
Classify a batch (say 50 items) and measure: tokens in/out, total cost, latency. Try one lever — a cheaper model (Haiku) on the same task, or a cached system prompt — and compare quality vs. cost. Decide what you'd actually ship. *(Model-landscape + caching fundamentals, made concrete on your data.)*
Analogy: the governor-limit instinct, but *you* set the budget now — cost is the limit you design for.

## 3 flashcard ideas
- The cost / latency / quality triangle — pick-two in practice.
- When does a smaller model beat a bigger one for classification?
- What does prompt caching cache, and when does it help?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
