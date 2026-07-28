# Day 23 — Architecture write-up v2: the whole discovery system

- [ ] Done

**After this you should know:** how to present the *entire* taste-discovery system as one defensible design — and reason about what breaks as it grows.

## 📖 Read first (~25 min)
*Designing Data-Intensive Applications* ch. 1 (**Reliability, Scalability, Maintainability**) — or the **scalability** section of *The System Design Primer* (github.com/donnemartin/system-design-primer). Get the vocabulary: throughput vs latency, load parameters, bottlenecks, and how to reason about **10×**.

## Do (~30 min) — direct it, don't grind it
Redraw the diagram from Day 06, now with everything: Browse fetch → normalize → store → classify → taste-rank → API → discovery UI + the scheduled worker. Write the one-paragraph pitch and a **"what breaks at 10×"** note.

## Understand & defend (~5 min, journal it)
Which stage bottlenecks *first* at 10× volume — the eBay rate limit, the LLM cost, the DB, or the worker? Defend your answer.

## 3 flashcard ideas
- name every stage of the full system in order.
- throughput vs latency — the difference?
- which stage bottlenecks first at 10×, and why?

_Journal: the one-paragraph pitch of the whole system, in your words._
