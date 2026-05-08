---
tags:
  - CS446
aliases:
  - Process
---
A process is the instance of a computer [[Programs|Program]] that is being executed by one or more threads. Almost all processes are rooted in an [[Operating systems|Operating system]] process which comprises the program code, assigned system resources, physical and logical access permissions, and [[Data structures]] to initiate, control, and coordinate execution activity.

A process is a program in execution.
- defines the sequential execution of a program
- programs are static entries with the potential for execution

A process contains the full state of a program in execution.
- an [[Address spaces|Address space]]
- the code for the executing program
- the data for the executing program
- an execution [[Stacks|Stack]] encapsulating the state of procedure calls
- the program counter indicating the next instruction
- a set of general-purpose registers with current values
- a set of operating system resources

A process is named using its process identifier, or PID.

## Transition of Process Execution State
As a process executes, it moved from execution state to execution state.
- in Unix `ps: STAT` column indicates execution state
	- maximum number of processes in operating system: "In the Linux kernel space context, a process and a thread are one and the same. They're handled in the same way by the kernel. They both occupy a slot in the `task_struct`. A thread, by common terminology, is in Linux a process that shares resources with another process (they will also share a thread group ID)"
		- `/proc/sys/kernel/threads-max`
		- `/proc/sys/kernel/pid_max`

## State Queues
how the operating system keeps track of processes

simple $1$st idea:
- list of processes
- how to find out ones in the ready execution state
	- iterating through the list is slow

improvement:
- partition list of process based on type of execution state
- operating system maintains a collection of queues that represent the execution state of all processes
	- a typical implementation is to have one queue for each type of execution state: ready, waiting, etc.
- each[[Process control blocks|Process control block]] is queued on a state queue according to its current execution state
	- when a process changes execution state, its process control block is moved from one state queue into another

## Waiting on a Process
in Unix: `pid_t wait (int* status)` (in Windows: `WaitForSingleObject(eHandle, millis)`)
- suspends current process until the `pid-specified` [[Child processes|Child-process]]  changes state (terminated, or stopped/resumes by a signal)

`pid_t waitpid (pid_t pid, int* status, int options)`
- suspends current process until the `pid-specified` child process changes state
	- `pid` $> 0$: wait for the child whose process ID is equal to the value of `pid`
	- `pid` $= 0$: wait for the child whose parent group ID is equal to that of the calling process
	- `pid` $= -1$: wait for any child process
	- `pid` $< 0$: wait for any child process whose process group ID is equal to the absolute value of `pid`

return value of `wait/waitpid`:
- `wait()`:
	- on success, returns the PID of the state-changed (e.g. terminated) child; on error, $-1$ is returned
- `waitpid()`:
	- on success, returns the PID of the child whose state has changed; if `WNOHAND` was specified and one or more child(ren) specified by PID exist, but have not yet changed state, then $0$ is returned. on error, $-1$ is returned

The purpose of the `wait()` syscall is to allow the child process to report a status back to the parent process
- child process is not completely cleaned up when it `exit()`s
	- it "dies" as a running process, most resources are released, but it still remains in the process table
		- that's where its exit status is stored, so that the parent can retrieve it by calling one of the `wait()` variants
- it will remain and keep consuming that process table slot until it is "reaped" (by being `wait()`ed on)
- Unix: every process must be "reaped" by a parent

## Process Miscellanea
- a process can be `kill()`ed
	- not just by a parent process
	- any process running under the same user ID or as the `root` user can `kill()` any other process
	- terminal command sequence ctrl-c can be used to send `SIGINT` signal to the active process (in that terminal)
		- will (by default - unless otherwise handled) terminate that process
	- terminal command sequence ctrl-z can be sued to send `SIGTSTP` signal to the active process (in that terminal)
		- will (by default - unless otherwise handled) pause that process and move it to background
		- command `jobs` can be used to see such stopped (alive, just not running) background processes
		- typing `fg` in shell will resume it in foreground, `bg` will resume it in background
- whn a parent process is `kill()`ed, it doesn't by default `kill()` the children processes
	- you can do that by `kill()`int a process group
		- use with (negative) process group ID (PGID)
		- or use `killpg()`
	- as mentioned if the parent process is `kill()`ed first, it will leave [[Orphan processes]] out of any children processes
