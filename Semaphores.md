---
tags:
  - CS446
---
## Semaphore Motivation
problem with lock:
- ensures mutual exclusion, but has no execution ordering semantics

producer-consumer problem: ensuring execution order makes sense
- producer: creates resources
- consumer: uses resources
- bounded buffer: shared between them
- execution order: producer should just wait if bounded buffer is full, consumer should just wait if bounded buffer is empty
	- e.g., `$ cat entries.txt | sort | uniq | wc`

## Semaphore Definition
abstract data type to provide [[Synchronisation]]

a synchronisation object that contains an integer counter variable
- no direct access to integer counter variable
- semaphore safety property: integer counter value never allowed to go below $0$
- integer counter variable must be initialised to some value:
	- `sem_init(sem_t* s, int pshared, unsigned int value)`
- operations to manipulate integer counter variable:
	- `sem_wait`: decrements, blocks until semaphore is open
	- `sem_post`: increments, allows another [[Threads|Thread]] to enter

## Blocking in Semaphores
associated with each semaphore is a [[Queues|Queue]] of waiting threads

when `P()`/`sem_wait` is called by a thread:
- if semaphore is open, the thread continues
- if semaphore is closed, the thread will block and be placed on the queue

when `V()`/`sem_post` opens the semaphore:
- if a thread is waiting on the queue, it is unblocked
- if no threads are waiting on the queue, the signal is remembered for a next thread (that will perform `P()`/`sem_wait`)
	- in other words, `V()` has memory
		- in contrast to condition variables
	- this memory property is derived form the integer counter value

## Semaphore Types

### Mutex Semaphore (or Binary Semaphore)
- represents single access to a resource
- guarantees mutual exclusion to a critical section

### Counting Semaphore (or General Semaphore)
- represents a resource with many units available, or a resource to which we want to limit concurrent access (e.g., reading)
	- is initialised to number of resources available
- multiple threads can pass the semaphore "wait" test
- number of threads determined by semaphore "counter"

## Semaphore Uses
mutual exclusion
- case of binary semaphore
execution ordering
- case of limiting concurrent access $\rightarrow$ counting semaphore

## Producer-Consumer Problem
- bounded buffer
	- size $N$, access entry $0 \dots N - 1$, then wraps around to $0$ again

- producer thread: writes data to bounded buffer
- consumer thread: reads data from bounded buffer
- execution ordering constraints:
	- producer shouldn't try to produce if bounded buffer is full
	- consumer shouldn't try to consume if bounded buffer is empty