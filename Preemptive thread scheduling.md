---
tags:
  - CS446
---
- non-preemptive threads have to voluntarily give up CPU
	- a long-running thread will take over the machine
	- only voluntary calls to `sched_yield`, `sleep`, or finishing, will lead to a context switch

## Preemptive Scheduling
- causing involuntary context switching
	- need to regain control of CPU asynchronously
	- use timer interrupt
	- timer interrupt handler takes over control from current thread, and can result in a new scheduling decision that leads to a context switch
