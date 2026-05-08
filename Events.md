---
tags:
  - CS446
---
an event is a "forced" change in execution control flow
- events immediately stop current execution
- changes mode, context (machine state), or both

the [[Operating systems|Operating system]] kernel defines a handler for each event type
- the specific types of events are defined by the architecture
	- e.g. timer event, input/output interrupt, system call, trap/software interrupt

after operating system [[Bootloaders|Booting]], all entry to kernel space is a result of some event
- event immediately stops current execution
- changes mode to kernel mode
- invoke a piece of code to handle event (event handler)

when the CPU receives an event of a given type, it:
- transfers control to handler (within the operating system kernel)
- handler saves program state (program counter, registers, etc.)
- handler executes core operating system functionality, e.g., writing data to disk
- handler restores program state, resumes program execution