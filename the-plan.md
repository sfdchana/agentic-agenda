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
