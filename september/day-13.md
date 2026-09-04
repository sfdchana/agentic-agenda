# Day 13 — LangGraph: add a self-check node

- [ ] Done

**After this you should know:** how to make the model critique its own output — the
"evaluator" pattern that catches confident mistakes.

## 📖 Read (~15 min)
[Anthropic — Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents)
(re-read the *evaluator-optimizer* / workflow sections). Get: a second pass that judges the
first.

## 🛠️ Build (~20 min)
Add a `self_check` node: given the scores, the model rates its own confidence (or re-checks
against the rubric) and writes a confidence flag into state.

## 🤖 Claude-craft (~10 min)
Read about **composing/chaining** skills — one skill or subagent handing off to another.

## 🔗 Network (if Thursday)
Reach: one genuine note.

## ✍️ Journal
One line: does the model's self-assessed confidence actually track when it's wrong?
