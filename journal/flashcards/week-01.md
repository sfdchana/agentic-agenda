# Week 1 flashcards — LLM & agent fundamentals

Covers days 01, 02, 18, 03, 04. Q on top, A below. Review by covering the answer.

---

## Day 01 — The agent mental model

**Q:** What is an agent, in three parts?
**A:** A **model + tools + a loop.** The model decides → calls a tool → sees the result → decides again, until it's done.

**Q:** Agent vs workflow — the core difference?
**A:** In a **workflow, *you* define the steps** (fixed control flow). In an **agent, *the model* decides the steps** at runtime (dynamic control flow). Use a workflow when the path is knowable up front; an agent when it isn't. Most "AI features" should be workflows.

**Q:** Name the workflow patterns.
**A:** Prompt chaining · routing · parallelization (sectioning + voting) · orchestrator-workers · evaluator-optimizer.

**Q:** Prompt chaining — what is it and what's the tradeoff?
**A:** Break a task into sequential steps, each prompt building on the last. Trades **higher latency** (multiple calls) for **higher accuracy**.

**Q:** Routing — what is it?
**A:** Classify the input, then send it down the matching **specialized path** (a different prompt, tool, or model). (SF analogy: assignment rules.)

**Q:** Parallelization — its two flavors?
**A:** **Sectioning** = split into *independent* subtasks run at once. **Voting** = run the *same* task several times for diverse outputs, then aggregate.

**Q:** Orchestrator-workers vs parallelization?
**A:** Parallelization runs **predefined** subtasks concurrently. Orchestrator-workers: a central model **decides the subtasks at runtime** — dynamic, not predefined.

**Q:** Evaluator-optimizer?
**A:** A generate → critique → revise loop where one LLM produces and **another LLM** evaluates it (both are models, not a human). (SF analogy: an approval process where author and reviewer are both AI.)

---

## Day 02 — Tokens & context windows

**Q:** What is a token?
**A:** The chunk of text a model reads/generates — on average **~¾ of a word (~4 chars)**. Common words = 1 token; rare words split into several; punctuation and spaces count too.

**Q:** What is the context window?
**A:** The **finite maximum tokens** (input + output + tool results + thinking) that must fit in one turn. A hard ceiling you now manage yourself.

**Q:** Do token counts transfer across models?
**A:** **No.** Different models use different tokenizers, so the same text can be ~20–30% more tokens on one model than another. Measure per model.

**Q:** Why does JSON/code tokenize "heavier" than prose?
**A:** All the quotes, braces, and field names are tokens too — structured text packs **more tokens per word** than plain English.

**Q:** Two reasons tokens matter?
**A:** **Cost** (you pay per token, in and out) and **limits** (everything must fit the context window).

---

## Day 18 — Prompt engineering fundamentals

**Q:** What can prompt engineering fix — and what can't it?
**A:** It fixes **quality/behavior** problems. It **can't** fix **system** problems (latency, cost, capability) — those need a different model or architecture.

**Q:** The "smart but new to your world" principle?
**A:** Treat the model as intelligent but with **no context on your specifics.** Give it the **relevant** background it needs — quality/relevance of context beats raw quantity (irrelevant context dilutes *and* costs tokens).

**Q:** The highest-leverage prompt techniques?
**A:** Be clear and direct · give **examples** (multishot) · **let it think** (chain-of-thought) · use **structure** (XML tags) · give it a **role** (system prompt).

**Q:** How do you get a model to write in *your* voice (avoid AI slop)?
**A:** Feed it **2–3 examples of your actual writing** (multishot) + an explicit description of the voice. Examples of your own writing is the strongest anti-slop lever.

**Q:** Why does matching prompt style to output style work?
**A:** The model **mirrors** the tone/format of the prompt — so write the prompt in the voice you want the output in.

---

## Day 03 — First raw API call

**Q:** What is an LLM API call, mechanically?
**A:** An **HTTP POST** with three parts: the **endpoint** (URL), **headers** (API key + version), and a **JSON body** (model, max_tokens, messages). Everything else (SDKs, LangChain) is sugar on top of exactly this.

**Q:** Where does the model's text live in the response?
**A:** `content[0].text`. `content` is a **list** — because a response can hold multiple blocks (text now; tool calls later).

**Q:** What does the `usage` field tell you?
**A:** `input_tokens` and `output_tokens` — what you were charged, in tokens. Day 2 made real.

**Q:** What is `stop_reason` and why care?
**A:** *Why* the model stopped: `end_turn` = finished naturally · `max_tokens` = hit the length cap · (later) `tool_use` = wants a tool. It's the exact signal the **agent loop** uses to decide stop vs. continue.

---

## Day 04 — Sampling params & streaming

**Q:** What does `temperature` control?
**A:** **Randomness.** Low (0) = focused/repeatable; high (1) = varied/creative.

**Q:** What does `max_tokens` do?
**A:** Caps output **length.** If hit, the response is cut off mid-answer and `stop_reason` = `max_tokens`.

**Q:** What is streaming, and what does it actually change?
**A:** Tokens are sent/printed **as they're generated** instead of all at once. Total time is ~the same — it changes **perceived** latency (feels instant). A UX lever, not a speed one.

**Q:** What is `top_p` (nucleus sampling)?
**A:** Keep only the top tokens whose probabilities **sum to p**, drop the tail, then sample from what's left. Another way to control randomness.

**Q:** temperature vs top_p — the rule?
**A:** Both control randomness by different mechanisms (temperature **reshapes** the distribution; top_p **truncates** the tail). **Tune one, not both.**
