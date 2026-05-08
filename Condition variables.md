---
tags:
  - CS446
---
a [[Synchronisation]] object that is associated to a condition predicate
- condition variables are not `bool`ean objects; they are `associated` with a `bool` condition predicate

operations on condition variables:
- `wait()` suspends the calling [[Threads|Thread]] until another thread `signal()`s/`broadcast()`s in this condition variable 
	- (should be) called when the condition predicate is `false`
- `signal()` resumes one thread waiting in `wait()`, if any
	- (should be) called once condition predicate becomes `true`, and wants to `Wakeup one` waiting thread
- `broadcast()` resumes all threads waiting in `wait()`
	- (should be) called once condition predicate becomes true, and wants to `Wakeup all` waiting threads

although operations have similar names with [[Semaphores]], they are different
- but one can be used to implement the other

`wait()`: blocks the calling thread
- a thread should decide whether it has to call `wait()` by checking the status of the condition predicate
- if it `wait()`s, it will be blocked
	- semaphore's `sem_wait()` internally checks the integer counter and either proceeds or it blocks the thread on the [[Queues|Queue]]

`signal()`: causes a `wait()`ing thread to wakeup
- if there is no `wait()`ing thread, the `signal()` is lost
	- semaphore's `sem_post()` increments the integer counter, allowing future entry even if no thread is waiting on the queue right now
- i.e., semaphores are "sticky", condition variables have no memory
	- if no thread is `wait()`ing for a `signal()`, it is lost

## Producer-Consumer Problem
solution with two condition variables:
- `has_empty`: buffer has at least one empty slot
- `has_filed`: buffer has at least one filled slot
- `nfilled`: number of filled slots

e.g.,
- if a thread tries to `consume()` and the buffer is empty, ti will be blocked at the second condition variable. if another thread tries to `consume()` again, it will also be blocked at the second condition variables, etc.
- if a third thread tries to `produce()`, it will bypass the first condition variables's `wait()`, and `signal()`(one of) the first two threads

i.e., each condition variables has to have a queue

spurious wakeup - `pthread`
- `pthread_cond_signal()` is only guaranteed to unblock at least one thread
- even worse, a thread blocked in `pthread_cond_wait` can return with no `pthread_cond_signal`/`broadcast()` call

spurious wakeup fix:
- when woken up, a thread must recheck the predicate associated to the condition variable it was waiting on
- most systems use mesa semantics
	- e.g., `pthread`

### Condition Variable `signal()` Semantics
when `signal()` wakes up a `wait()`ing thread, who should get to run?

#### Hoare Semantics:
suspends signaller, and immediately transfers control to a waiter
- the condition and the waiter was anticipating is guaranteed to hold when waiter executes
- too complex and inefficient to implement due to many considerations

#### Mesa Semantics
signal moves a single waiter from the blocked to the runnable state, and the signaller resumes
- problem: condition variable's predicate is not necessarily true when waiter gets to run again
	- return from `wait()` is only a hint that something changed, always have to recheck predicate
- e.g. spurious wakeup: fill one single slot and `signal()`, but before a scheduled woken consumer grabs the queue lock to continue, a different thread enters the queue, grabs the lock, consumes the one filled slot. the woken thread will find the predicate changed once it runs

## Condition Variables with `pthread`
`pthread`'s implementation of `pthread_cond_t` operations require a `pthread_mutex_t`
- need to manually lock/unlock the mutex where appropriate
- `int pthread_cond_wait(pthread_cond_t* restrict cond, pthread_mutex_t* restrict mutex);` automatically waits on `cond` and releases `mutex`
- the function shall block on a condition variable. it shall be called with `mutex` locked by the calling thread or undefined behaviour results. the function atomically releases `mutex` and causes the calling thread to block on `cond`... upon successful return, the `mutex` shall have been locked and shall be owned by the calling thread
- the function shall unblock at least one of the threads that are blocked on teh specified condition variable cond... may be called by a thread whether or not it currently owns the mutex that threads calling `pthread_cond_wait()`... have associated with the condition variable... however, if predictable scheduling behaviour is required, when the mutex is locked by the `pthread_cond_signal()` - calling thread
- for the producer-consumer problem, we need one mutex and two condition variables