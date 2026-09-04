# Day 10 — LangChain: write scores back to Postgres from Python

- [ ] Done

**After this you should know:** how the Python classifier persists to the *same* database
your Node app uses — two services, one source of truth.

## 📖 Read (~15 min)
[psycopg 3 — Basic usage](https://www.psycopg.org/psycopg3/docs/basic/usage.html). Get:
connect, parameterized queries, commit — Python's version of what `db.js` does in Node.

## 🛠️ Build (~20 min)
Connect the Python chain to your Railway Postgres and **upsert** axis scores into
`item_axis_scores` (`ON CONFLICT (item_id, axis)` — idempotent, same key as Node). Run on a
few items; check the rows in the DB.

## 🤖 Claude-craft (~10 min)
Read [Slash commands](https://docs.claude.com/en/docs/claude-code/slash-commands); note one
repeatable task worth a custom command.

## 🔗 Network (if Thursday)
Reach: one genuine note.

## ✍️ Journal
One line: two services writing the same table — what keeps them from stepping on each other?
