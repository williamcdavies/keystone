---
tags:
  - CS446
aliases:
  - Child process
---
A [[Processes|Process]] is created by another process.
- parent is creator, child is created (Unix: `ps` "PPID" field / `pstree -p` command)
- very first process (Unix: `init` / Linux: `systemd` (PID 1 and PPID 0)). "Once the kernel has started, it starts the `init` process, a "Daemon" which then bootstraps the user space, for example by checking and mounting filesystems, and starting up other processes. The `init` system is the first daemon to start and the last daemon to terminate." 
	- note: `init` is a user space process

parent defines resources and privileges for its children
- Unix: process user ID is inherited - children (processes) of your shell (process) will execute with the same user privileges 

after creating a child process
- parent process may either wait for it to finish its task, or concurrently continue its work

## Process Creation in Windows

```c
CreateProcess( prog, // Module to load (e.g. "c:\\winnt\notepad.exe" or NULL - use command line)
	argv[1], // Command line args
	NULL, // Process handle not inheritable
	NULL, // Thread handle not inheritable
	FALSE, // Set handle inhertiance ot FALSE
	0, No creation flags
	NULL, // Use parent's environment block
	NULL, // Use parent's starting directory
	&spi, // Pointer to STARTUPINFO structure
	&pi ) // Pointer to PROCESS_INFORMATION structure
)
```

1. creates and initialises a new [[Process control blocks|Process control block]]
2. creates and initialises a new address space
3. loads the program specified by `prog` into the address space
4. copies `args` into memory allocated in address space
5. initialises the saved hardware context  to start execution at `main`
6. places the process control block on the rady queue

note: returns `BOOL`. If `CreateProcess` succeeds, it returns a `PROCESS_INFORMATION` structure that contains handles and identifiers for the new process and its primary thread. The thread and process handles are created with full access rights, although you can restrict access if you specify security descriptors.

## Process Creation in Unix

```c
pid_t fork (void)
```

1. creates and initialises a new process control block
2. creates a new address space
3. initialises the address space with a `copy` of the address space of the parent
4. initialises the kernel resources to point to the parent's resources (e.g. open files)
5. places the process control block on the ready queue

`fork()` returns twice:
because if it's successful, we now have two processes
- returns the child's PID to the parent process
- returns $0$ to the child process

```c
#include <stdio.h>
#include <unistd.h>
int main(int argc, char* argv[]) {
	char* name = argv[0];
	int fork_retval = fork();
	if (fork_retval == 0) {
		printf("I'm the child of %s and my pid is: %d\n", name, getpid());
		return 0;
	} else {
		printf("I'm the parent and my chlid's pid is: %d\n", fork_retval);
		return 0;
	}
}
```

expected program (`$ gcc -o fork_proc fork_proc.c && ./fork_proc`) output?:

```
I'm the parent and my child's pid is: 486
I'm the child of ./fork_proc and my pid: 486
```

running a program

```c
int execv(char* path, char* argv[]);
int execve(const char* filename, char* const argv[], char* const envp[]);
int execvp(const char* file, char* const argv[]);
```

`v`: takes an `argv` array of C-strings populated with the program, its arguments/flags, and a `NULL`-pointer at the end
`e`: takes an `envp` array of C-strings populated environment variables
`p`: inherits the parent process environment

`execXX()`
1. stops the program from executing under the current process
2. loads the new program `prog` into the calling process' address space
3. initialises hardware context and args for the new program
4. places the program control blcok onto the ready queue
note: It does not create a new process. "... it replaces the entire current process with a new program image". It loads the program into the current process' address space and runs it from the entry point. (Also, in PintOS, `exec` is more like a combined `fork/exec`)

most calls to `fork()` will be followed by `execXX()`
- can always be combined in a single `spawn` system call

very useful when
- child is working together with parent
- child relies on parent's data to accomplish its task

real win is in the simplicity of its interface
- many things we might want to do to the child process
	- manipulate file descriptors, set environment variables, reduce privileges, etc.
- yet `fork()` requires no arguments at all
	- remember: Windows `CreateProcess()` system call required a lot of different function call arguments to cover the possibilities for the new program we intend to run