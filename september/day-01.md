# Day 1 — Harden: rate limiting & respecting the API

- [x] Done

**After this you should know:** why you pace calls to an external API, and how to keep
your pipeline from getting throttled or banned.

## 📖 Read (~15 min)
[Stripe — Rate limiters](https://stripe.com/blog/rate-limiters) (skim the token-bucket
idea). Get: why and how services cap request rate — and why you self-throttle.

Notes:
- rate limiters are a good way to ensure that an  API doesn't get overloaded and is able to handle different types and volumes of requests by putting limits on certain aspects of reaching the endpoint
- rate limiters let a server cap load so it stays healthy — and a well-behaved client paces itself to stay under that cap and never get rejected.

  
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
