# Day 18 — Prompt engineering fundamentals

- [x] Done

**After this you should know:** the levers that actually move output quality.

## Do (~1 hr)
Read Anthropic's prompt-engineering docs. Take your Day 05 classify prompt and improve it (clear role, examples, explicit output contract); measure the difference across a few pieces.

## 3 flashcard ideas
- Three prompt levers that reliably help.
- Why do examples (few-shot) improve output?
- The "output contract" idea.

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
Prompt engineering:

* Prompt engineering can help solve a lot of gaps in responses from an llm, but things like latency and other similar system issues would be better solved with a different model, not a different prompt.
* The more context you include in your prompt the better. Assume claude is intelligent but new to your world and the more background the better the response will be.
* Give examples to guide Claude even more.
* Match the style of your output desired to the style of your prompt. (I found this one interesting)
* Using models in parallel can maximize efficiency and do a few steps in one.
* Techniques that would be applicable to me: I think giving claude prompts in the style of desired output would be good for structuring a taste profile so that I can control most of the copy and keep it to an editorial voice instead of it generating AI slop that's recognizable as non human.also research and information gathering
