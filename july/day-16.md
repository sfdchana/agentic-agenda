# Day 16 — Deepen: reliability (rate limits, retries, backoff)

- [ ] Done

**After this you should know:** how to make eBay calls survive the real world — rate limits and transient failures — instead of falling over. Core infra-lane skill.

## 📖 Read first (~20 min)
AWS Builders' Library — *"Timeouts, retries, and backoff with jitter"* (aws.amazon.com/builders-library). This is canonical. Get: **exponential backoff**, why you add **jitter**, what a **retry storm** is, and when to stop retrying and fail.

## Do (~30 min) — direct it, don't grind it
Add to the Browse calls: a small delay between searches, and a **retry-with-backoff** around each fetch (try → wait longer each time → give up after N). Log when a retry fires. Direct the resilience logic; understand each knob.

## Understand & defend (~10 min, journal it)
Why does retrying *immediately* make an overloaded API worse? What does jitter prevent? Why cap the retries at all?

## 3 flashcard ideas
- what is exponential backoff, and why not retry instantly?
- what is jitter, and what problem does it solve?
- when do you stop retrying and fail?

_Journal: which failure mode you hadn't considered before reading this._
