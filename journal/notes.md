# Notes — running log

_One or two lines per session. Newest at the top._

July 13: agent = model owns the steps; workflow = I own the steps. There are various types of workflows that can be used if steps are known and an agent can be used when steps are uknown and need to be determined based on input which is also unkown.

July 14: * context windows describe the data or tokens (as all input and output are measured with anthropic), available to the llm or agent within the context of the task or conversation. There are different strategies available to condense (server side compaction), clear (empty thinking blocks) and retain context for different use cases, with the main use case being limits on context.
* token counting refers to an endpoint that can tally up tokens in any type of input (image, pdf, tool, words etc) and generate the total count which is helpful when scaling use cases for prompts and inputs and wanting to govern usage limits.

July 15/Skipped to Day 18:
 * Prompt engineering can help solve a lot of gaps in responses from an llm, but things like latency and other similar system issues would be better solved with a different model, not a different prompt.
* The more context you include in your prompt the better. Assume claude is intelligent but new to your world and the more background the better the response will be.
* Give examples to guide Claude even more.
* Match the style of your output desired to the style of your prompt. (I found this one interesting)
* Using models in parallel can maximize efficiency and do a few steps in one.
* Techniques that would be applicable to me: I think giving claude prompts in the style of desired output would be good for structuring a taste profile so that I can control most of the copy and keep it to an editorial voice instead of it generating AI slop that's recognizable as non human.also research and information gathering

July 16: ran my first anthropic api call from python: ! stop_reason is how the agent loop knows to stop
July 17: 
tempature = how random/deterministic the result is, 0 will be the same or similar and increased tempature inc
max tokens = length cap, how long the answer can be
top_p = this is nucleus sampling which means it truncates the distribution by chopping off the unlikely tail, then picks from what's left. It changes how much of the list is even eligible and it's different from tempature because is just how adventouresly you pick.
Analogy: temperature = how much you trust the rankings; top_p = how far down the rankings you're allowed to reach at all.
streaming is basically when the llm shows the answer as it's ready like the typing effect. this way the latency appears quicker than it is because the user starts seeing the answer as it's ready instead of waiting for it all at once.

July 20: 
