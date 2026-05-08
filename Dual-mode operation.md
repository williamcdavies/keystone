---
tags:
  - CS446
---
user mode:
- limited privileges
- only those granted by the [[Operating systems|Operating system]] kernel

kernel mode:
- execution with the full privileges of the hardware
- read/write to any memory, access input/output device, read/write disk, sector, send/read network packets

note:
- on the x86 architecture, the current privilege level (CPL) is a $2$-bit field in the `cs` register. on the MIPS architecture, the status register