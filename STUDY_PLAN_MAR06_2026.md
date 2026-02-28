# Anthropic Coding Interview Study Plan

Interview target date: Friday, March 6, 2026  
Prep window: Sunday to Thursday, with 2-3 work-heavy days

## What "implement the plan" means
For this task, "implement" means following the study schedule yourself. There is no code feature to build.

## Priority Ranking (Most Important First)

1. `notebooks/01_mock.ipynb`
2. `https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/implement-tool-use` and `https://docs.anthropic.com/en/api/handling-stop-reasons`
3. `notebooks/02_mock.ipynb`
4. `notebooks/03_mock.ipynb`
5. `building_effective_agents_course/02_Developing Claude Agents with Tool Integration in Python/`
6. `notebooks/04_mock.ipynb`
7. `https://support.codesignal.com/hc/en-us/articles/19116922232983-What-are-the-Industry-Coding-Assessment-ICA-rules` and `https://support.codesignal.com/hc/en-us/articles/21025134150423-How-do-I-practice-coding-questions-on-CodeSignal`
8. `building_effective_agents_course/01_Exploring Workflows with Claude in Python/` (selective)
9. `notebooks/06_mock.ipynb`
10. `notebooks/05_mock.ipynb`
11. `notebooks/07_mock.ipynb`
12. `building_effective_agents_course/03_Mastering Agentic Patterns with Claude in Python/` and `building_effective_agents_course/04_Parallelizing Claude Agentic Systems in Python/` (only if extra time)

## Why this order

- Your recruiter-described round is a 55-minute practical coding interview around tool use + agents.
- `01-03_mock` are the closest simulation of that shape and include follow-up questions.
- `04_mock` is high value because stack-sample/event-style practical prompts are repeatedly reported.
- Course module 02 is the most directly relevant part of the downloaded course.
- Multi-agent orchestration and async modules are useful but lower ROI for a single 55-minute round.

## Time-Boxed Tracks

### If you only have 1 focused day

1. Run `01_mock` (strict 55-minute timer)
2. Review `sol01` and rewrite key functions from memory
3. Read tool-use + stop-reasons docs
4. Run `02_mock` (strict 55-minute timer)
5. Do 30-minute verbal drill on trade-offs and failure modes

### If you have 2 focused days

1. Everything from 1-day track
2. Run `03_mock`
3. Do only module 02 lessons from `building_effective_agents_course`
4. Re-implement a minimal `run_agent` loop from blank cell in <=35 minutes

### If you have 3 focused days

1. Everything from 2-day track
2. Run `04_mock`
3. Read CodeSignal ICA rules and do one practice session
4. Do one interview-style follow-up Q&A rehearsal

### If you can use the full 5 days

1. Everything from 3-day track
2. Run `06_mock`, then `05_mock`, then `07_mock`
3. Skim module 01 lessons (routing/chaining/parallel basics)
4. Only if time remains, skim modules 03-04

## Daily Session Template

- Deep day: 1 timed mock + 60 minutes debrief + 30 minutes verbal defense
- Light day: 45-75 minutes docs/course + 30 minutes coding warm-up
- Final day before interview: 1 timed mock + follow-up Q&A rehearsal

## Interview Behaviors to Practice (Not Just Passing Tests)

1. State assumptions early
2. Build minimal correct solution first
3. Handle invalid inputs and runtime failures explicitly
4. Explain trade-offs between speed, robustness, and clarity
5. Call out what you would improve in production

## Verbal Script During Coding

1. "I will optimize for correctness first, then reliability."
2. "I am implementing minimal working behavior, then extending safely."
3. "These are the failure modes I am covering: invalid args, tool errors, loop limits."
4. "Trade-off: I choose X over Y because of time and risk constraints."
5. "I will validate with targeted tests before refactoring."

## Readiness Checklist

- [ ] Can implement tool loop (`tool_use` -> execute -> `tool_result`) from scratch in <=35 minutes
- [ ] Can explain at least two stop reasons and how your loop handles them
- [ ] Can pass `01_mock`, `02_mock`, and `03_mock` under 55-minute timebox
- [ ] Can answer at least 3 follow-up questions per mock without notes
- [ ] Can clearly explain one trade-off and one failure mode per solution

## Key Links

- Anthropic careers: https://www.anthropic.com/careers
- Candidate AI guidance: https://www.anthropic.com/candidate-ai-guidance
- Tool use overview: https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview
- Implement tool use: https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/implement-tool-use
- Stop reasons: https://docs.anthropic.com/en/api/handling-stop-reasons
- CodeSignal ICA rules: https://support.codesignal.com/hc/en-us/articles/19116922232983-What-are-the-Industry-Coding-Assessment-ICA-rules
- CodeSignal practice: https://support.codesignal.com/hc/en-us/articles/21025134150423-How-do-I-practice-coding-questions-on-CodeSignal
- Course page: https://codesignal.com/learn/paths/building-effective-agents-claude-python

## Notes on AI Assistance During Interview

Your recruiter said an assistant may be available. Confirm exact allowed usage before interview day. Use any assistant only for syntax/boilerplate and keep architecture, logic, and trade-off reasoning fully your own.
