---
tags:
  - CS446
---
- [[Threads|Thread]] management done by user-level thread library, kernel knows nothing
- implement as a user-level thread library (a.k.a. green threads)
- one kernel thread per process
	- creating, exiting, joining, etc. are just functions of a suer-level thread library
	- library does thread [[Context switching]]
- user-level threads are small and fast
	- Java `Thread`
	- POSIX:  threads (`pthreads`)

## Limitations
- can't take advantage of multiple CPUs or cores
- user-level threads are "invisible" to the [[Operating systems|Operating system]]
	- not directly integrated with the operating system
- as a result, the operating system can make poor decisions
	- deciding to schedule a process with idle user-level threads
	- a "blocking" system call (e.g., disk read) blocks all user-level threads of that process, even if the process has other user-level threads that can be executed
	- unscheduling a process with a user-level thread that is holding a lock

## At User-Space
- allocate a new thread [[Stacks|Stack]] for each `thread_create`
- keep a [[Queues|Queue]] of runnable threads
- configure a periodic timer-based signal (e.g., system call for interval timer `settimer()`)
	- switch to another thread on timer signal (e.g., `SIGALRM`)
- replace blocking system calls with nonblocking versions
	- if operations `WOULD_BLOCK`, switch and run different thread
- all these have to be performed/accounted for at the user space
- the thread schedular determines when a thread runs
- it uses queues to keep track what threads are doing
	- just like the operating system and processes
	- but it is implemented at user-level in a library
- run queue: threads currently running (usually one)
- ready queue: threads ready to run
- pending queue: threads waiting on a condition until they can be come ready 
	- e.g., thread `sleep()`ing; placed there by schedular until a certain interval timer (operating system-managed) expiration occurs, at which point it will move it back to ready queue

## Multiplexing
Use both kernel-level and user-level threads
- associate user threads with a kernel thread
- a thread library is required to map user threads to kernel threads

### One-to-One (1 : 1 Threading)
- one user-level thread maps to one kernel-level thread
- good: 
	- more concurrency
		- when one thread "blocks", others can run
		- better multicore/multiprocessor performance
- bad: 
	- expensive
		- thread operations involve kernel
		- threads need kernel resources

### Many-to-One (N : 1 Threading)
- many user-level threads maps to one kernel-level thread
- good:
	- fast
		- no system calls required
	- portable
		- few system dependencies
- bad:
	- no parallel execution of threads
		- all threads "block" when e.g. one waits for I/O

### Many-to-Many (N : M Threading)
- many user-level threads maps to many kernel-level threads
- $N \geq M$
- good:
	- flexible
		- operating system creates kernel threads for physical concurrency
		- applications create user threads for application concurrency
- bad:
	- complex implementation
		- most programs use 1:1 threading model anyway

### Two-level
similar to N:M
- except that a user-level thread can be bound to a kernel-level thread

## Thread Miscellanea
- semantics of `fork()` system call
	- POSIX `fork()` copies only the calling thread
		- effectively, entire memory is duplicated, but the child process will only have one active thread, i.e., only the calling thread will be in a non-suspended state
	- note: potentially dangerous to call `fork()` from a multi-threaded process as any mutexes held in non-calling threads will be forever locked in the child process
- signal handling
	- POSIX `pthreads` requires all threads in a process to:
		- share some process-wide attributes, including:
			- signal dipositions
		- have some distinct attributes
	- Linux's implementation will by default try to deliver to the main thread first, unless another thread has been nominated by the user