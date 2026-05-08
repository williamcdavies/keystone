---
tags:
  - CS446
aliases:
  - Address space
  - Protection domains
---
An address space defines a range of discrete addresses. Often an address space in a system with virtual memory corresponds to a highest level translation table.

(virtual) address space: all memory a [[Processes|Process]] can (potentially) address
- linear byte array: $[0, N)$, $N$ roughly $2^{32}$, $2^{64}$

address space $\equiv$ protection domain
- [[Operating systems|Operating system]] isolates address space
- one process can't access another process' address space
- same pointer address values in different processes point to different physical memory locations (translation table)