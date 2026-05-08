---
tags:
  - CS446
---
context switching in the same process, such that virtual memory [[Address spaces|Address space]] is not switched
- which would otherwise involve memory address mappings, page tables, and kernel resources
- note: without additional considerations, thread context switching can lead to memory pollution

the context switch routine does all of the magic
- saves context of the outgoing (`current`) thread
	- push all machine state onto the top of the kernel [[Stacks|Stack]] of the outgoing thread
- restores context of the incoming (`new`) thread
	- pop all machine state from the kernel stack of the incoming thread and loads it into CPU registers
- the incoming thread becomes the `current` thread
- return control to caller of the incoming thread

all this has to be done in [[Assembly language]]
- works at the level of the procedure calling conventions, so itself cannot be implemented by using procedure calls

