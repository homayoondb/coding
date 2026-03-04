# 07_sol Guide: SQL + Python Data Cleaning


## Walkthrough: Exactly How to Solve `07_mock`

### 0) First 3 minutes
- Write target cleaned schema: `order_id, order_date(ISO), region(upper/trim), amount(float)`.
- Decide invalid-row policy: drop rows with invalid amount/date.

### 1) Should I read tests now?
Yes:
- `o1` latest row must win (`1250.0`).
- invalid amount/date rows must be dropped.
- `None`/blank region must become `UNKNOWN`.
- expected region summary is exact.

### 2) Coding order
1. `parse_amount` and `parse_order_date` first (unit-testable).
2. `extract_clean_rows` with SQL dedupe + Python normalization.
3. `summarize_by_region`.
4. `top_day`.

### 3) One concrete example to narrate aloud
Order `o1` has two rows:
- 10:00 amount `$1,200.00`
- 12:00 amount `$1,250.00`
You select latest by `updated_at`, parse amount to `1250.0`, and keep only that row.

### 4) What to say while coding
- "I’m locking canonical schema first so cleaning rules are unambiguous."
- "Dedupe happens before aggregation to avoid double counting."
- "Parsing helpers return `None` on invalid input so filtering is explicit."

### 5) Self-check before final run
- Do malformed rows leak into summary?
- Is region normalization deterministic?
- Is top-day tie behavior deterministic?
