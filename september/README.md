# September — Month 3: AI classification layer (LangChain / LangGraph)

_Hybrid month: **Week 1** finishes the ingestion pipeline (August's leftovers —
reliability + architecture) so the data is solid; **Weeks 2–4** put AI *on* that clean
data — LangChain chains → a LangGraph classify→self-check→route flow → a machine-vs-me
correction dataset._

**Deliverable:** `taste-classifier` — a LangGraph pipeline that scores pieces on your taste
axes, checks its own work, routes low-confidence cases to human review, and accrues a
correction dataset (the eval set for Month 4).

**Stack note:** Weeks 2–4 are **Python** (LangGraph is Python-first, and Python is your
plan's "home base"). You'll stand up a small Python classifier service *beside* your Node
API — both talk to the same Railway Postgres. This is the data/AI-eng skill your target
jobs list, so the new stack is the point, not a detour.

## The daily shape (weekdays, ~45–60 min)

- **📖 Read (~15 min)** — one real article, tied to that day's build.
- **🛠️ Build (~20 min)** — the *real* project. **Rule: pick up where I left off.** Even
  10 minutes counts; it always advances the actual thing.
- **🤖 Claude-craft (~10 min)** — one small rep at building *with* Claude (skills,
  connectors, `CLAUDE.md`, subagents, slash commands). Compounds; pays off at work.
- **🔗 Network (Mon & Thu)** — Mon = research one company you'd love that uses Salesforce;
  Thu = send one genuine note. Light, sustainable.
- **✍️ Journal (~2 min)** — one line.

## The build arc

- **Week 1 (days 1–5) — Harden ingestion:** rate limiting, retries/backoff+jitter, error
  handling, a scheduled worker, and an architecture write-up. Closes August; ships
  `archive-ingest` documented.
- **Week 2 (days 6–10) — LangChain:** Python env, structured-output chains with Pydantic,
  port the classifier to a chain, write scores back to Postgres from Python.
- **Week 3 (days 11–15) — LangGraph:** the stateful graph — classify → self-check → route
  — run on real items.
- **Week 4 (days 16–20) — Machine-vs-me + ship:** store ai vs human classification,
  batch-classify the backlog, find "confident-and-wrong," write it up, post to LinkedIn.

## Claude-craft ladder (the 🤖 lane, in order)

CLAUDE.md → project rules → read skills → build a skill → refine it → connectors/MCP →
subagents → slash commands → chaining → scheduled jobs/hooks. Each day names the rep.

## Networking cadence (the 🔗 lane)

Mon = research (company + one person, confirm Salesforce). Thu = reach (one genuine note).
Target in play: GOAT Group (Culver City). Ties to `job-listing-compiler`. See
[next-month-ideas.md](next-month-ideas.md).

_The visible product layer (taste-map, slider-search, deploy, LinkedIn) is parked in
[`_parked/materialize-month/`](../_parked/materialize-month/README.md) for a later month._
