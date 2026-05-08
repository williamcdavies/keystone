---
tags:
  - CS446
aliases:
  - Race condition
---
a timing-dependent error involving shared state

very bad
- non-deterministic
	- can't know what the output will be, and it is likely to be different across runs
- hard to detect
	- too many possible schedules
- hard to debug
	- heisen-bug: debugging changes timing so it can hide the bugs (vs. bhor-bug)

## Avoiding Race Conditions
- atomic operations
	- no other instructions can be interleaved
	- entire operation is executed as a unit - guaranteed by hardware
- possible approach:
	- have a dedicated atomic instruction for the job:
		- `add $0x1, 0x8049780`
- problem:
	- can't anticipate very possible way we may desire atomicity
	- increases hardware complexity, slows down other instructions