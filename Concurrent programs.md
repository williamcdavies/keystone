---
tags:
  - CS446
---
recall simple web server example
- using `fork()` to make copies of itself that each of them would handle some request
- multiple requests can be handled "simultaneously"

to execute these programs we need to:
- create several processes that execute "concurrently"
- have each of them map to the same [[Address spaces|Address space]] to share data
	- they can all be thought of as a group, part of the same "computational unit"
- have the [[Operating systems|Operating system]] schedule these processes to run simultaneously (logically or physically)

this is inefficient:
- space: PCB, page tables, etc.
- time: create data structures, `fork()` and copy virtual address space, etc.

