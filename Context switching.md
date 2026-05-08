---
tags:
  - CS446
aliases:
  - Context switch
---
context switching
- the procedure of storing the state of a process or thread, so that it can be restored and resume execution at a later point, and then restoring a different, previously saved, state

changing over the running process
- CPU and MMU (memory management unit) hardware state is changed from one to another
	- can happen thousands of times each second

context switching is very machine-dependent. typical things include:
- save program counter and integer registers (always)
- save condition codes, i.e. the CPU status register (e.g. `EFLAGS` in x86 architecture)
- save floating point registers or other special registers (conditionally optimisable)

tricky:
- need to save program counter to the [[Process control blocks|Process control block]] in memory
	- but that would require to load the program counter of the code that saves the original program counter, which would not be lost
- need to save all registers to the process control block in memory
	- but we have to actually run code to save registers, and running code changes register values
- need combined software/hardware support
	- when an interrupt occurs, the CPU will automatically save the program counter, the status register, and active data registers, at a known location (typically pushes them onto the [[Stacks|Stack]])

context switching has a non-negligible cost
- it represents pure overhead: the system does no useful work while context switching
	- save/restore floating point registers expensive
		- optimisation: only save if process actually used floating point arithmetic
	- may require flushing/invalidating part of the MMU's translation lookaside buffer (TLB) cache
		- memory cache that stores the recently utilised translations of virtual memory to physical memory
		- used to reduce the time taken to access a user memory location
- the operating system must balance context switching frequency with scheduling requirements

context switching usually causes more CPU cache misses
- due to frequent switching between working sets
	- working set: the memory pages most frequently accessed at some point
	- potentially causing cache pollution
- also, in the extreme case of over-commited resources: [[Thrashing]]