---
tags:
  - CS446
---
In Unix-like computer [[Operating systems]], a pipeline is a mechanism for [[Inter-process communication]] using message passing. A pipeline is a set of [[Processes|Process]] chained together by their standard streams, so that the output text of each process is passed directly as input to the next one. The second process is started as the first process is still executing, and they are executed concurrently.

## UNIX PIPE
creates a one-way communication channel
`int pipe(int fds[2])`
- `fds[2]` is used to return two [[File descriptors]]
	- bytes written to `fds[1]` (write end of pipe) will be read from `fds[0]` (read end of pipe)

how can one process (e.g. reader) know of another process' (e.g. writer) setting-up of a pipe connection?
- `fork()` process creation mechanism"

```c
int pipefd[2];
pipe(pipefd);
switch(pid = fork()) {
	case -1: 
		perror("fork error");
		exit(1);
	case 0:
		close(pipefd[0]); // child process
		// write to pipefd[1]
		break;
	default:
		close(pipefd[1]); // parent process
		// read from pipefd[0]
		break;
}
```