# Day 15 — Chunk 4: Wire UI → API (taste-ranked results, live)

- [ ] Done

**After this you should know:** how a frontend talks to your own API, and why every data fetch has three states you must handle — the first end-to-end slice, live on your site.

## 📖 Read first (~20 min)
A piece on the **loading / empty / error** UI states (search "the three states of a data fetch" or an article on UI states) plus a short **REST API design** primer. Get: the *client-server contract* — the frontend asks, the backend answers, and you must design for the answer not arriving.

## Do (~35 min) — direct it, don't grind it
Swap the fake data for a real `fetch` to your taste-ranked endpoint. Handle loading, empty, and error explicitly. Confirm real eBay pieces, ordered by taste, render on houseofsof.com.

## Understand & defend (~5 min, journal it)
Why are the *empty* and *error* states as important as the happy path? What does the user see for each if you skip them?

## 3 flashcard ideas
- the three states every data fetch must handle?
- what is the client-server "contract"?
- what's now true end-to-end that wasn't at month's start?

_Journal: the first time real, taste-ranked pieces rendered on your own site._
