# 08_sol Guide: Tokenizer Greedy Longest Match


## Walkthrough: Exactly How to Solve `08_mock`

### 0) First 2 minutes
- Write the greedy rule in a comment:
  - longest match at index
  - fallback to `UNK` and advance one char
- Confirm `UNK` is mandatory.

### 1) Should I read tests now?
Yes:
- `apple -> [2]` proves longest token priority.
- `bbb` with compression gives one `-1`.
- custom vocab test validates greedy at each step.
- missing `UNK` must raise `vocab_missing_UNK`.

### 2) Coding order
1. Validate `UNK` exists.
2. Precompute max token length (excluding `UNK`).
3. Implement greedy scan in `tokenize_longest`.
4. Add compression logic.
5. Implement `tokenize_batch` as list comprehension.

### 3) One concrete example to narrate aloud
`apppie` with vocab `app=1, pie=3`:
- index 0 longest match is `app` -> `1`
- index 3 longest match is `pie` -> `3`
- output `[1,3]`

### 4) What to say while coding
- "I’m implementing greedy longest-match with bounded window length."
- "I scan from longest to shortest candidate at each index."
- "Compression is optional post-processing and does not change base matching semantics."

### 5) Self-check before final run
- Do I ever skip characters incorrectly?
- Does compression only collapse consecutive UNKs?
- Is batch wrapper behavior identical to single-string behavior?
