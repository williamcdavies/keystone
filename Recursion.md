---
tags:
  - CS302
---
Recursion is a method of solving a computational problem where the solution depends on solutions to smaller instances of the same problem. Recursion solves such recursive problems by using functions that call themselves within their own function definition.

Calling a function from within itself, however, may cause the call stack to have a size equal to the sum of the input sizes for all involved calls. Therefore, for problems that can be solved by iteration, recursion is less efficient.

A recursive function definition has one or more base case, of which will allow the functions to terminate up the call stack, preventing infinite recursion.

```cpp
Ex.

int factorial(int n)
{
	if(n == 1) 
	// Base case
	{
		return 1;
	}

	return n * factorial(n - 1)
	// Recursive call
}
```

```cpp
Ex.

int pow(int b, int n)
{
	if(n == 1)
	// Base case
	{
		return b;
	}

	return b * pow(b, n - 1);
	// Recursive call
}
```

