# Day 07 — Build the loop: agent = model + tools + while loop

- [ ] Done

**After this you should know:** the agent loop is just a `while` loop that runs tool calls until the model stops asking.

## Do (~1 hr)
Wrap Day 06 in a loop: call model → if a tool is requested, run it, append the result, repeat → else return. ~40 lines.
Analogy: like a Batch Apex execute loop, except *you* own the exit condition.

## 3 flashcard ideas
- What is the loop's continue-vs-stop condition?
- How do tool results feed back into the model?
- When does the loop end?

_Last 2 min: a line in ../journal/ (log / question / idea). Prefix a-ha lines with `!`._
