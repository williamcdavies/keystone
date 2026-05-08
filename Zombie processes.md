---
tags:
  - CS446
---
[[Child processes|Child process]] that terminates, but has not been `wait()`ed for yet (by the parent). The kernel maintains a minimal set of information about the zombie (PID, termination status, resource usage information) in order to allow the parent to later perform a `wait()` to obtain information about the child. As long as a zombie is not removed from the system via a `wait()`, it will consume a slot in the kernel process table, and if this table fills, it will not be possible to create further processes. If a parent process terminates, then its zombie children (if any) are adopted by `init()`, which automatically performs a `wait()` to remove the zombies.

note: every process spawned after `init` has a parent process
- each parent can have many children and those can have their own children
- zombie processes are eventually "adopted" by `init`, which will routinely `wait()` on and reap any zombie children