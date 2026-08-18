# Notes — running log

_One or two lines per session._

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

July 20: Pydantic is a pythan library that validates the shape of your data and also checks that real data matches it.

July 21: Looking at my existing ebay/data ingestion pipeline and answering some questions:
Why does the normalizer exist at all — why not just store eBay's raw JSON?
   * the normalizer is like a transformer, it exists to take raw, hard to read data from ebays response and parse it into categories and values that we build our system around and understand.
* There are two eBay integrations. Which is alive, which is dead, and why does that matter?
   * the finding api is dead, the browse api is alive. it matters because the finding api wont return anything it'll error out. The reason there's two is because i started with the finding and then kept erroring out and i reached out to ebay developers who said its been retired and replaced with browse api. future maintenance item is to deprecate the finding api from code.
* Dedup is keyed on source_url — why that field and not, say, name or price?
   * because it's a unique identifier and name or price are not, there can be many items with same names and prices.
* What's the difference between passes() and score() — why have both?
   * passes is whether it gets in the door as a data piece overall, score is the level it scores against everything else in the door once it's in.
* Why does every new row land as status='pending' instead of going straight live?
   * because we designed a human in a loop pattern and pending means that it's waiting for a human to decide.

July 22: 1. What does client-credentials OAuth prove, and how is it different from "log in with Google"? it identifies itself as the client via api key and receives a bearer token which is then stashed until expiry. different because log in with google requires human interaction? and logs in on behalf on person vs this is machine.
2. Why cache the token instead of fetching one per request? no need to fetch a new one each time since that would increase run time and latency, instead store token and only refetch if expired.
3. Why expire it 60 seconds early? so that you shouldn't run into issues with a token that is valid when fetch but expired once sent. This way is more safe.
4. In one sentence: why did eBay kill Finding in favor of Browse? browse api has a more modern rest security structure and finding api included the app id right in the query url.

July 23: Practiced running the call directly from a test script and saw the auth, headers, endpoint with token retrieved from cache or new and saw results.

July 24: Testing the normalizer on the api call and seeing issues with trying to put a brand in a defined picklist and separating brand from entire title. 

July 27: Idempotency, distributed system failure, and guardrails to protect in the event of different types of failure:
* idempotency key: the reason why this makes failures that could occur safe is because this is a unique id that is passed with every transaction so to say, and that is unique so if it knows if it's a duplicate means it's processed and shouldn't be processed again if it's not it isn't. 
* exponential backoff: if a system is continously down the and the client keeps trying backoff is a way of waiting exponentially longer between each try (i.e. 1, 2, 4 seconds) to give the system time to recover. Capping retries is another safegaurd that protects additional damage caused by further retries to a broken system.
* thundering herd problem: when a server is down, we anticipate that once its back up the retries will come in from the client all at once. Therefore assigning randomness or jitter to client requests allows breathing time in between so the server can recover instead of all the retries coming at once.

July 28:
- a workflow beats an agent when a pre-identified set of tasks will always be applicable
- the augmented llm is basically the building blocks of all llm agents/workflows  - retrieval (pull context), tools(which functions), memory(carry information across steps).
- The principle: anywhere untrusted data enters your system — API responses, user input, and especially LLM output - validate at the door. In Python you'd use Pydantic: parse, then assert the object matches the taste schema, and flag/reject if not. Even when it "looks right," validation is the difference between "the model was wrong and I caught it instantly" and "the model was wrong and I found out when the portal broke."

August 16:
- Why continuous axes instead of categorical buckets? What does "0.8 edgy" capture that a tag "edgy" can't? axes represent a spectrum that can't be clearly defined in pre-existing values. 0.8 edgy can capture a relative level that a static tag can't.
- ANN Index: a universal specialized data structure used in vector databases and machine learning to find approximate closest search results by trading accuracy for lower latency and more speed.
- B-tree index: an index tree used by relational databases to store sorted date. Think indexing fields in salesforce for search.
- online/offline retrieval vs ranking: each process has both online and offline components; offline processes can be used to create an ANN index that can be reused in online processes and similar.

August 17:
- some takeaways from fine tuning your AI model: evaluations are key and any evaluation correction is a dataset. 
- looking at your data is the single most important aspect of bettering your model so remove all friction and make it super easy to look at your data, creating whatever kind of view or report or interface that'll help you do that.

August 18:
- 
