# Day 14 — LangGraph: conditional routing

- [ ] Done

**After this you should know:** how a graph *branches* — sending confident results one way
and uncertain ones to human review.

## 📖 Read (~15 min)
[LangGraph — Conditional edges](https://langchain-ai.github.io/langgraph/concepts/low_level/#conditional-edges)
(the branching part of the low-level concepts). Get: routing on state.

## 🛠️ Build (~20 min)
Add a conditional edge after `self_check`: high confidence → save to DB; low confidence →
flag `needs_review`. The human-in-the-loop fork, in the graph.

## 🤖 Claude-craft (~10 min)
Chain a skill + subagent on one real task in your repo.

## 🔗 Network
—

## ✍️ Journal
One line: where did you set the confidence threshold, and what did that trade off?
