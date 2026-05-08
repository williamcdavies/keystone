---
tags:
  - CS202
---
Passing by pointer/address refers to a method of [[Memory allocation]] where the address of an argument in a calling function is passed as a parameter to the called function. However, unlike [[Passing by reference]], anything passed by pointer needs to be dereferenced from the memory address before the data held at that memory address can be accessed.

```cpp
Ex.

int main()
{
	function(int* variable);
}
```