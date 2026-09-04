# Day 13 — Slider-search: query the nearest items

- [ ] Done

**After this you should know:** how to rank rows by distance in SQL and return only the
closest — the query behind the search.

## 📖 Read (~15 min)
[Use The Index, Luke — Fetch first rows only](https://use-the-index-luke.com/sql/partial-results/fetch-first-rows-only).
Get: `ORDER BY … LIMIT` and why the index matters as data grows.

## 🛠️ Build (~20 min)
Write the query: given target scores, compute per-item distance across axes, `ORDER BY`
distance, `LIMIT n`. Return the nearest pieces. (Pivot `item_axis_scores` per item.)

## 🤖 Claude-craft (~10 min)
Read about **composing/chaining** skills — how one skill or subagent can hand off to
another.

## 🔗 Network (if Thursday)
Reach: one genuine note.

## ✍️ Journal
One line: what breaks in this query at 10,000 items? (throughput vs latency — Day 23 read)
