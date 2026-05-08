---
tags:
  - CS302
aliases:
  - List
---
Lists are [[Abstract data types]] that represent a finite number of ordered values, where the same value may occur more than once. A list is said to be empty when it does not contain any elements. The element at (or pointer to) index $0$ is described as the head. The element at (or pointer to) index $N - 1$ is described as the tail.

```cpp
Interface:

#ifndef LIST_INTERFACE
#define LIST_INTERFACE

template <class ItemType>
class ListInterface
{
	public:
		virtual bool isEmpty() const = 0;
		virtual int getLength() const = 0;
		virtual bool insert(int newPosition, const ItemType& newEntry) = 0;
		virtual bool remove(int position) = 0;
		virtual void clear() = 0;
		virtual ItemType getEntry(int position) const = 0;
		virtual ItemType replace(int position, const ItemType& newEntry) = 0;
		virtual ~ListInterface() { }
};

#endif
```
