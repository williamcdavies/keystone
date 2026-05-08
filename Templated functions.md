---
tags:
  - CS202
aliases:
  - Generic functions
---
Since [[Generic programming is built upon the concept of parametric polymorphism]], templated functions are used to design generic programs. They are written identically to explicit functions with a few key exceptions. All templated functions must be identified with the $\text{ template }$ keyword and a typename. The typename of a templated function serves as a placeholder data type until a specific data type is passed during run-time.

```cpp
Ex.

#include "Stats.h"
template<class T>
Stats<T>::Stats()
{
	currentSize = 0;
}

template<class T>
Stats<T>::Stats(T* array, int currentSize)
{
	this->currentSize = currentSize;
	for(int i = 0; i < this->currentSize; i++)
	{
		this->array[i] = array[i];	
	}
}

template<class T>
Stats<T>::Stats(const Stats<T>& c)
{
	currentSize = c.currentSize;
	for(int i = 0; i < currentSize; i++)
	{
		array[i] = c.array[i];	
	}
}

template<class T>
T Stats<T>::min()
{
	T min = array[0];
	for(int i = 1; i < currentSize; i++)
	{
		if(min > arr[i])
		{
			min = arr[i];
		}
	}
	
	return min;
}

template<class T>
T Stats<T>::max()
{
	T max = array[0];
	for(int i; i < currentSize; i++)
	{
		if(max < array[i])
		{
			max = array[i];
		}
	}
	
	return max;
}

template<class T>
T Stats<T>::median()
{
	bubblesort(array);
	T median;
	if(currentSize % 2 == 0){
		median = (array[currentSize / 2] + array[(currentSize / 2)+1]) / 2
	} else 
	{
		median = array[currentSize / 2];
	}
	
	return median;
}

template<class T>
T* Stats<T>::getArray()
{
	return array;
}

template<class T>
void Stats<T>::addToArray(const T& element)
{	
	array[currentSize] = element;
	currentSize++;
}
```