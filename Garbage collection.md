---
tags:
  - CS326
---
Garbage collection is a form of automatic memory management.

Advantages:
- Prevents [[Dangling references]], which occur when references to heap-dynamic objects aren't resolved before deallocation.
- Prevents [[Memory leaks]], in which a program fails to free memory occupied by heap-dynamic objects that have become unreachable.

Disadvantages
- Automatic garbage collection requires additional run-time overhead.

## Strategies

### Mark-and-Sweep
In the mark-and-sweep method, each object in memory has a flag reserved for garbage collection use only. This flag is always cleared, except during the collection cycle.

The first stage is the *mark stage* which does a tree traversal of the entire root set and marks each object that is pointed to by a root as being 'in-use'. All objects that those objects point to, and so on, are marked as well, so that every object that is reachable via the root set is marked.

In the second stage, the *sweep stage*, all memory is scanned from start to finish, examining all free or used blocks; those not marked as being 'in-use' are not reachable by any roots, and their memory is freed. For objects which were marked in-use, the in-use flag is cleared, preparing for the next cycle.

This method has several disadvantages, the most notable being that the entire system must be suspended during collection; no mutation of the working set can be allowed.

### Stop-and-Copy
In the stop-and-copy method, memory is partitioned into an equally sized "from space" and "to space". Initially, objects are allocated in "to space" until it becomes full and a collection cycle is triggered. At the start of the cycle, the "to space" becomes the "from space", and vice versa. The objects reachable from the root set are copied from the "from space" to the "to space". These objects are scanned in turn, and all objects that they point to are copied into "to space", until all reachable objects have been copied into "to space". Once the program continues execution, new objects are once again allocated in the "to space" until it is once again full and the process is repeated.
