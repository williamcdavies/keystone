---
tags:
  - CS202
aliases:
  - Generic data types
---
Since [[Generic programming is built upon the concept of parametric polymorphism]], templated [[Classes]] are used as the framework for generic programs. They are written identically to explicit classes with a few key exceptions. All templated classes must be identified with the $\text{ template }$ keyword and a class.

```cpp
Ex.

#ifndef STATS_H
#define STATS_H
template <class T>
class Stats
{
	private:
		T* array = new T[1];
	public:
		Stats();
		Stats(T*)
		Stats(const Stats<T>&);
		T getLow() const;
		T getHigh() const;
		T getMedian() const;
		T* getArray();
		void addToArray(const T&);
};
#include "stats.cpp"
#endif
```