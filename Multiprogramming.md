---
tags:
  - CS446
---
Modern [[Operating systems]] run multiple [[Processes]] concurrently.
- multiple processes loaded in memory and available to run
- if a process is blocked in input/output, select another process to run on CPU
- different hardware components utilised by different tasks at the same time

example:
- `gcc file_A.c` - compiler running on file $A$
- `gcc file_B.c` - compiler running on file $B$
- `vim` - text editor
- `firefox` - web browser

note:
- multiple `firefox` windows:
	- implemented as a single process

advantages: 
- increase utilisation and overall speed
	- higher throughput, lower latency
- multiple processes can increase CPU utilisation
	- overlap one process' computation with another's wait
