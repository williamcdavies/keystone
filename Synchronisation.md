---
tags:
  - CS446
---
## Layer Approach to Synchronisation
- hardware provides simple low-level atomic operations
	- upon which we can build high-level synchronisation primitives
		- upon which we can implement critical sections and build correct multi-threaded/multi-processing programs
- example low-level atomic operations
	- on uniprocessor, disable/enable interrupts
	- on x86, aligned-load and aligned-store of words
	- special instructions: test-set-lock/exchange (TSL, XCHG), compare-and-swap (lock CMPXCHG)
- example high-level synchronisation primitives
	- lock, semaphore, monitor

## Synchronisation Motivation
[[Threads]] cooperate in multithreaded programs 
- to share resources, access shared data structures
- to coordinate their execution

for correct execution, control of this cooperation is required
- thread scheduling is non-deterministic (i.e., runtime behaviour changes on same program re-runs)
	- scheduling is not under the program's control
		- schedular is part of [[Operating systems|Operating system]]
	- threads interleave executions arbitrarily and at different rates
- multi-word operations are not atomic
- compiler reordering and/or hardware reordering

## Shared Resources
initially focus on controlling access to shared resources

basic problem
- if two concurrent threads are accessing a shared variable, and that variable is read/modified/written by those threads, then access to the variable must be controlled

we need
- mechanisms to control access to shared resources
	- locks, mutexes, semaphores, monitors, condition variables, etc.
- patterns for coordinating accesses to shared resources
	- bounded-buffer, producer-consumer, etc.

the previously demonstrated problem (bank problem, not copied) came from accessing a shared resource without proper synchronisation
- [[Race conditions|Race condition]]

controlled-access mechanisms to shared data structures are required to deal with concurrency, so we can ensure a degree of determinism in program execution

what is shared:
- local variables are not shared
	- refer to data on the [[Stacks|Stack]]
	- each thread has its own stack
	- note 1: potentially dangerous to pass/share/store a pointer to a local variable on the stack of one thread to another
	- note 2: but not UB as long as lifetime of objects hasn't ended
- global and `static` variables are shared
	- stored in the static data segment, accessible by any thread
- dynamic and other heap data are shared
	- allocated from heap with `malloc`/`free`

## Mutual Exclusion
we use mutual exclusion to synchronise access to shared resources
- allows us to build larger atomic blocks

critical section: code that uses mutual exclusion to synchronise its execution
- only one thread's execution at a time can-or-be in the critical section
- all other threads are forced to wait on entry
- when a thread leaves a critical section, another can enter

### Critical Section Requirements
- mutual exclusion (mutex)
	- if one thread in is in the critical section, then no other is
- liveness (progress)
	- if some thread $T$ is not in the critical section, then $T$ cannot prevent some other thread $S$ from entering
		- if multiple threads simultaneously request to enter critical section, one must be allowed to proceed 
		- a thread's operations outside the critical section should not be able to prevent another one to proceed
	- a thread in the critical section will eventually leave it
- bounded waiting (starvation-free)
	- if some thread $T$ is waiting on the critical section, then $T$ will eventually enter the critical section
- performance
	- the overhead of entering and exiting the critical section is small with respect to the work being done within it

### Critical Section Desired Properties
- safety: nothing bad should happen
	- mutex
- liveness: something useful should be happening
	- progress, bounded waiting
- performance
	- efficiency: don't consume too many resources while waiting
		- don't busy-wait. better to relinquish CPU and let another thread run
	- fairness: don't make one thread wait longer than others
		- hard to do efficiently
	- simplicity: should be simple to use
	- properties hold for each run, while performance is quantified by all runs

### Implementing Locks
- `void lock();`: acquire the lock object exclusively; wait if not available
- `void unlock();`: release exclusive access to the lock object
- `lock_t lock;`: shared lock object type implementation, manipulated by `lock()` and `unlock()`
- on a uniprocessor we can cheat
	- implement mutual exclusion by disabling/enabling interrupts
	- good:
		- simple
	- bad:
		- both operations are privilege, user-level program not allowed to use them
		- doesn't work on multiprocessor
- software-based lock algorithm:
	- good:
		- shouldn't require much from hardware
	- only assumptions:
		- loads and stores are atomic
		- they execute in-order
			- (vs. out-of-order execution)
		- does not require special hardware instructions

### Spin-Waiting vs. Blocking
- problem: waste of CPU cycles
	- worse case scenario: a thread holding a busy-wait lock gets preempted, and then some other thread tries to acquire the same lock
- on uniprocessor: should not use a spin-lock
	- should yield CPU when lock is not available
- on multiprocessor
	- if a thread holding lock gets preempted, the correct action depends on how long before the lock would be released
- problem with simple yield
	- uncontrollably results in a lot of context switches
		- thundering herd
	- starvation due to lack of control over which thread gets the lock still becomes possible
- why?
	- no control over who gets the lock next
	- need explicit control to ensure which thread should get the lock

### Reader-Writer Problem
- a read er is a thread that needs to look at the shared data but won't change it
- a writer is a thread that modifies the shared data
- problem: with the regular lock approach, there is unnecessary synchronisation
	- only one writer should be active at a time
	- however, any number of readers can be active simultaneously
- solution
	- acquire lock for read mode and write mode

#### `read_lock`
acquires lock in read mode
- if lock is not acquired or in read mode: success
- otherwise, lock is in write mode: wait

#### `write_lock`
acquires lock in write mode
- if lock is not acquired: success

## Semaphore & Condition Variable Summary
- [[Semaphores]] and [[Condition variables]] can be used to solve any of the traditional synchronisation problems
- drawbacks:
	- they are essentially shared global variables
		- can potentially be accessed anywhere in a program
	- no direct connection between the semaphore and the data being controlled by it
	- used for both critical sections (mutex) and execution ordering
	- no control or guarantees for their proper usage
- when used in complex code can lead to bugginess
	- solution: leverage object-oriented programming to support controlled behaviours