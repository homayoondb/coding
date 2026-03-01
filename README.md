# ant-mock

Ranked, Colab-ready mock technical interviews for Anthropic-style prep.

Each `NN_mock.ipynb` is one full timed exam (55 minutes).  
Each `NN_sol.ipynb` contains the same exam with a full reference answer.  
Each `NN_sol.md` contains the step-by-step guide/walkthrough.

## Structure

- `notebooks/01_mock.ipynb` + `notebooks/01_sol.ipynb` + `notebooks/01_sol.md`
- `notebooks/02_mock.ipynb` + `notebooks/02_sol.ipynb` + `notebooks/02_sol.md`
- `notebooks/03_mock.ipynb` + `notebooks/03_sol.ipynb` + `notebooks/03_sol.md`
- `notebooks/04_mock.ipynb` + `notebooks/04_sol.ipynb` + `notebooks/04_sol.md`
- `notebooks/05_mock.ipynb` + `notebooks/05_sol.ipynb` + `notebooks/05_sol.md`
- `notebooks/06_mock.ipynb` + `notebooks/06_sol.ipynb` + `notebooks/06_sol.md`
- `notebooks/07_mock.ipynb` + `notebooks/07_sol.ipynb` + `notebooks/07_sol.md`
- `notebooks/08_mock.ipynb` + `notebooks/08_sol.ipynb` + `notebooks/08_sol.md`
- `notebooks/09_mock.ipynb` + `notebooks/09_sol.ipynb` + `notebooks/09_sol.md`

## Priority Ranking (Most Important First)

1. `01_mock` Tool-use loop correctness (closest to stated interview shape)
2. `02_mock` Tool safety + prompt-injection defense
3. `03_mock` Reliability loop (retry/cache/structured output)
4. `04_mock` Stack samples to trace events (practical Colab coding pattern)
5. `05_mock` Concurrent web crawler (frequently reported practical coding)
6. `06_mock` SQL + Python extraction/cleaning (applied data task)
7. `07_mock` Tokenizer longest-match (time-pressure correctness drill)
8. `08_mock` Exact LC 636 (Exclusive Time of Functions)
9. `09_mock` Exact LC 609 (Find Duplicate File in System)

## Exact LeetCode Coverage

- `1236. Web Crawler` -> `05_mock` (single-thread crawler)
- `1242. Web Crawler Multithreaded` -> `05_mock` (multi-thread crawler)
- `636. Exclusive Time of Functions` -> `08_mock` (exact API and semantics)
- `609. Find Duplicate File in System` -> `09_mock` (exact parse/grouping API)

## Recommended Study Modes

- **Core-only mode (high relevance):** `01_mock` -> `02_mock` -> `03_mock`
- **Complete mode:** run all 7 in ranked order
- **Exam simulation:** one notebook per day, strict 55-minute timer, no answer notebook until after tests

## How To Run

1. Open one `NN_mock.ipynb` in Colab.
2. Implement all TODO sections.
3. Run the final test cell.
4. Only then compare with `NN_sol.ipynb`.
5. Read `NN_sol.md` for the guided walkthrough.

## Colab Sync

After pushing to GitHub, open any notebook directly in Colab with:

`https://colab.research.google.com/github/<github-user>/<repo-name>/blob/<branch>/notebooks/<notebook-name>.ipynb`

Example:

`https://colab.research.google.com/github/<github-user>/ant-mock/blob/main/notebooks/01_mock.ipynb`

## Regenerate Notebooks

```bash
python scripts_generate_notebooks.py
```
