---
tags:
  - CS446
aliases:
  - Exception
---
exceptions (or software interrupts) are caused by the CPU executing instructions instructions (synchronous)
- classified as traps, faults, or aborts
- note: in Intel architecture:
	- traps are restarted at the address following the address causing the trap
	- faults are restarted at the address of the faulting instruction
	- aborts give no reliable restart address
- x86-architecture `int` instruction, page fault, divide-by-zero, etc.