---
tags:
  - CS446
---
- [[Threads]] voluntarily give up the CPU by `yield()`ing

`int sched_yield (void);` causes the calling thread to relinquish the CPU. The thread is moved to the end of the [[Queues|Queue]] for its static priority and a new thread gets to run. 

- in other words, it causes context switching to another thread
- so `sched_yield()` returns once we have context-switched back to the calling thread
	- e.g. because another thread called `sched_yield()`