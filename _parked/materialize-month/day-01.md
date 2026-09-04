# Day 1 — Portal: serve the axis scores through the API

- [ ] Done

**After this you should know:** how the scores you persisted become a *resource* the
front end can ask for — the join from `items` to `item_axis_scores`, exposed over HTTP.

## 📖 Read (~15 min)
[REST resource naming](https://restfulapi.net/resource-naming). Get: URLs name *things*
(nouns), methods are the verbs — how to shape a clean endpoint.

## 🛠️ Build (~20 min)
Add an admin route that returns each pending item **with its axis scores** joined in
(`LEFT JOIN item_axis_scores`). Pick up from `classify-items.js` now persisting scores —
this is the read side.

## 🤖 Claude-craft (~10 min)
Read what a [`CLAUDE.md`](https://docs.claude.com/en/docs/claude-code/memory) is, then
create or improve one in `houseofsof-api` describing the repo in a few lines.

## 🔗 Network (if Monday)
Research: find one company you'd love to work at, confirm it uses Salesforce (quick
Google), note one person there.

## ✍️ Journal
One line: what shape did you give the endpoint, and why?
