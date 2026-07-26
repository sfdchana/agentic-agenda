# Day 09 — Chunk 2: Fix the normalizer (Browse shape → items columns)

- [x] Done

**After this you should know:** how to map a messy external response to your own clean schema — the core skill of data engineering.

## Do (~1 hr)
The Browse response has *different field names* than the old Finding response, so `normalizer.js` `fromEbay()` needs updating. Compare one raw Browse item to the `items` columns (name, brand, price, currency, source_url, image_url). Rewrite `fromEbay()` to pull the right fields (e.g. `item.title`, `item.price.value`, `item.itemWebUrl`, `item.image.imageUrl`). Print the normalized object; confirm every column is populated.
Analogy: a field-mapping in an integration — external payload on the left, your object on the right.

## 3 flashcard ideas
- What is a normalizer's job in one sentence?
- Why map to your own schema instead of storing the raw API response?
- Name three Browse fields and the columns they map to.

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
