---
tags:
  - CS446
---
Interaction between [[Processes|Process]] is sometimes desired.
- conceptually simples form is through files: `vim` edits file `gcc` compiles it
- more complicated: shell/command, window-manager, application

## Message-Passing (Through the Kernel)
- pros: all sharing is explicit $\rightarrow$ fewer chances for errors
- cons: data copying. crossing [[Address spaces|Protection domains]]

## Shared Memory (Sharing a Region of Physical Memory)
- pros: performance. set up shared memory once, then access without crossing protection domains
- cons: synchronisation is required. things can change behind your back. error prone

`int shmget(key_t key, size_t size, int shmflg);`
- create a shared memory segment
- `key`: either a unique identifier (e.g. returned by `ftok`) if the segment should be accessed by other processes using this specific `key`, or `IPC_PRIVATE` to ignore `key` and just create the segment (note: in this case returned `shmid` has to be communicated to other process through another form of inter-process communication)
- returns: `shmid` identifier of shared memory segment associated with the value of the argument `key`

`int shmat(int shmid, const void* addr, int flg);`
- attach shared memory segment to address space of the calling process
- `shmid`: identifier (previously return by `shmget()`)

`int shmdt (const void* shmaddr);`
- detach calling process' address space from shared memory segment

## Signals or Alerts (Through the Kernel)
- a very small payload - an integer message
- a fixed set of available operating system-defined signals
	- e.g. 9: `SIGKILL`, 11: `SIGSEGV`, etc.
- registering an operating system signal handler in a process

```c
sighandler_t signal(int signum, sighandler_t handler);
int sigaction(int signum, const struct sigaction* act, struct sigaction* oldact);
```

- send a signal to a process/process group

```c
int kill(pid_t pid, int sig);
int killpg(int pprp, int sig);
```

- note: if pid is positive, then signal sig is sent to the process with the identifier specified by pid. if pid equals $0$, then sig is sent to every process in the process group of the calling process. if pid equals $-1$, then sig is sent to every process for which the calling process has permission to send signals, except for process $1$ (init), but see below
- if pid is less than $-1$, then sig is sent to every process in the process group whose identifier is -pid