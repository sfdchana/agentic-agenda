# Foundations — Salesforce → Software Engineering
### The mindset shift, prioritized for a data + AI lane

The real news, and it's good: the hard parts of engineering — complex business
logic, data modeling, enterprise architecture, owning delivery — I already do.
The gap isn't *coding*. It's moving from a **managed platform that hides the
machine** to **systems I own end to end**, where *I* define the limits instead of
the platform handing them to me.

This is the map of that shift. It's deliberately **prioritized for my lane**
(data + AI engineering in Python), not a generic "become a Java backend dev"
checklist — see the language note below.

## The core reframe: I define the limits now
In Salesforce, governor limits are hard walls the platform sets to keep me
efficient (SOQL rows, CPU time, heap). In real software, **nothing throws a
"too many queries" error.** If 10k requests/sec hit my service, it doesn't hand
me a governor limit — it runs out of memory and falls over. Predicting and
designing for *hardware* limits (CPU, RAM, disk I/O, network, connection counts)
*before* they hit is **capacity planning**, and it's the single biggest change in
how I think. Every limit is now mine to reason about.

## The gap map (with priority for my lane)

| Area | Salesforce (have) | Custom software (gap) | Priority for data/AI |
|---|---|---|---|
| Infrastructure | Managed, auto-hosted | I host it (Railway / AWS / GCP) | High — already doing it (Railway) |
| Scaling & limits | Governor limits | Resource limits I design for | High — capacity thinking |
| Databases | SOQL on a hidden schema | SQL vs NoSQL, indexing, pooling, caching (Redis) | **Highest — this *is* the lane** |
| Deployment | Changesets, SFDX | Docker, CI/CD (Kubernetes later) | Medium — Docker yes, K8s awareness |
| Concurrency | Queueable, Batch, Platform Events | Async workers, message brokers (Kafka) | Medium — workers/queues yes |
| Architecture | Trigger vs Flow vs Apex | Distributed systems, services, load balancing | Medium-High — system design |
| Lifecycle | Platform runs it | I own the OS (Linux), build, container, runtime | Medium — enough to deploy + debug |

## The three mindset shifts
1. **I own the limits** (capacity planning) — above.
2. **System design *is* distributed-systems design** — not "Trigger or Flow?" but
   "where do the boundaries go, what owns the data, what's the contract, what can
   scale or fail independently?" I already started this instinct: one Postgres,
   multiple bounded services against it.
3. **I own the full lifecycle** — the language, the OS, how code builds and runs
   in a container. Nothing is auto-wrapped anymore.

## Language note — an important correction
Generic SF→SWE advice says "pick Java/Spring or C#/.NET because the syntax mirrors
Apex." True for a *classic backend* target — but the **wrong optimization for my
lane.** Data + AI lives in **Python** (model SDKs, LangChain/LangGraph, pandas, ML
tooling) with **TypeScript** for the frontend/edge. Staying Python isn't the easy
way out — it's the *correct* home base for where I'm going. No Java detour.

## Prioritized action — what to actually go deep on
- **Highest — Data.** SQL beyond ORMs (already writing raw SQL in taste-search),
  indexing, query plans, connection pooling, caching (Redis), and the
  SQL-vs-NoSQL / when-to-reach-for-what judgment. Core of the lane.
- **High — Capacity & system design.** Reason about RPS, latency, cost, and where
  things fail; draw the diagram and defend the boundaries.
- **Medium — Docker / containers.** Write a Dockerfile, build an image, run it
  locally (already touched via Railway + the houseofsof Dockerfile).
- **Medium — Async / workers / queues.** Background workers, retries, idempotency
  — the ingestion pipeline teaches this directly.
- **Awareness only (not now).** Kubernetes, microservices-at-scale, Kafka — know
  what they are and when they'd matter; don't rabbit-hole before I need them.
- **Read slowly, all year.** *Designing Data-Intensive Applications* (Kleppmann)
  — the gold standard for how data moves across servers. Directly my lane.

## How this connects to the build plan
Fundamentals are **woven into the builds, not front-loaded** — learned applied,
which sticks better than abstract study:
- SQL depth, indexing, idempotency, dedup, containerization → **Month 2** (ingestion)
- Async workers, retries, scheduling → **Month 2–3**
- Resource limits, caching, gateways, cost budgets, streaming → **Month 5** (hardening)
- System design (data + AI flavored) → reps in **Month 6 / Part 2**
- Capacity mindset + DDIA → a slow ongoing read from day one

The only genuinely *upfront* piece is the **mindset reframe** in this doc — worth
internalizing in Week 1, because it changes how I read everything after.
