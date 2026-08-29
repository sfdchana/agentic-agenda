# Day 17 — Data III: auto-score items on the axes

- [x] Done

**After this you should know:** how the vision judge turns your axes into real scores on real items — the machine positioning pieces on your map.

## 📖 Read (~20 min)
Anthropic — **Vision** guide
(https://docs.anthropic.com/en/docs/build-with-claude/vision). Get: how to send an
image to the model and get structured output back — how your judge will score real
eBay items on your sliders.

## 🛠️ Build (~20 min) — taste-map project
Extend `classify-items.js` so the vision judge outputs a **score per axis** (`feminine: 0.8`, `edgy: 0.3`…) and stores them in `item_axis_scores`. Run on ~10 items. Now real pieces have coordinates.

## Understand & defend (~5 min, journal)
Why store the scores (judge-once) instead of recomputing them every time you draw the map? (Tie to cost.)

## 3 flashcard ideas
- how does the judge produce a 0–1 axis score?
- why cache the scores in a table?
- scheduled vs queued work?

_Journal: one item's axis scores vs. your own read of it._
