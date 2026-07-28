# Day 22 — Deepen: cost + context on batch classify

- [ ] Done

**After this you should know:** what it costs to classify at scale, and the levers — model choice, caching, prompt size — that control it. Capacity thinking, made concrete.

## 📖 Read first (~20 min)
Anthropic **prompt caching** docs (docs.anthropic.com) + a short piece on **token economics / cost optimization**. Get: what caching actually caches, when it helps, and the cost/latency/quality tradeoff across model sizes (Haiku ↔ Sonnet ↔ Opus).

## Do (~30 min) — direct it, don't grind it
Classify a batch (~50 items) and measure: tokens in/out, total cost, latency. Try one lever — a cheaper model on the same task, or a cached system prompt — and compare quality vs cost. Decide what you'd ship.

## Understand & defend (~10 min, journal it)
The cost/latency/quality triangle — where does your taste judge sit, and why? When would a *smaller* model beat a bigger one here?

## 3 flashcard ideas
- what does prompt caching cache, and when does it help?
- the cost/latency/quality triangle — pick-two in practice?
- when does a smaller model win?

_Journal: the real per-item cost of a taste read, and whether it surprised you._
