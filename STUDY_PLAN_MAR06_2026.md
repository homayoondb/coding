# Anthropic 55-Minute Technical Interview Study Plan (Single Source)

Interview target: Friday, March 6, 2026  
Plan owner file: `STUDY_PLAN_MAR06_2026.md` (keep this as the only plan markdown)

## Current status
Completed:
1. CodeSignal Course 2: `02_Developing Claude Agents with Tool Integration in Python`
2. Claude tool-use doc: `tool_use_with_claude.md`
3. Stop-reasons retry guidance: `handling-stop-reasons#3-implement-retry-logic-for-pause-turn`

This is strong coverage of the core requirement in the recruiter email.

## What the interview is most likely testing
1. Correct `tool_use -> tool_result` loop handling in Messages API.
2. Prompting to make agent behavior reliable (not just code correctness).
3. Fast implementation under time pressure in Colab-style coding.
4. Clear communication of trade-offs while coding.

## What to do next after mocks 01/02/03 (exact lessons)
Priority is based on your specific 55-minute prompt+agent+tool-use round, not general OA prep.

### Tier A (do first)
1. `building_effective_agents_course/01_Exploring Workflows with Claude in Python/Building_Intelligent_Task_Routers_CodeSignal_Learn.md` (`5:12`)
2. `building_effective_agents_course/01_Exploring Workflows with Claude in Python/Breaking_Down_Tasks_with_Prompt_Chaining_CodeSignal_Learn.md` (`4:42`)
3. `building_effective_agents_course/04_Parallelizing Claude Agentic Systems in Python/Going_Async_with_Claude_Agents_CodeSignal_Learn.md` (`4:49`)
4. `building_effective_agents_course/04_Parallelizing Claude Agentic Systems in Python/Implementing_Async_Tool_Execution_CodeSignal_Learn.md` (`5:23`)

Why Tier A first:
1. Course 1 lessons above sharpen prompt + routing behavior that shows up in agentic coding rounds.
2. Course 4 first two lessons cover async/tool execution patterns that repeatedly appear in interview feedback (crawler/parallel follow-ups).

### Tier B (only if extra time remains)
1. `building_effective_agents_course/01_Exploring Workflows with Claude in Python/Speeding_Up_Workflows_with_Parallelization_CodeSignal_Learn.md` (`6:39`)
2. `building_effective_agents_course/04_Parallelizing Claude Agentic Systems in Python/Orchestrating_Parallel_Agent_Systems_CodeSignal_Learn.md` (`6:20`)
3. `building_effective_agents_course/03_Mastering Agentic Patterns with Claude in Python/Building_Agentic_Pipelines_CodeSignal_Learn.md` (`7:21`)

### Tier C (lowest ROI for your immediate 55-min prep)
1. Remaining Course 3 handoff/orchestrator lessons:
   - `.../03_Mastering Agentic Patterns with Claude in Python/Orchestrating_Agents_as_Tools_CodeSignal_Learn.md` (`5:48`)
   - `.../03_Mastering Agentic Patterns with Claude in Python/Delegating_Work_with_Handoffs_CodeSignal_Learn.md` (`7:02`)
2. Longer external curriculum modules (Coursera full modules) unless you have several extra hours.

## Should you do other courses mentioned in prior plans?
Short answer: **not before Tier A above**.

Recommended order now:
1. Timed mocks: `notebooks/01_mock.ipynb`, `notebooks/02_mock.ipynb`, `notebooks/03_mock.ipynb`
2. Tier A lessons (exact four lessons listed above)
3. Tier B lessons if time remains
4. Then external long-form courses

So yes, for your immediate interview readiness, the selective Course 1 + Course 4 lessons are better than jumping now to broader external courses.

## Time-boxed execution guide
### If you have ~1 hour after mock 01/02/03
1. Router lesson (`5:12`)
2. Prompt-chaining lesson (`4:42`)
3. Spend remaining time re-implementing one clean tool loop from memory

### If you have ~2 hours
1. All Tier A lessons (`~20 min` video total; `~60-90 min` with coding/review)
2. One strict 55-minute rerun of `02_mock`

### If you have ~3+ hours
1. Tier A complete
2. Tier B #1 (`Speeding_Up_Workflows_with_Parallelization`)
3. One additional timed rerun (`01_mock` or `03_mock`)

## Mocks to keep as primary drills
1. `notebooks/01_mock.ipynb` - hybrid stage-gated realistic flow
2. `notebooks/02_mock.ipynb` - prompt + tool-use loop correctness
3. `notebooks/03_mock.ipynb` - reliability controls (retry/cache/structured outputs)

## Source links and local references
1. Local doc: `tool_use_with_claude.md`
2. Official docs: `https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview`
3. Official docs: `https://platform.claude.com/docs/en/agents-and-tools/tool-use/implement-tool-use`
4. Official docs: `https://platform.claude.com/docs/en/build-with-claude/handling-stop-reasons`
5. Course path URL: `https://codesignal.com/learn/paths/building-effective-agents-claude-python`
6. Optional long-form external: `https://www.coursera.org/learn/building-with-the-claude-api`
7. Local mocks: `notebooks/01_mock.ipynb` to `notebooks/10_mock.ipynb`
