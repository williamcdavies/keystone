---
tags:
  - CS202
---
Dynamic memory allocation is a type of [[Memory allocation]] that refers to the process of assigning memory space during run-time. Unlike [[Static memory allocation]], which allocates memory only once, dynamic memory can be re-allocated when it is no longer needed.

c++ uses the following keywords for dynamic memory allocation
* the $\text{ new }$ keyword allocates memory to the heap

```cpp
int* array = new int[1]; // must allocate at least one address to an array
```

* the $\text{ delete }$ keyword frees memory from the heap

```cpp
delete [] array; // deletion prevents memory leaks
```

When memory is dynamically allocated for objects, destructors must be used to free memory when the object leaves scope. The $\text{ delete }$ keyword is not compatible with objects.