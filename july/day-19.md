# Day 19 — Deepen: clean service architecture (structure, not syntax)

- [ ] Done

**After this you should know:** how to structure a service so it's clean, deployable, and defensible — the architecture, not the keystrokes.

## 📖 Read first (~20 min)
*The Twelve-Factor App* (12factor.net) — read **Config**, **Processes**, and **Dependencies**. Get: config in the environment (not the code), **stateless processes**, explicit dependencies — the principles that make a service easy to deploy and scale.

## Do (~30 min) — direct it, don't grind it
Tidy the pipeline into clean modules and move any hardcoded config (keys, limits, search terms) into env/config. You're *directing* the cleanup and judging the boundaries — where does each responsibility belong? — not hand-writing idioms.

## Understand & defend (~10 min, journal it)
Why keep config in the environment instead of the code? What does "stateless process" mean, and why does it matter the moment you want to run two copies?

## 3 flashcard ideas
- why config-in-env, not config-in-code?
- what makes a process "stateless," and why care?
- separation of concerns — what does each module own?

_Journal: one boundary you moved, and why it belongs where you put it._
