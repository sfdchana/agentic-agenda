# Day 2 — Harden: retries & backoff with jitter

- [ ] Done

**After this you should know:** how to survive transient failures without hammering the
API — the single most important reliability pattern.

## 📖 Read (~15 min)
[AWS — Exponential backoff and jitter](https://aws.amazon.com/blogs/architecture/exponential-backoff-and-jitter/).
Get: retry with growing delays + randomness so retries don't stampede.

## 🛠️ Build (~20 min)
Wrap the eBay fetch (and the Anthropic call) in a retry helper: exponential backoff +
jitter, capped attempts. One flaky response shouldn't kill the run.

## 🤖 Claude-craft (~10 min)
Add one **project rule** to `CLAUDE.md` (e.g. "all external calls go through the retry
helper").

## 🔗 Network
—

## ✍️ Journal
One line: why does jitter matter — what breaks without it?
