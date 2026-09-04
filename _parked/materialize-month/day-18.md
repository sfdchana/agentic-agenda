# Day 18 — Clean: remove the dead tension model

- [ ] Done

**After this you should know:** how to safely delete a superseded subsystem — leave the
codebase better than you found it.

## 📖 Read (~15 min)
[Refactoring.Guru — What is refactoring](https://refactoring.guru/refactoring). Get: small,
safe, behavior-preserving changes; delete dead code with confidence.

## 🛠️ Build (~20 min)
Remove the tension model now that sliders won: unused tables/routes/tagger paths and the
`tension`/`elements`/`trends` plumbing you no longer touch. Verify nothing breaks.

## 🤖 Claude-craft (~10 min)
Use a **subagent** to find *every* reference to tension across the repo before you cut —
let Claude map the blast radius.

## 🔗 Network
—

## ✍️ Journal
One line: what did removing it clarify about what the product actually is?
