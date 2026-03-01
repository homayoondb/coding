# 03_sol Guide: Reliability-Focused Incident Triage Agent


## Walkthrough: Exactly How to Solve `03_mock`

### 0) First 3 minutes
- This is reliability-first, not algorithm-first.
- Write these goals in comments: cache hit, one retry, strict final JSON parse.

### 1) Should I read tests now?
Yes, because tests define reliability policy:
- `cache_hits == 1`
- `LOOKUP_ATTEMPTS["payments"] == 2` (one retry happened)
- final output must include `summary/action/confidence`
- max step protection must raise error

### 2) Coding order
1. `parse_final_output` (small, deterministic).
2. `execute_tool_call` with:
   - validation
   - cache read/write
   - one retry around transient tool failure
3. `run_agent`:
   - maintain `stats`
   - increment `tool_calls`
   - increment `cache_hits` from tool message metadata

### 3) One concrete example to narrate aloud
Use retry scenario:
- First `lookup_runbook(payments)` throws transient timeout.
- Retry once, second attempt succeeds.
- Final action becomes `restart_payments_workers`.
- You can explain this as "bounded retry for transient faults."

### 4) What to say while coding
- "I’m defining explicit reliability policy first, then implementing to that contract."
- "Cache key is tool-name plus normalized input to reduce duplicate work."
- "Retry is bounded to one attempt to avoid runaway latency."
- "I validate final output schema to prevent silent bad responses."

### 5) Self-check before final run
- Can cached calls skip tool execution?
- Is retry only for runtime failures, not validation failures?
- Do stats reflect actual behavior?
