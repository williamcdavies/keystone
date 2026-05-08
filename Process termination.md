---
tags:
  - CS446
---
## Normal Termination
in Unix: `exit (int status)` (in Windows: `ExitProcess (int status)`)

frees resources and terminates "normally", returns `status & 0xFF` to parent `wait()`
1. terminate all threads
2. close open files, network connections
3. allocated memory
4. remove PCB from kernel data structures, delete

note: all functions registered with `atexit()` and `on_exit()` are called, in the reverse order of their registration. $\dots$ all open `stdio` streams are flushed and closed. Files created by `tmpfile()` are removed.

`exit()` is a system call, i.e., a [[Processes|Process]] does not just simply clean up after itself

## Immediate Termination
in Unix: `_exit (int status)`

frees resources and terminates "immediately", returns `status & 0xFF` to parent `wait()`

note: terminates the calling process "immediately". Any open [[File descriptors]] belonging to the process are closed; any children of the process are inherited by process $1$, `init`, and the process's parent is sent a `SIGCHLD` signal.

i.e., calling the "normal" `exit()` from a `fork`ed child that hasn't successfully `exec`ed something (to replace the original process image it inherits), will interfere with the parent process's external data (files) via calling its `atexit()` handlers, calling its signal handlers, and/or flushing buffers.

rule-of-thumb:
- use `_exit()` to abort the child when the `exec` fails
- use `_exit()` to terminate a child that performs no `exec` (more rare)