---
tags:
  - CS446
---
- [[Threads]] directly supported by the kernel
	- virtually all modern [[Operating systems]] support kernel threads

- all thread options are implemented in the kernel by an operating system provided API
- the operating system schedule all the threads in the system
- threads initially called lightweight processes
	- Windows: threads
	- Solaris: lightweight processes (`LWP`)
	- POSIX: threads (`pthreads`)

## Limitations
- every thread operation must go through the kernel (system call interface)
	- kernel has to do creation, exiting, joining, synchronisation, scheduling/switching
		- on typical laptop: `syscall` might take $100$ cycles, a function `call` only takes $5$ cycles
		- result: threads 10x-30x slower when implemented in kernel
- one-size-fits-all thread implementation
	- kernel threads must please every user of the operating system
	- user may have to pay for certain features that (priority, etc.) aren't necessary
- general heavy-weight memory requirements
	- e.g. requires its own fixed-size thread [[Stacks|Stack]] within the kernel
		- remember: in Linux, every thread has its own user stack and its own kernel stack
	- other required data structures designed for heavier-weight processes