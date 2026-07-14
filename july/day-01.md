# Day 01 — The agent mental model

- [x] Done

**After this you should know:** what an "agent" actually is (model + tools + loop) and when a plain workflow beats an agent.

## Do (~1 hr)
Read Anthropic, "Building Effective Agents" — https://www.anthropic.com/research/building-effective-agents
As you read, translate each pattern into Salesforce terms you already know: prompt chaining ≈ chained Apex service methods in sequence; routing ≈ a `switch`/`case`; orchestrator-workers ≈ Queueable/Batch Apex fan-out.

Write 3 sentences at the bottom of this file: "An agent is ___. I'd use a workflow instead when ___. The loop ends when ___."
An agent is an autonomous system that determines what steps and output to return independently. 
I'd use a workflow instead when there the input and consequent steps are somewhat defined or known and the best steps for the llm can be optimized based on needs. 
The loop ends when the response is returned and there are no more tools to be processed.

## 3 flashcard ideas
- What distinguishes an agent from a workflow?
- The three parts of an agent.
- When is an agent the *wrong* choice?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
