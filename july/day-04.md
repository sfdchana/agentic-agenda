# Day 04 — Sampling params and streaming

- [x] Done

**After this you should know:** what temperature / top_p / max_tokens do, and how streaming works.
tempature = how random/deterministic the result is, 0 will be the same or similar and increased tempature inc
max tokens = length cap, how long the answer can be
top_p = this is nucleus sampling which means it truncates the distribution by chopping off the unlikely tail, then picks from what's left. It changes how much of the list is even eligible and it's different from tempature because is just how adventouresly you pick.
Analogy: temperature = how much you trust the rankings; top_p = how far down the rankings you're allowed to reach at all.
streaming is basically when the llm shows the answer as it's ready like the typing effect. this way the latency appears quicker than it is because the user starts seeing the answer as it's ready instead of waiting for it all at once.
## Do (~1 hr)
Re-run Day 03 varying `temperature` and `max_tokens`; observe the difference. Then set `stream=True` and print tokens as they arrive.

## 3 flashcard ideas
- temperature vs top_p — what each controls.
- What does max_tokens actually cap?
- Why stream a response?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
