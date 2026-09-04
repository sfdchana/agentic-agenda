# Day 1 — Harden: rate limiting & respecting the API

- [ ] Done

**After this you should know:** why you pace calls to an external API, and how to keep
your pipeline from getting throttled or banned.

## 📖 Read (~15 min)
[Stripe — Rate limiters](https://stripe.com/blog/rate-limiters) (skim the token-bucket
idea). Get: why and how services cap request rate — and why you self-throttle.

## 🛠️ Build (~20 min)
Add simple pacing to the eBay pipeline ([run.js](../../houseofsof-api/houseofsof-api/src/pipeline/run.js)):
a small delay between calls, or a concurrency cap. Pick up where the pipeline left off.

## 🤖 Claude-craft (~10 min)
Create or improve [`CLAUDE.md`](https://docs.claude.com/en/docs/claude-code/memory) in
`houseofsof-api` — describe the repo and the pipeline in a few lines.

## 🔗 Network (if Monday)
Research: one company you'd love to work at, confirm Salesforce, note one person.

## ✍️ Journal
One line: what rate is "polite" for the eBay API, and how did you decide?
