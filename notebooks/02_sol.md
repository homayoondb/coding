# 02_sol Guide: Tool-Using Support Agent


## Walkthrough: Exactly How to Solve `02_mock`

### 0) First 2 minutes (do this before coding)
- Read function TODOs and write this mini-plan in comments:
  1. `build_agent_system_prompt`
  2. `build_tool_schemas`
  3. `validate_tool_call`
  4. `execute_tool_call`
  5. `run_agent`
- Do **not** start `run_agent` first.

### 1) Should I read tests now?
Yes, but fast:
- Spend 3-4 minutes scanning test names and assertions only.
- Extract contracts from tests:
  - Prompt must enforce tool-grounding and clarifying behavior.
  - Tool schemas must be present and passed on model calls.
  - Single and multiple tool calls must work.
  - Missing args and runtime failures must return `is_error=True`.
  - Claude message ordering must hold: assistant `tool_use` -> next user `tool_result`.
  - `pause_turn` should continue the loop without crashing.
  - `max_steps` must raise `RuntimeError("max_steps_exceeded")`.
- Then stop reading tests and implement TODOs.

### 2) Coding order with checkpoints
1. `build_tool_schemas`:
   - produce minimal Claude-compatible tool definitions
   - include `required` arguments from function signatures
2. `validate_tool_call`:
   - check required keys (`id`, `name`, `input`)
   - check tool exists
   - check `input` is dict
   - check required args from function signature
3. `build_agent_system_prompt`:
   - instruct model to verify facts via tools
   - forbid fabricated tool outputs
   - require concise clarification when policy inputs are missing
4. `execute_tool_call`:
   - call validator first
   - on validation/runtime error return tool message with `is_error=True`
   - on success return tool message with JSON result payload
5. `run_agent`:
   - initialize Claude-style `messages=[{"role":"user","content":[{"type":"text",...}]}]`
   - create `system_prompt` and `tools` once and pass both to each model call
   - loop up to `max_steps`
   - append assistant content every turn
   - if `tool_use`: execute **all** tool calls and append one user message with only `tool_result` blocks
   - if `pause_turn`: continue loop with no extra user message
   - if `end_turn`: join assistant text blocks and return final text + messages
   - else: unsupported stop reason error

### 3) One concrete example to narrate aloud
Use test case #2 (multiple tools):
- Model returns `policy_check` and `create_refund` in one turn.
- You execute both and append one user message containing two `tool_result` blocks.
- Next model turn ends with "Refund submitted."
- Why this matters: proves your loop handles batched tool calls, not only one.

### 4) What to say while coding (verbatim-safe)
- "I scanned tests first to lock the contract, now I am implementing TODOs in dependency order."
- "I am enforcing Claude ordering: assistant tool_use is immediately followed by user tool_result blocks."
- "I am returning structured tool errors instead of crashing so the conversation can recover."
- "After baseline passes, I check failure paths: missing args, runtime exception, and max-step loop safety."

### 5) Self-check questions before final run
- Do I process all tool calls in a turn and return tool results in the same order?
- Can unknown tools and missing args fail safely?
- Is `max_steps` guaranteed to stop infinite loops?
- Are error messages JSON and debuggable?
