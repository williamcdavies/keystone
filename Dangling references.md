---
tags:
  - CS326
---
Dangling references are references that do not resolve to a valid destination.

## Detecting dangling references

### Tombstones
A tombstone is a structure that acts as an intermediary between a pointer and its target, often heap-dynamic data in memory. The pointer points only at the tombstone and never to its actual target. When the data is deallocated, the tombstone is set to a null, indicating that the variable no longer exists.

### Locks & Keys
The locks-and-keys approach represents pointers as ordered pairs (key, address) where the key is an integer value. Heap-dynamic variables are represented as the storage for the variable plus a cell for an integer lock value. When a variable is allocated, a lock value is created and placed both into the variable's cell and into the pointer's key cell. Every access to the pointer compares these two values, and access is allowed only if the values match.

When a variable is deallocated, the key of its pointer is modified to hold a value different from the variable's cell. From then on, any attempt to dereference the point can be flagged as an error. Since copying a pointer also copies its cell value, changing the key of the ordered pair safely disables all copies of the pointer.