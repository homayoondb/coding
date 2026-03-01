# Anthropic 55-Minute Coding Study Plan (CV-Tailored)

Interview target: Friday, March 6, 2026  
Available prep: Sunday-Thursday, with 2-3 work-heavy days

## What this plan optimizes for
This plan is tuned to your submitted Anthropic profile (FDE/SA style):
- production agent systems
- reliability + safety guardrails
- enterprise deployment patterns
- Python-first applied problem solving

That means we prioritize interview prompts that look like real deployment engineering, not only generic algorithm puzzles.

## Most likely interviewer pick (based on your CV)

1. Reliability triage loop with retries/cache/structured output
2. Tool-use loop correctness with robust error handling
3. Safety/guardrail handling of untrusted tool output
4. Applied data cleaning + metric extraction (SQL + Python)
5. Practical trace/event reconstruction from runtime samples

This maps to your strongest resume signals: agent deployment, guardrails/evals, production reliability, and customer-facing technical implementation.

## CV-Matched Resource Ranking (Most Important First)

1. `notebooks/03_mock.ipynb`
2. `notebooks/01_mock.ipynb`
3. `notebooks/02_mock.ipynb`
4. `notebooks/06_mock.ipynb`
5. `notebooks/04_mock.ipynb`
6. `https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/implement-tool-use`
7. `https://docs.anthropic.com/en/api/handling-stop-reasons`
8. `building_effective_agents_course/02_Developing Claude Agents with Tool Integration in Python/`
9. `notebooks/05_mock.ipynb`
10. `notebooks/08_mock.ipynb` (exact LC636)
11. `notebooks/09_mock.ipynb` (exact LC609)
12. `notebooks/07_mock.ipynb`
13. `building_effective_agents_course/01_Exploring Workflows with Claude in Python/` (selective)
14. `https://support.codesignal.com/hc/en-us/articles/19116922232983-What-are-the-Industry-Coding-Assessment-ICA-rules`
15. `https://support.codesignal.com/hc/en-us/articles/21025134150423-How-do-I-practice-coding-questions-on-CodeSignal`
16. `building_effective_agents_course/03_Mastering Agentic Patterns with Claude in Python/` and `building_effective_agents_course/04_Parallelizing Claude Agentic Systems in Python/` (only if extra time)

## Why this ranking changed

- Your prior rank weighted interview-general signal heavily.
- This revised rank weights **CV-match likelihood** first.
- For your background, a practical reliability/agent/safety problem is more likely than a pure tokenizer-style prompt.

## Exact mock set now available

- `01_mock.ipynb` + `01_sol.ipynb` + `01_sol.md`
- `02_mock.ipynb` + `02_sol.ipynb` + `02_sol.md`
- `03_mock.ipynb` + `03_sol.ipynb` + `03_sol.md`
- `04_mock.ipynb` + `04_sol.ipynb` + `04_sol.md`
- `05_mock.ipynb` + `05_sol.ipynb` + `05_sol.md`
- `06_mock.ipynb` + `06_sol.ipynb` + `06_sol.md`
- `07_mock.ipynb` + `07_sol.ipynb` + `07_sol.md`
- `08_mock.ipynb` + `08_sol.ipynb` + `08_sol.md`
- `09_mock.ipynb` + `09_sol.ipynb` + `09_sol.md`

## Day-by-Day Execution Plan

### Day 1 (High-value core)
1. Timed run: `03_mock` (55 min)
2. Debrief: compare with `03_sol.ipynb`
3. Study guide: `03_sol.md`
4. 30-min rewrite from blank (no copy/paste)

### Day 2 (Tool loop + safety)
1. Timed run: `01_mock`
2. Debrief with `01_sol.ipynb` and `01_sol.md`
3. Timed run: `02_mock`
4. Debrief with `02_sol.ipynb` and `02_sol.md`

### Day 3 (Applied practical coding)
1. Timed run: `06_mock`
2. Timed run: `04_mock`
3. 20-minute verbal defense rehearsal for both

### Day 4 (Role breadth + backup patterns)
1. Read docs: tool use implementation + stop reasons
2. Do selected lessons from course module 02
3. One timed run: `05_mock` or `08_mock` (choose based on weak area)

### Day 5 (Final rehearsal)
1. One full timed run from top-5 list, no interruptions
2. 45-minute speaking rehearsal (trade-offs, failure modes, alternatives)
3. Light review of mistakes only (no new topics)

## If time collapses

### Only 1 focused day remains
1. `03_mock`
2. `01_mock`
3. Docs: tool-use + stop-reasons
4. 30-minute communication rehearsal

### Only 2 focused days remain
1. Day 1: `03_mock` + `01_mock`
2. Day 2: `02_mock` + `06_mock`

### Only 3 focused days remain
1. Day 1: `03_mock` + `01_mock`
2. Day 2: `02_mock` + `06_mock`
3. Day 3: `04_mock` + final rehearsal

## Session format (for every timed mock)

1. 8-10 min: parse prompt + tests + write invariants
2. 30-35 min: implement TODOs in dependency order
3. 10 min: edge-case pass + clear explanation pass

## Speaking script during coding

Use this structure out loud:

1. "I’ll lock the contract from tests first, then implement minimal correct behavior."
2. "I’m implementing in dependency order: validator/helper first, loop/orchestration last."
3. "Failure modes I’m explicitly handling are invalid input, runtime tool errors, and loop safety."
4. "Trade-off: I choose clarity and deterministic behavior over extra features in this timebox."
5. "If this were production, next step is observability and tighter schema validation."

## Self-questions to ask while solving

1. What is the exact output contract the tests enforce?
2. Which path fails first under malformed input?
3. Can this loop or workflow get stuck?
4. What is my deterministic tie-break behavior?
5. Am I handling both happy path and recovery path?

## Readiness gates (must all be true)

- [ ] Can complete `03_mock` under 55 minutes with clean explanation
- [ ] Can complete `01_mock` under 55 minutes and explain stop-reason handling
- [ ] Can complete `02_mock` under 55 minutes and explain trust boundary design
- [ ] Can explain one reliability trade-off and one safety trade-off without notes
- [ ] Can describe one concrete production hardening step for every top-5 mock

## LeetCode exact coverage status

- `1236 Web Crawler` -> covered by `05_mock`
- `1242 Web Crawler Multithreaded` -> covered by `05_mock`
- `636 Exclusive Time of Functions` -> covered by `08_mock`
- `609 Find Duplicate File in System` -> covered by `09_mock`

## Notes

- Keep using `NN_sol.ipynb` for reference implementation and `NN_sol.md` for guided walkthrough.
- If recruiter confirms assistant usage rules, align your practice mode to those constraints.
