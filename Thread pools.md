---
tags:
  - CS446
---
creating a [[Threads|Thread]] for each request is costly
- also, the created thread will exit after service a request

## Thread Pool
- more user requests increase the number of required threads
- pre-create/allocate a number of threads waiting for work
- waking up a thread to serve user request 
	- faster than form-scratch thread creation
- when request is done, don't exit
	- return to thread pool
- imposes a limit to the max number of threads