---
tags:
  - CS302
aliases:
  - Queue
---
Queues are [[Abstract data types]] that represent a collection of entities that are maintained in a sequence and can be modified by the addition of entities at one end and the removal of entities from the other.

```cpp
Interface:

#ifndef QUEUE_INTERFACE
#define QUEUE_INTERFACE

template <class ItemType>
class QueueInterface
{
	public:
		virtual bool isEmpty() const = 0;
		virtual bool enqueue(const ItemType& newEntry) = 0;
		virtual bool dequeue() = 0;
		virtual ItemType peekFront() const = 0;
		virtual ~QueueInterface { }
};

#endif
```