# Day 02 — Tokens and context windows

- [x] Done

**After this you should know:** what a token is, why context is finite, and how that drives cost and design.
context windows describe the data or tokens (as all input and output are measured with anthropic), available to the llm or agent within the context of the task or conversation. There are different strategies available to condense (server side compaction), clear (empty thinking blocks) and retain context for different use cases, with the main use case being limits on context.

token counting refers to an endpoint that can tally up tokens in any type of input (image, pdf, tool, words etc) and generate the total count which is helpful when scaling use cases for prompts and inputs and wanting to govern usage limits.

## Do (~1 hr)
Read Anthropic's docs on tokens and context windows. Paste your taste-schema JSON into a tokenizer and see how it tokenizes. Note the context limit and price-per-token of the model you'll use.
Analogy: the context window is like a governor limit — but *self-managed*. You decide what stays in it.

## 3 flashcard ideas
- A token is roughly ___.
- Why is the context window finite, and what happens when you exceed it?
- How does token count map to cost?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
