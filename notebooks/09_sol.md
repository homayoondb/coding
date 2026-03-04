# 09_sol Guide: LeetCode 636 Exclusive Time of Functions


## Walkthrough: Exactly How to Solve `09_mock` (LC 636)

### 0) First 2 minutes
- Write these invariants first:
  - stack top = currently running function
  - `prev_time` = first unaccounted timestamp
  - end event is inclusive

### 1) Should I read tests now?
Yes:
- Confirm canonical sample expected `[3,4]`.
- Confirm nested case and single-tick case.
- Confirm invalid unmatched end should raise error.

### 2) Coding order
1. Parse log triplets (`fid:action:ts`) and validate.
2. Start event: credit current top function with `ts - prev_time`.
3. Push new function and set `prev_time = ts`.
4. End event: credit top function with `ts - prev_time + 1`.
5. Pop and set `prev_time = ts + 1`.

### 3) One concrete example to narrate aloud
For `0:start:0, 1:start:2, 1:end:5, 0:end:6`:
- function 0 gets `2` units before function 1 starts
- function 1 gets `4` units (`2..5` inclusive)
- function 0 gets final `1` unit (`6..6`)
- total `[3,4]`

### 4) What to say while coding
- "I am using a stack because nesting depth changes over time."
- "I track `prev_time` so every tick is counted exactly once."
- "Inclusive end means I add `+1` and then move `prev_time` to `ts+1`."

### 5) Self-check before final run
- Do I double-count any time interval?
- Did I handle inclusive end correctly?
- Do malformed sequences fail explicitly?
