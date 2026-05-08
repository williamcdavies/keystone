---
tags:
  - CS446
aliases:
  - Thread
---
Modern [[Operating systems]] have implementations of the concepts of [[Processes]] and threads.

thread
- defines a sequential execution stream within a process (PC, SP, registers)
	- threads are separate streams of execution the share an [[Address spaces|Address space]]
	- this allows one process to have multiple points of execution (will exist multiple associated states of execution)
		- can potentially use multiple CPUs

process
- defines an address space and general process attributes

a thread is bound to a single process
- a process can however have multiple threads

a thread now becomes the unit of scheduling
- processes are now "containers" under which threads execute
- threads become the actual "dynamic" entities

## Threads in a Process
threads in the same process share the same global memory
- code and data and heap segments
	- i.e., share code, data, files, etc.

## Threads & Processes
why?
- concurrency does not always require creation of an entirely new process
- easier to support multithreaded applications

multithreading can be very useful
- can unlock "parallelism", i.e., the potential to allocate different threads to multiple cores / CPUs
	- note: not an easy task, adds in numerous optimisation considerations, e.g., memory pollution
- improving a program's structure
- handling simultaneous events (e.g. web requests)
- allowing a program to overlap I/O and computation

so, multithreading is even useful on a single-core processor
	- although today we can have multicore power-efficient microprocessors in almost everything
- required software engineering skillset:
	- synchronisation

## Multithreaded Concurrent Server
using `fork()` to create a new process to handle requests is overkill:
- remember:

```c
for(;;) {
	int client_sock = accept(server_sock, addr, addrelen);
	if ((child_pid = fork()) == 0) { // Child
		close(server_sock);
		handle_request(client_sock);
	} else { // Parent
		// back to for(;;)
	}
}

void handle_request(int sock) {
	// Process client request
	close(sock);
}
```

instead, create a new thread for each request:
- example:

```c
void run_web_server() {
	for(;;) {
		int client_sock = accept(server_sock, addr, addrlen);
		thread_create_interface(handle_request, client_scok);
	}
}

void handle_request(int sock) {
	// Process client request
	close(sock);
}
```

## Thread API (Unix)
`int pthread_create(pthread_t* thread, const pthread_attr_t* attr, void* (*start_routine) (void*), void* arg);`
- create a new thread in the calling process, run `start_routine` with arguments `arg`
	- can be customised via `attr`

`int pthread_join(pthread_t thread, void** retval);`
	- the calling thread waits for the target thread specified by `thread` to terminate
		- if that thread has already terminated, then `pthread_join()` returns immediately
		- the target thread specified by `thread` must be joinable (i.e, not created with `PTHREAD_CREATE_DETACHED`, or `pthread_detach()`ed later)
		- if the supplied `retval` is not `NULL`, then it copies the exit status of the target thread (i.e., the value that it supplied to `pthread_exit()`)

`void pthread_ext(void* retval);`
- terminates the calling thread and returns a value via `retval` that (if the calling thread is joinable) is made available to another thread in the same process that calls `pthread_join()`
- performing a `return` from the start function of any thread other than the main thread results in an implicit call to `pthread_exit()`, using the function's return value as the thread's exit status
- to allow other threads to continue execution, the main thread should terminate by calling `pthread_exit()` rather than the `exit()` system call
- the value pointed to by `retval` should not be located on the `calling` thread's [[Stacks|Stack]], since the contents of that stack are undefined after the thread terminates

## Thread Implementation
a general prototype:
$\dots$ `thread_create(` $\dots$ `, start_routine, args);`
- allocate [[Thread control blocks|Thread control block]]
- allocate thread stack
- build stack frame for base of thread stack
- put `start_routine`'s `args` on thread stack
- put thread on ready queue for scheduling