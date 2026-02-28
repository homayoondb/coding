# ant-mock

Ranked, Colab-ready mock technical interviews for Anthropic-style prep.

Each `NN_mock.ipynb` is one full timed exam (55 minutes).  
Each `solNN.ipynb` contains the same exam with a full reference answer.

## Structure

- `notebooks/01_mock.ipynb` + `notebooks/sol01.ipynb`
- `notebooks/02_mock.ipynb` + `notebooks/sol02.ipynb`
- `notebooks/03_mock.ipynb` + `notebooks/sol03.ipynb`
- `notebooks/04_mock.ipynb` + `notebooks/sol04.ipynb`
- `notebooks/05_mock.ipynb` + `notebooks/sol05.ipynb`
- `notebooks/06_mock.ipynb` + `notebooks/sol06.ipynb`
- `notebooks/07_mock.ipynb` + `notebooks/sol07.ipynb`

## Priority Ranking (Most Important First)

1. `01_mock` Tool-use loop correctness (closest to stated interview shape)
2. `02_mock` Tool safety + prompt-injection defense
3. `03_mock` Reliability loop (retry/cache/structured output)
4. `04_mock` Stack samples to trace events (practical Colab coding pattern)
5. `05_mock` Concurrent web crawler (frequently reported practical coding)
6. `06_mock` SQL + Python extraction/cleaning (applied data task)
7. `07_mock` Tokenizer longest-match (time-pressure correctness drill)

## Recommended Study Modes

- **Core-only mode (high relevance):** `01_mock` -> `02_mock` -> `03_mock`
- **Complete mode:** run all 7 in ranked order
- **Exam simulation:** one notebook per day, strict 55-minute timer, no answer notebook until after tests

## How To Run

1. Open one `NN_mock.ipynb` in Colab.
2. Implement all TODO sections.
3. Run the final test cell.
4. Only then compare with `solNN.ipynb`.

## Colab Sync

After pushing to GitHub, open any notebook directly in Colab with:

`https://colab.research.google.com/github/<github-user>/<repo-name>/blob/<branch>/notebooks/<notebook-name>.ipynb`

Example:

`https://colab.research.google.com/github/<github-user>/ant-mock/blob/main/notebooks/01_mock.ipynb`

## Regenerate Notebooks

```bash
python scripts_generate_notebooks.py
```
