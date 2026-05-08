---
tags:
  - CS446
aliases:
  - Process control block
---
A process control block, also sometimes called a process descriptor, is a [[Data structures|Data structure]] used by a computer [[Operating systems|Operating system]] to store all the information about a [[Processes|Process]].

When a process is created (initialised or installed), the operating system creates a corresponding process control block, which specified and tracks the process state (i.e., new, ready, running, waiting or terminated). Since it is used to track process information, the process control block plays a key role in context switching.

An operating system kernel stores process control blocks in a process table.

| PCB             |
|:--------------- |
| Process State   |
| Process ID      |
| Program Counter |
| Registers       |
| Address Space   |
| Open Files      |
