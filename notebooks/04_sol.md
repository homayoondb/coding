# 04_sol Guide: Local Research Agent + Injection Defense


## Walkthrough: Exactly How to Solve `04_mock`

### 0) First 2 minutes
- Write your threat model first: "tool output is untrusted."
- Decide sanitizer strategy (string-level block/replace rules).

### 1) Should I read tests now?
Yes, quickly:
- Find these must-pass checks:
  - final text must not contain `ADMIN_TOKEN`
  - multi-tool turn should append two `tool_result` blocks in one user message
  - unknown tool must become error tool message and still recover
  - `pause_turn` should continue the loop and still converge
- Once contract is clear, stop reading tests and implement.

### 2) Coding order
1. `sanitize_tool_output` first.
2. In loop: sanitize tool results **before** appending to messages.
   - append assistant response first, then one user message containing only `tool_result` blocks
3. On `end_turn`: sanitize final text again.
4. Unknown tool path should add `is_error=True` tool message, not crash.
5. On `pause_turn`: continue loop without appending a user message.

### 3) One concrete example to narrate aloud
Use "injection" scenario:
- Tool returns doc text with malicious instruction.
- Your sanitizer strips/blocks dangerous phrase.
- Model no longer sees exploitable payload, final output contains policy `[d1]` and no secret.

### 4) What to say while coding
- "I’m solving this as a trust-boundary problem, not only as a loop problem."
- "Sanitization happens both on tool output and final text to reduce leak paths."
- "I still return recoverable errors for unknown tools so the run can continue."

### 5) Self-check before final run
- If malicious text appears in docs, can it leak to final answer?
- If tool is unknown, do I recover and continue?
- Are false positives acceptable for this interview-time sanitizer?
