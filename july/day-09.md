# Day 09 — Error handling: malformed args, retries, giving up

- [ ] Done

**After this you should know:** real agents spend most of their code on failure — bad args, retries, and knowing when to stop.

## Do (~1 hr)
Make a tool throw or receive bad args. Handle it: validate, retry once, then give up gracefully. Add a max-turns guard so the loop can't run forever.
Analogy: defensive Apex + a retry policy — but you own the policy now.

## 3 flashcard ideas
- Three failure modes an agent must handle.
- Why a max-turns guard?
- Retry vs. give up — how do you decide?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
