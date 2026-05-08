---
tags:
  - CS302
aliases:
  - Stack
---
Stacks are [[Abstract data types]] that represent a collection of elements with three main operations; push, pop, and peek. A stack has one end which is the only position at which the push and pop operations may occur, the top of the stack, and is fixed as the other end, the bottom.

```cpp
Interface:

#ifndef STACK_INTERFACE
#define STACK_INTERFACE

template <class ItemType>
class StackInterface
{
	public:
		virtual bool isEmpty() const = 0;
		virtual bool push(const ItemType& newEntry) = 0;
		virtual bool pop() = 0;
		virtual ItemType peek() const = 0;
		virtual ~StackInterface() { }
};

#endif
```

