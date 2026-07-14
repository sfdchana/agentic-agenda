# July — Month 1: LLM + agent fundamentals
Starts July 13. Theme: LLM working knowledge + the agent loop, built from scratch.
Home base is **Python** (my target language); analogies lean on **Apex /
Salesforce** — the stuff I already know deeply. Python gets solidified in Week 3,
TypeScript ramps in Week 4.

**Setup (alongside Week 1, ~15 min total):** install `uv` (Python envs), and
`pnpm` + `tsx` (TS) so Weeks 3–4 have zero environment friction. Optional but
recommended: Anki for spaced-repetition flashcards.

**Format:** one file per session, ~1 hr each, ~5 per week. Each file says what
you should know after, links to go deeper, and has **3 flashcard ideas** — not
finished cards. Rewrite the ones worth keeping in your own words (the rewriting
*is* the encoding). Check the box in the file **and** on this list when done.
Last 2 minutes of every session: a line or two in `../journal/` (log, open
questions, ideas — see its README); prefix a-ha lines with `!` and card them
next session.

### Week 1 — LLM fundamentals (Python)
- [ ] day-01 — The agent mental model
- [ ] day-02 — Tokens and context windows
- [ ] day-03 — First raw API call in Python (no SDK)
- [ ] day-04 — Sampling params and streaming
- [ ] day-05 — Structured outputs (reliable JSON)

### Week 2 — Tool calling and the agent loop (Python)
- [ ] day-06 — Tool calling mechanics: one tool, full round trip
- [ ] day-07 — Build the loop: agent = model + tools + while loop
- [ ] day-08 — Add a second tool; watch context and cost grow
- [ ] day-09 — Error handling: malformed args, retries, giving up
- [ ] day-10 — Write up your raw-agent lessons (publishable notes)

### Week 3 — Python depth (for an Apex dev), in agent context
- [ ] day-11 — Python idioms for a Salesforce dev
- [ ] day-12 — Classes, decorators, context managers
- [ ] day-13 — Solidify the agent with the Anthropic SDK
- [ ] day-14 — pytest + type hints: test your tool dispatch
- [ ] day-15 — asyncio basics vs Apex async

### Week 4 — TypeScript ramp + prompt/context engineering
- [ ] day-16 — Pure TS: types, interfaces, pnpm/tsx
- [ ] day-17 — Pure TS: async/await + fetch — call Claude from TS
- [ ] day-18 — Prompt engineering fundamentals
- [ ] day-19 — Prompt caching and the cost levers
- [ ] day-20 — Context engineering (the month's capstone concept)

### Week 5 — Consolidation
- [ ] day-21 — MCP: run an existing server against your agent
- [ ] day-22 — Model landscape: same task, 3 models, compare
- [ ] day-23 — Hand-rolled mini-eval of your agent (Month 2 teaser)
- [ ] day-24 — Ship it: agent repos to GitHub with honest READMEs
- [ ] day-25 — Month review + all-flashcard review; sketch Month 2

**After this month you should know:** how LLM APIs actually work (tokens,
sampling, streaming, caching), how to build a tool-using agent from scratch in
Python, enough TypeScript to call models comfortably, and the vocabulary of
prompt and context engineering — with two documented repos on GitHub.
