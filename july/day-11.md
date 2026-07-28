# Day 11 — Chunk 3: Wire the taste judge onto incoming items

- [ ] Done

**After this you should know:** how to put a structured LLM classification onto real ingested data — AI *on* clean data, the whole thesis — and why classification is a controlled call, not a chat.

## 📖 Read first (~20 min)
Anthropic — *Building Effective Agents* (anthropic.com/engineering/building-effective-agents). Focus on the **augmented LLM** and **when a workflow beats an agent**. Your taste judge is a *workflow step* (classify → validate → store), not an open-ended agent — read enough to know *why* that distinction matters.

## Do (~35 min) — direct it, don't grind it
Take the Day-5 structured-output call and point it at new `items` rows: send name/aspects (+ image later), get back a validated taste read, store it. Classify ~5 real items and eyeball the machine's read next to the listing. You're wiring a known pattern onto real data.

## Understand & defend (~5 min, journal it)
Why classify *after* ingestion instead of during the eBay fetch? Why validate the model's output even when it "looks" right?

## 3 flashcard ideas
- why is the taste judge a workflow step, not an agent?
- why classify after ingestion, not during the fetch?
- what makes the output safe to store (vs raw model text)?

_Journal: where the machine's read matched your eye — and where it didn't._
