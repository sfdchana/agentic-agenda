# Day 16 — Scale: batch-score the archive + cost

- [ ] Done

**After this you should know:** what it costs to score the whole archive, and the levers
that control it. Capacity thinking, concrete.

## 📖 Read (~15 min)
[Anthropic — Prompt caching](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)
(recap). Focus on caching a stable prompt prefix across many calls.

## 🛠️ Build (~20 min)
Batch-score every unscored item on the axes. Measure tokens in/out, total cost, latency.
Apply judge-once (skip already-scored) so you never re-pay.

## 🤖 Claude-craft (~10 min)
Draft a **scheduled job** idea (e.g. nightly scrape + score) — sketch what it'd run.

## 🔗 Network
—

## ✍️ Journal
One line: the real per-item cost of scoring your archive.
