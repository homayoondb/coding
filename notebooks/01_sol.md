# 01_sol Guide: Tool-Using Support Agent


## Walkthrough: Exactly How to Solve `01_mock`

### 0) First 2 minutes (do this before coding)
- Read function TODOs and write this mini-plan in comments:
  1. `validate_tool_call`
  2. `execute_tool_call`
  3. `run_agent`
- Do **not** start `run_agent` first.

### 1) Should I read tests now?
Yes, but fast:
- Spend 3-4 minutes scanning test names and assertions only.
- Extract contracts from tests:
  - Single and multiple tool calls must work.
  - Missing args and runtime failures must return `is_error=True`.
  - `max_steps` must raise `RuntimeError("max_steps_exceeded")`.
- Then stop reading tests and implement TODOs.

### 2) Coding order with checkpoints
1. `validate_tool_call`:
   - check required keys (`id`, `name`, `input`)
   - check tool exists
   - check `input` is dict
   - check required args from function signature
2. `execute_tool_call`:
   - call validator first
   - on validation/runtime error return tool message with `is_error=True`
   - on success return tool message with JSON result payload
3. `run_agent`:
   - initialize `messages=[{"role":"user", ...}]`
   - loop up to `max_steps`
   - if `tool_use`: execute **all** tool calls, append messages, continue
   - if `end_turn`: return final text + messages
   - else: unsupported stop reason error

### 3) One concrete example to narrate aloud
Use test case #2 (multiple tools):
- Model returns `policy_check` and `create_refund` in one turn.
- You execute both and append two tool messages.
- Next model turn ends with "Refund submitted."
- Why this matters: proves your loop handles batched tool calls, not only one.

### 4) What to say while coding (verbatim-safe)
- "I scanned tests first to lock the contract, now I am implementing TODOs in dependency order."
- "I am enforcing a loop invariant: every `tool_use` turn appends tool outputs before next model call."
- "I am returning structured tool errors instead of crashing so the conversation can recover."
- "After baseline passes, I check failure paths: missing args, runtime exception, and max-step loop safety."

### 5) Self-check questions before final run
- Do I process all tool calls in a turn?
- Can unknown tools and missing args fail safely?
- Is `max_steps` guaranteed to stop infinite loops?
- Are error messages JSON and debuggable?
