---
tags:
  - CS202
---
Ad hoc polymorphism is a class of [[Polymorphism]] in which polymorphic functions can be applied to arguments of different types. When applied to object-oriented or procedural concepts, ad hoc polymorphism is also known as function overloading or operator overloading. 

```cpp
Ex.

int sum(int x, int y)
{
	int c = x + y;
	
	return c;
}

std::string sum(char* x, char* y)
{
	std::string c = x + y
	
	return c;
}
```