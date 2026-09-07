# Day 3 — Harden: error handling & partial failure

- [x] Done

**After this you should know:** how to make a batch pipeline resilient — one bad item
doesn't sink the whole run, and re-running is always safe.

## 📖 Read (~15 min)
[The Twelve-Factor App — Disposability](https://12factor.net/disposability) (recap). Get:
processes should fail fast and be safe to restart.

## 🛠️ Build (~20 min)
Make the pipeline fault-tolerant: wrap each item in try/catch, log-and-continue on
failure, and confirm the idempotent upsert means a re-run resumes cleanly (judge-once).

## 🤖 Claude-craft (~10 min)
Read the [Agent Skills overview](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview);
open one skill and note how it's structured.

## 🔗 Network (if Thursday)
Reach: one genuine note to the person you noted Monday.

## ✍️ Journal
One line: what's the worst thing that can happen mid-run now, and is it survivable?
