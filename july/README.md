# July — Month 1 sessions

**Read this first — the model changed.** These days used to be a *learn-first*
syllabus (LLM fundamentals in order). As of **Session 6** we flipped to
**build-first**: the spine is now the **Active Build** — taste-enabled discovery
over eBay listings (see `../the-plan.md` → "Active Build"). Each day is now a
**build session** that moves the product forward, and the fundamentals get pulled
in *when a chunk needs them*, applied to real code instead of studied in the
abstract.

**Home base** stays **Python**; analogies lean on **Apex / Salesforce**. Cadence
and streak are unchanged — one ~1-hr session, most days. Last 2 min of every
session: a line in `../journal/` (log / question / idea); prefix a-ha lines with
`!` and card them.

**Done so far:** 01, 02, 18, 03, 04, 05 — the LLM fundamentals the build now
stands on (agent model, tokens, prompting, raw API call, sampling, structured
output).

### The chunks (from the plan) → the days
- **Chunk 0 — understand + *defend* the existing pipeline**
  - [ ] day-06 — Architecture tour: read + diagram your own pipeline
  - [ ] day-07 — Defend it: Browse/OAuth vs the dead Finding API
- **Chunk 1 — revive the pipeline on the Browse API**
  - [ ] day-08 — Lift OAuth + Browse into the scraper; one live search
- **Chunk 2 — fix the normalizer; real rows flow again**
  - [ ] day-09 — Map the Browse response shape → `items` columns
  - [ ] day-10 — Run end-to-end; dedup / idempotency check
- **Chunk 3 — the taste layer: classifier ranks incoming items**
  - [ ] day-11 — Wire the Day-5 classifier onto incoming items
  - [ ] day-12 — Rank by taste *fit*, not price; revisit scoring
  - [ ] day-13 — Write-up: how the taste layer decides; confident-and-wrong
- **Chunk 4 — beautiful discovery UI on the website**
  - [ ] day-14 — Design the discovery UI (Claude Design), static first
  - [ ] day-15 — Wire UI → API; taste-ranked results live on the site
- **Deepen + harden (pulled from the fundamentals library as needed)**
  - [ ] day-16 — Reliability: rate limiting, retries/backoff on Browse
  - [ ] day-17 — Scheduled worker: ingestion runs on a schedule
  - [x] day-18 — Prompt engineering fundamentals *(done early)*
  - [ ] day-19 — Python depth where it bit you: refactor the scraper clean
  - [ ] day-20 — pytest + type hints: test the normalizer
  - [ ] day-21 — "My taste as data": sketch the taste-profile model
  - [ ] day-22 — Cost + context awareness on batch classify
  - [ ] day-23 — Architecture write-up v2: the whole discovery system
  - [ ] day-24 — Polish the UI / responsive
  - [ ] day-25 — Month-1 wrap: README + demo; what shipped

**The old fundamentals are a library, not a march.** Tool-calling, the agent loop,
Python idioms, async, pytest, the SDK — they live on *inside* the days above,
pulled in the moment the build hits them.
