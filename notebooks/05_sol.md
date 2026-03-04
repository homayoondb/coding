# 05_sol Guide: Stack Samples to Trace Events


## Walkthrough: Exactly How to Solve `05_mock`

### 0) First 2 minutes
- Write one rule: "difference between old/new stack = events".
- Keep generation and aggregation in separate functions.

### 1) Should I read tests now?
Yes, very quickly:
- Expected exact event order is given. That is your gold contract.
- Note this critical rule from expected output: end events are inner-first.
- Note invalid timestamp test.

### 2) Coding order
1. Input validation (`list`, fields, timestamp monotonicity).
2. Longest common prefix computation.
3. Emit end events for old suffix in reverse.
4. Emit start events for new suffix in forward order.
5. Optional close-final behavior (`last_ts + 1`).
6. `longest_running_function` on top of generated events.

### 3) One concrete example to narrate aloud
Transition:
- Old stack: `[main, load, parse]`
- New stack: `[main, render]`
- LCP is `[main]`
- Emit ends: `parse`, then `load` at ts=5
- Emit start: `render` at ts=5

### 4) What to say while coding
- "I am using prefix-diff; that makes transitions deterministic."
- "Reverse unwind preserves call-stack correctness."
- "I validate timestamp monotonicity early to fail fast on bad input."

### 5) Self-check before final run
- Do unchanged stacks emit no transitions?
- Does `close_final=True` end remaining frames?
- Is tie-breaking deterministic in longest-running function?
