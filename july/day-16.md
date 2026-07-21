# Day 16 — Deepen: reliability (rate limiting, retries/backoff on Browse)

- [ ] Done

**After this you should know:** how to make the eBay calls survive the real world — rate limits and transient failures — instead of falling over.

## Do (~1 hr)
The Browse API has rate limits and will occasionally fail. Add: a small delay between search calls, and a retry-with-backoff around the fetch (try, wait, try again, then give up). Log when a retry fires. *(This is where the old "error handling — retries, giving up" fundamental lands, applied to real API calls.)*
Analogy: a retry policy on a callout — but you own the policy and the backoff now.

## 3 flashcard ideas
- What is exponential backoff and why not just retry immediately?
- Three failure modes an API client must handle.
- When do you stop retrying and give up?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
