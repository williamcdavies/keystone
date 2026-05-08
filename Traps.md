---
tags:
  - CS446
---
a trap is an intentional software-generated [[Exceptions|Exception]]
- the main mechanism for [[Programs]] to interact with the [[Operating systems|Operating system]]
	- on x86, programs can use the `int n` instruction to cause a trap
	- on ARM, the `SVC` instruction

the handler for a trap is defined in the interrupt descriptor/vector table
- kernel chooses the vector number (e.g. `n`) for representing the system call trap

## System Call
for a user space program to invoke an operating system service
- also referenced as "crossing the protection boundary", or "protected control transfer"

the system call instruction
- causes an [[Exceptions|Exception]], which is vectored to a kernel handler
- passes a parameter determining the desired system routine to call
- saves the caller state so it can be restored
	- returning from a system call restores this state

architectural support is required to:
- restore saved state
- change mode
- resume execution
