# 09_sol Guide: LeetCode 609 Find Duplicate File in System


## Walkthrough: Exactly How to Solve `09_mock` (LC 609)

### 0) First 2 minutes
- Write parse contract:
  - first token is root
  - others are `name(content)`
- Write grouping contract:
  - key by content
  - keep groups with size >= 2

### 1) Should I read tests now?
Yes:
- Confirm canonical sample groups.
- Confirm no-duplicate input returns `[]`.
- Confirm malformed token should raise error.

### 2) Coding order
1. Loop rows -> split by spaces.
2. Extract `root`.
3. Parse each file token into `name` + `content`.
4. Build full path `root/name`.
5. Append into `content_to_files[content]`.
6. Filter and sort groups for deterministic tests.

### 3) One concrete example to narrate aloud
Row: `root/a 1.txt(abcd) 2.txt(efgh)`:
- parse root as `root/a`
- add `root/a/1.txt` under content `abcd`
- add `root/a/2.txt` under content `efgh`
Later rows with same content join same bucket.

### 4) What to say while coding
- "I map content to file paths to avoid O(n^2) comparisons."
- "I return only buckets with duplicates."
- "I sort for deterministic testing; original problem allows any order."

### 5) Self-check before final run
- Are full paths constructed correctly?
- Do singleton groups get excluded?
- Do malformed file tokens fail fast?
