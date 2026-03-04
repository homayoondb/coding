# 06_sol Guide: Concurrent Web Crawler


## Walkthrough: Exactly How to Solve `06_mock`

### 0) First 2 minutes
- Decide canonical URL format first (`urldefrag` + parse host).
- Decide dedupe rule: add to visited when enqueued/scheduled.

### 1) Should I read tests now?
Yes:
- Expected output list shows exactly which URLs survive.
- Both single and multi must return same sorted result.
- Parser call count must equal number of visited URLs.

### 2) Coding order
1. `normalize_url` first (easy win).
2. `crawl_single_thread` using queue + visited + same-host filter.
3. `crawl_multi_thread` with executor + in-flight futures + lock-protected visited updates.

### 3) One concrete example to narrate aloud
From `start`, parser returns:
- `https://docs.local/a#intro` -> normalize to `/a`
- `https://external.com/ignore` -> filtered by host check
This demonstrates why normalization and same-host filtering happen before scheduling.

### 4) What to say while coding
- "I am using single-thread as correctness baseline before concurrency."
- "I protect visited-set updates to avoid duplicate scheduling races."
- "I normalize URLs before dedupe, otherwise fragments would create false duplicates."

### 5) Self-check before final run
- Is each URL fetched at most once?
- Can external host URLs leak in?
- Do multi-thread and single-thread outputs match exactly?
