---
tags:
  - CS302
aliases:
  - Heap
---
Heaps are complete [[Binary trees]] that satisfy the heap property:
- In a max-heap, for any given node $C$, if $P$ is a parent of node $C$, then the key of $P$ is greater than or equal to the key of $C$.
- In a min-heap, for any given node $C$, if $P$ is a parent of node $C$, then the key of $P$ is less than or equal to the key of $C$.

```cpp
Interface:

#ifndef HEAP_INTERFACE
#define HEAP_INTERFACE

template <class ItemType>
class HeapInterface
{
	public:
		virtual bool isEmpty() const = 0;
		virtual getHeight() const = 0;
		virtual getNumberOfNodes() const = 0;
		virtual ItemType peekTop() const = 0;
		virtual bool add(const ItemType& newEntry) = 0;
		virtual bool remove() = 0;
		virtual void clear() = 0;
		virutal ~HeapInterface() { }
};

#endif
```