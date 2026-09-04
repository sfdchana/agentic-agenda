# Day 8 — LangChain: port your classifier to a chain

- [ ] Done

**After this you should know:** how your working Node classifier becomes a clean Python
chain — image + prompt → validated axis scores.

## 📖 Read (~15 min)
[Pydantic — Models](https://docs.pydantic.dev/latest/concepts/models/). Get: how Pydantic
parses and validates — the backbone of trustworthy model output.

## 🛠️ Build (~20 min)
Port [classify-items.js](../../houseofsof-api/houseofsof-api/src/pipeline/classify-items.js)
logic to a LangChain chain: send the (bigger) image + your axis rubric, get back the
Pydantic-validated scores. Run it on one item.

## 🤖 Claude-craft (~10 min)
Read [Subagents](https://docs.claude.com/en/docs/claude-code/sub-agents); run one on a
throwaway question.

## 🔗 Network
—

## ✍️ Journal
One line: what was easier in the chain than in raw Node — and what was harder?
