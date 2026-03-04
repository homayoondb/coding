## Walkthrough: Exactly How to Solve `01_mock`

### 0) First 3 minutes: lock stage contracts
- Read level checks first, not function bodies.
- Capture stage contracts quickly:
  - L1: schema + single tool call.
  - L2: multiple tool calls in one turn and strict message ordering.
  - L3: business-logic mutation + recoverable tool errors.
  - L4: `pause_turn`, one retry on runtime fault, max-step guard.

### 1) Implementation order
1. `build_tool_schemas`
2. `build_system_prompt`
3. `_validate_tool_call` (inside solution)
4. `execute_tool_call`
5. `run_agent`

Do not start with the full loop first.

### 2) What to say out loud while coding
- "I’m solving this as a staged contract: pass each level before adding complexity."
- "I’m enforcing deterministic behavior with stable cache keys and bounded retries."
- "I’m preserving strict sequencing: assistant tool_use, then one user tool_result message."
- "I’m treating unknown tools and bad args as recoverable errors, not crashes."

### 3) Fast mental model per level
- Level 1: prove baseline loop and schema wiring.
- Level 2: prove batched tool execution in one turn.
- Level 3: prove side effects and resilience together.
- Level 4: prove control-flow stability under pause + loop pressure.

### 4) Common failure points
- Returning one user message per tool call instead of one message for the whole turn.
- Forgetting to pass system prompt/tools on each model call.
- Retrying all errors instead of retrying only transient runtime faults.
- Missing max-step guard, causing runaway loops.

### 5) Interview-time strategy
- Build the minimum passing loop first.
- Immediately run Level 1.
- Add one feature per level and re-run stage sequence.
- Keep final 5 minutes to explain trade-offs and safety boundaries.
