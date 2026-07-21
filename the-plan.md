# The Plan — Part 1: Jul 13 2026 → Jan 13 2027
### Out of the Salesforce ecosystem, into data + AI engineering

Six months, ~5 hrs/week (5 weekday sessions, ~1 hr each). The plan assumes 5 hrs
and no more — extra time is a bonus, not a dependency.

**Where this is going.** The ~12-month goal is to build the skills and the track
record to earn an internal engineering title at my current company — Lead AI
Engineer / Senior Software Engineer, something not Salesforce-bound — around
mid-2027. Landing a non-Salesforce title *first* makes the 12–18 month external
job search that follows far easier. **This is Part 1** (Jul 13 – Jan 13); I'll
write Part 2 in December, once I see how the first half actually went.

**January is a checkpoint, not a finish line.** By Jan 13:
- one clean, finished project live on my website,
- LinkedIn updated with the end-to-end outcomes I've owned at work,
- resume rewritten + a target-company list drafted (for later, not to apply yet).

**Focus.** Preparing clean, structured data for AI is the part that matters most.
Around it: Python (home base), TypeScript, LangChain, LangGraph, Braintrust
(evals), Langfuse (tracing). The vehicle is real fashion-tech / resale-market
data projects (House of Sof) — every skill learned by shipping something I can
defend architecturally.

**Foundations (woven in, not front-loaded).** Coming from Salesforce, the real
shift is from a managed platform to systems I own — capacity, databases, system
design, the full lifecycle. I learn these *applied* inside the build months, not
as a separate phase (see `foundations.md` for the gap map and where each shows
up). The one upfront piece is the mindset reframe — read it Week 1. Ongoing all
year: *Designing Data-Intensive Applications*, slowly. Home base stays **Python**
(+ TS) — no Java/Spring detour; that points away from the data/AI lane.

**How detail works.** Monthly folders named for the month each starts in (months
run ~mid-month to mid-month). December folds in holiday slack.

---

## Parallel track — at work (runs continuously)
Not week-by-week; these compound the whole time and *are* the title-change case:
- Take on non-Salesforce projects — distributed systems, AWS / cloud, integrations
  — and **own them end-to-end and document the outcomes** (these become LinkedIn
  bullets and the argument for the title).
- Partner regularly with the process-excellence director and the business side;
  map end-user workflows to find where AI (in and out of Salesforce) adds real
  efficiency.
- Keep leading the two admins: groom, assign, oversee. Run grooming **2×/month**.
  Own delivery and write down what shipped and its impact.

---

## Active Build — taste-enabled discovery (the thing I ship continuously)
The product I actually care about, and the through-line the monthly layers feed.

**The problem I'm solving.** Resale is chaos — tens of thousands of listings, no
way to surface the *right* things. The product cuts through it: **taste-enabled
discovery over live eBay listings, displayed beautifully on my website.**

**The vision (directional, refined as I build).**
- a taste profile (start with *mine*; maybe let a user build their own later)
- → eBay **Browse API** pulls candidates out of the chaos
- → a **taste layer** ranks/filters for "this is the right *kind* of thing"
- → surfaced in a clean, beautiful UI on houseofsof.com.

The monthly deliverables below aren't separate projects anymore — they're the
**layers of this one product** (ingestion → classification → evals → semantic
search → polish).

**Own before I extend — comprehension is step zero.** Much of this is already
built (`houseofsof-api`), but built *for* me, not in a way I can defend yet.
Before adding anything I walk the existing architecture until I can whiteboard it
and justify every choice. Reading rides *alongside* each chunk, not front-loaded.

**Honest inventory of what exists right now.**
- ✅ **Live admin search** (`routes/ebay.js`) — modern **Browse API** over OAuth
  (client-credentials), token-cached. Working; it's the portal I use.
- ⚠️ **Auto-pipeline** (`scrapers/ebay.js` + `run.js`) — full loop (fetch →
  normalize → dedup → score → insert) but built on eBay's **Finding API, which
  eBay shut down in early 2025.** It no longer produces anything. Reviving +
  modernizing it onto Browse is the first real build.
- ✅ **Postgres `items` table**, scoring/filter `rules.js`, `normalizer.js`,
  admin review UI.

**Near-term ladder (session-sized chunks, comprehension first).**
- **Chunk 0 — Understand + defend what exists.** Walk `routes/ebay.js`,
  `scrapers/ebay.js`, `run.js`, `normalizer.js`, the `items` schema. Draw the
  architecture diagram *myself*. Reading: eBay Browse API (`item_summary/search`),
  OAuth client-credentials, why REST/Browse replaced the old Finding API.
  *Output: a diagram + a paragraph defending each boundary — the thing I can't do today.*
- **Chunk 1 — Revive the pipeline on Browse.** Lift the working OAuth + Browse
  call from `routes/ebay.js` into `scrapers/ebay.js`; point `fetchEbay()` at
  `/buy/browse/v1/item_summary/search`. *Output: one real search returning live items in the terminal.*
- **Chunk 2 — Fix the normalizer.** Map the Browse response shape to the `items`
  columns (field names differ from Finding). *Output: real rows flowing into Postgres again — the archive fills itself.*
- **Chunk 3 — The taste layer.** Wire the Day-5 classifier onto incoming items so
  each gets a taste read; rank by *fit*, not just price. *Output: results ordered by taste, not noise.*
- **Chunk 4 — Make it beautiful on the site.** A clean discovery UI on
  houseofsof.com over the taste-ranked results (design + refine in Claude Design
  in downtime). *Output: the thing I actually wanted to look at.*

Months 3–5 below then deepen this *same* product (LangGraph classification, evals
on my own corrections, pgvector "find similar"). Same spine, more layers.

**Daily shape (flipped for momentum).** The build is the spine — most of each
session moves this product forward; fundamentals ride along when a chunk needs
them (the `foundations.md` philosophy). Reading is attached to the chunk it
serves. This is what replaces the "learn an hour, maybe build 15 min" order that
felt slow.

---

## Month 1 — july/ (Jul 13 – ~mid-Aug) — LLM + agent fundamentals (Python)
Build a tool-using agent from scratch to learn how LLM APIs really work. Full
detail + daily session files live in `july/`.
- W1: LLM fundamentals — tokens, raw API call, sampling, streaming, structured
  output (Pydantic; classify a real archive piece).
- W2: Tool calling + the agent loop — one tool → the while-loop agent → watch
  cost/context grow → error handling → write it up.
- W3: Python depth for an Apex dev — idioms, classes/decorators/context managers,
  port to the Anthropic SDK, pytest + type hints, asyncio.
- W4: TypeScript ramp + prompt/context engineering — call Claude from TS; prompt
  fundamentals, caching, context engineering (capstone).
- W5: Consolidation — MCP, a 3-model comparison, a hand-rolled mini-eval (Month 2
  teaser), ship repos with honest READMEs.
**Deliverable:** a from-scratch agent + a taste-classifier, both public with
design-doc READMEs.

## Month 2 — august/ (~Aug 13 – Sep 12) — Ingestion pipeline (clean data engineering)
The most important skill, front-loaded: messy external data → clean structured rows.
- W1: eBay API — auth, search, the shape of raw data; map it to the archive schema.
- W2: Normalize + write — idempotent upserts, dedup, the transform layer.
- W3: Reliability — rate limiting, retries/backoff, error handling, a scheduled worker.
- W4: Architecture write-up — boundaries, idempotency, what breaks at 10x.
**Deliverable:** `archive-ingest` — a real pipeline feeding the archive, documented.

## Month 3 — september/ (~Sep 13 – Oct 12) — AI classification layer (LangChain / LangGraph)
Put AI *on* the clean data: classify ingested pieces, human-in-the-loop.
- W1: LangChain — structured-output chains; port the Month-1 classifier to a chain.
- W2: LangGraph — a classify → self-check → route flow with state.
- W3: Machine-vs-me — store `ai_classification` + `human_classification`; the
  divergence *is* the dataset.
- W4: Batch-classify the backlog; write up where the model is confident-and-wrong.
**Deliverable:** `taste-classifier` with a human-correction dataset accruing.

## Month 4 — october/ (~Oct 13 – Nov 12) — Evals + observability (the differentiator)
The thing most people skip. My corrections are already an eval set.
- W1: Braintrust — dataset from real corrections; exact-match + rubric graders.
- W2: Langfuse — trace the classification pipeline; categorize failures.
- W3: LLM-as-judge and its pitfalls; evals running in CI like a test suite.
- W4: Close the loop — improve the prompt/graph from eval results; measure the lift.
**Deliverable:** eval harness + tracing, with a before/after story.

## Month 5 — november/ (~Nov 13 – Dec 12) — RAG, retrieval, production hardening
- W1: pgvector — embed pieces; semantic "find me things like this" over the archive.
- W2: Hybrid search + reranking; eval retrieval separately from generation.
- W3: Production — retries/fallbacks, a gateway (LiteLLM), cost budgets, streaming.
- W4: Security — prompt injection, tool-permission scoping; threat-model the classifier.
**Deliverable:** semantic taste-search in the app + a hardening write-up.

## Month 6 — december/ (~Dec 13 – Jan 13) — Package + career admin (the January checkpoint)
Lighter, holiday slack baked in. This month is about *presentation*, not new building.
- W1: Pick the strongest project; polish it to clean-and-finished and put it live on
  the website — READMEs, architecture decisions, and cost/eval notes up front.
- W2: LinkedIn — update with the end-to-end outcomes I've owned at work this half
  (the parallel-track wins) + the projects. Framed as impact, not tasks.
- Dec 20 – Jan 1: rest / overflow for anything that slipped.
- W3–4 (early Jan): resume rewritten data/AI-forward; target-company list drafted
  for the eventual search.
**Jan 13:** one finished showcase project live, LinkedIn current, resume + target
list ready. Then: write Part 2.

---

## Guardrails (how this fails, pre-empted)
- **Scope per project is fixed up front** — "done" defined like `taste-search` was.
  The refactor is more fun than the ship; ship first.
- **Every project gets a design-doc README** — code proves I build; the write-up
  proves I think in systems. This is what earns the title.
- **Clean data first, AI second** — ingestion + structured classification matter
  more than clever prompts.
- **5 hrs/week is the assumption, not the floor** — the plan survives a slow week.
