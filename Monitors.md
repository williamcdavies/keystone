---
tags:
  - CS446
---
an object-oriented language construct that controls access to shared data
- [[Synchronisation]] code added by compiler, enforced at runtime

a module that encapsulates
- shared data structures
- procedures that operate on the shared data structures
- synchronisation between concurrent [[Threads]] that invoke these procedures

guarantees that access of its data through threads is done in legitimate ways only

a monitor aims to guarantee mutual exclusion
- only one thread can execute any monitor procedure at a time
	- the thread is inside the monitor
- if a second thread invokes a monitor procedure when a first thread is already executing one, the second thread shall block
	- i.e., the monitor has to have a wait [[Queues|Queue]]
- if a thread that is inside a monitor blocks, then another thread can enter the monitor

note: a monitor invariant is a safety property associated with the monitor
- its an assertion regarding the monitored variables
- it holds whenever a thread enters or exits the monitor
	- i.e., the assertion holds whenever there is no thread execution inside the monitor

a monitor is like one big super-lock for a set of operations/methods
- it is however a language-level implementation
	- compiler automatically inserts the necessary synchronisation operations upon entry and exit of monitor procedures
	- c++ does not have monitor

## Monitors & Condition Variables
remember: a monitor also needs to take care of wait, wakeup, queueing functionalities
- not just locking
- what if a thread has to wait for something to happen/change, but is already inside the monitor
	- bad if left to just busy-wait
	- worse: no one can now get inside the monitor (eg., not even to take corrective actions)
- have to be able to let a different thread enter inside the monitor

to achieve the above, a monitor's implementation can use a known synchronisation mechanism: [[Condition variables]]
- a condition variable whose associated condition predicate reflects a necessary condition for a thread to make progress once it is inside the monitor

## Condition Variables (With Respect to Monitors)
- access to the monitor is controlled by a lock

`wait()`
- suspends the calling thread and releases the monitor lock (when it resumes, it will reacquire the monitor lock) for `wait()` to be called, the thread has to already be inside the monitor (hence holds the monitor lock)
	- remember: (should be) called when the associated condition predicate is `false`

`signal()`
- resumes one thread waiting in `wait()`, if any
	- remember: (should be) called once condition predicate becomes `true`, and wants to `Wakeup one` waiting thread

`broadcast()`
- resumes all threads waiting in `wait`
		- remember: (should be) called once condition predicate becomes `true`, and wants to `Wakeup all` waiting threads

remember: condition variables are not `bool`ean objects, they are associated with a `bool`ean condition predicate
- `if (cv) then`... does not make sense
- `if (monitor_condition == false) then wait(cv)` does