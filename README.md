# ant-mock

Three Colab-ready mock technical interviews focused on tool use + agents.

## Structure

- `notebooks/mock1_real_world_questions.ipynb`
- `notebooks/mock1_real_world_answers.ipynb`
- `notebooks/mock2_research_injection_questions.ipynb`
- `notebooks/mock2_research_injection_answers.ipynb`
- `notebooks/mock3_reliability_progressive_questions.ipynb`
- `notebooks/mock3_reliability_progressive_answers.ipynb`

## Recommended flow

1. Open a `*_questions.ipynb` notebook in Colab.
2. Implement TODO sections under a 55-minute timer.
3. Run the grading test cell at the end.
4. Compare against the matching `*_answers.ipynb` notebook.

## Colab sync

After pushing to GitHub, open any notebook directly in Colab with:

`https://colab.research.google.com/github/<github-user>/<repo-name>/blob/<branch>/notebooks/<notebook-name>.ipynb`

Example:

`https://colab.research.google.com/github/<github-user>/ant-mock/blob/main/notebooks/mock1_real_world_questions.ipynb`

## Mock design goals

- Mock 1 is closest to the real interview shape: end-to-end tool-use loop.
- Mock 2 focuses on tool safety and prompt-injection defense.
- Mock 3 focuses on reliability patterns: cache, retry, and structured output.
