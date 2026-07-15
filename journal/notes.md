# Notes — running log

_One or two lines per session. Newest at the top._

July 13: agent = model owns the steps; workflow = I own the steps. There are various types of workflows that can be used if steps are known and an agent can be used when steps are uknown and need to be determined based on input which is also unkown.

July 14: * context windows describe the data or tokens (as all input and output are measured with anthropic), available to the llm or agent within the context of the task or conversation. There are different strategies available to condense (server side compaction), clear (empty thinking blocks) and retain context for different use cases, with the main use case being limits on context.
* token counting refers to an endpoint that can tally up tokens in any type of input (image, pdf, tool, words etc) and generate the total count which is helpful when scaling use cases for prompts and inputs and wanting to govern usage limits.

  
