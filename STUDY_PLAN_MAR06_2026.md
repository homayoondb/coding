# Anthropic 55-Minute Technical Interview Study Plan (Updated)

Interview target: Friday, March 6, 2026  
Current status: you are already finishing `tool_use_with_claude.md`

## Calibration to recruiter email
The round tests:
1. Writing code with LLMs as a building block.
2. Prompting to create an agent.
3. Tool Use and Agents in Anthropic API handling.
4. Practical coding in Colab (Python) or CodeSignal (TypeScript), open-book, starter code provided.

So the plan below prioritizes:
1. Tool-use execution loop correctness.
2. Prompt + schema quality for reliable tool calling.
3. Reliability/safety hardening under time pressure.
4. Practical fallback coding patterns seen in reports.

## Official vs realistic time estimates
1. CodeSignal Path: Building Effective Agents with Claude in Python  
Path URL: `https://codesignal.com/learn/paths/building-effective-agents-claude-python`  
Official: `8h`  
Realistic for interview prep depth: `11-14h`
2. CodeSignal Course 1: Exploring Workflows with Claude in Python  
URL: `https://codesignal.com/learn/courses/exploring-workflows-with-claude`  
Official: `2h`  
Realistic: `2.5-3.5h`
3. CodeSignal Course 2: Developing Claude Agents with Tool Integration in Python  
URL: `https://codesignal.com/learn/courses/developing-claude-agents-with-tool-integration`  
Official: `2h`  
Realistic: `3-4.5h`  
Note: highest-value single course module for your interview shape.
4. CodeSignal Course 3: Mastering Agentic Patterns with Claude in Python  
URL: `https://codesignal.com/learn/courses/mastering-agentic-patterns-with-claude`  
Official: `2h`  
Realistic: `2.5-3.5h`
5. CodeSignal Course 4: Parallelizing Claude Agentic Systems in Python  
URL: `https://codesignal.com/learn/courses/parallelizing-claude-agentic-systems-in-python`  
Official: `2h`  
Realistic: `2.5-3.5h`
6. Anthropic/Coursera: Building with the Claude API  
URL: `https://www.coursera.org/learn/building-with-the-claude-api`  
Module labels total: `13h`  
Realistic: `12-16h`
7. One mock package (`NN_mock` + `NN_sol` + `NN_sol.md`)  
Local path pattern: `notebooks/NN_*`  
Timed run only: `55m`  
Run + debrief + compare: `1.5-2h`

## Ranked prep backlog (courses + mock packages, most important first)
1. `notebooks/01_mock.ipynb` package (`1.5-2h`) - best hybrid of 55-min tool-use loop + progressive stage constraints
2. `building_effective_agents_course/02_Developing Claude Agents with Tool Integration in Python/` (`3-4.5h`)
3. `notebooks/02_mock.ipynb` package (`1.5-2h`)
4. `notebooks/03_mock.ipynb` package (`1.5-2h`)
5. `notebooks/04_mock.ipynb` package (`1.5-2h`)
6. Anthropic/Coursera Module 3: Claude features + tool use (`4-6h`)  
Course URL: `https://www.coursera.org/learn/building-with-the-claude-api`
7. `building_effective_agents_course/01_Exploring Workflows with Claude in Python/` (`2.5-3.5h`)
8. Anthropic/Coursera Module 7: Agentic workflows (`1.5-2h`)  
Course URL: `https://www.coursera.org/learn/building-with-the-claude-api`
9. Anthropic/Coursera Module 2: Prompt engineering + evaluation (`2.5-3.5h`)  
Course URL: `https://www.coursera.org/learn/building-with-the-claude-api`
10. `building_effective_agents_course/03_Mastering Agentic Patterns with Claude in Python/` (`2.5-3.5h`)
11. `building_effective_agents_course/04_Parallelizing Claude Agentic Systems in Python/` (`2.5-3.5h`)
12. `notebooks/05_mock.ipynb` package (`1.5-2h`)
13. `notebooks/06_mock.ipynb` package (`1.5-2h`)
14. Anthropic/Coursera Module 1: Claude API basics (`2-3h`)  
Course URL: `https://www.coursera.org/learn/building-with-the-claude-api`
15. Anthropic/Coursera Module 4: MCP (`2.5-3.5h`)  
Course URL: `https://www.coursera.org/learn/building-with-the-claude-api`

## Priority ladder by available remaining time
### If you suddenly only have 1 day
1. `01_mock` package.
2. `02_mock` package if time remains.
3. CodeSignal Course 2 only if there is still time.

### If you have 2 days
1. `01_mock` package.
2. `02_mock` package.
3. `03_mock` package.
4. CodeSignal Course 2 core lessons.

### If you have 3 days
1. `01_mock` package.
2. `02_mock` package.
3. `03_mock` package.
4. `04_mock` package.
5. CodeSignal Course 2 full.

### If you have 4+ days
1. Finish the 4 core mocks above.
2. Add Course 3 and Course 4 (selective).
3. Add one fallback practical mock (`05` or `06`).

## Suggested schedule for your week (with work-heavy days)
### High-focus day block (`~3.5-4.5h`)
1. `90-120m`: Course 2 lessons + exercises.
2. `55m`: one timed mock run.
3. `45-60m`: debrief against solution/guide and note trade-off talking points.

### Work-heavy day block (`~1.5-2h`)
1. `45-60m`: one Course 2 or Course 1 lesson block.
2. `55m`: one strict timed mock (or half-mock focused on tool loop only).

## Mock-specific target outcomes (core 01/02/03)
1. `01`: stage-gated progressive contract under a banking business-logic scenario plus tool-use sequencing.
2. `02`: prompt + tool schema + clean `tool_use -> tool_result` loop, including `pause_turn`.
3. `03`: reliability controls under constraints (validation, retry, cache, structured output, max-steps).
4. `04`: safety guardrails on untrusted tool output while preserving loop correctness.

## Readiness gates
- [ ] Can implement a tool loop from scratch in ~35 minutes.
- [ ] Can explain `tool_use`, `tool_result`, `end_turn`, and `pause_turn` handling clearly.
- [ ] Can discuss one reliability trade-off and one safety trade-off in under 60 seconds each.
- [ ] Can finish at least one core mock in strict 55-minute conditions.

## Source links and local resources
1. Local: `tool_use_with_claude.md`
2. Official docs: `https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview`
3. Official docs: `https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use`
4. Official docs: `https://platform.claude.com/docs/en/build-with-claude/handling-stop-reasons`
5. Local course: `building_effective_agents_course/`
6. Local mock set: `notebooks/01_mock.ipynb` to `notebooks/10_mock.ipynb`
7. External course path: `https://codesignal.com/learn/paths/building-effective-agents-claude-python`
8. External course: `https://www.coursera.org/learn/building-with-the-claude-api`
