---
tags:
  - CS446
---
Modern CPUs may provide more than two privilege levels, called hierarchical protection domains or protection rings:
- x86 supports four levels of privilege:
	- bottom $2$ bits (CPL) of the `cs` register indicate execution privilege
	- ring $0$ (CPL$=00$) is kernel mode, ring $3$ (CPL$=11$) is user mode
- multics provides eight levels of privilege
- ARMv7 CPUs have eight levels of privilege

why?
- protect [[Operating systems|Operating system]] form itself
	- software-induced vulnerabilities
- reserved for specific operating system vendors
	- e.g. virtualisation, where actual ring $0$ calls are made through a hypervisor that performs them on behalf of a virtual machine guest operating system

