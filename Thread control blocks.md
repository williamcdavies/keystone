---
tags:
  - CS446
aliases:
  - Thread control block
---
the required data structure (implementation specific)
- lightweight and fast

- thread identifier: unique id (`tid`) assigned to every new [[Threads|Thread]]
- execution state of thread (e.g., running, ready, waiting, started, terminated)
- [[Stacks|Stack]] pointer (`ESP` and `EBP` in x86): points to thread's next instruction
- other register values of the thread
- pointer to [[Process control blocks|Process control block]] of the [[Processes|Process]] the thread lives in