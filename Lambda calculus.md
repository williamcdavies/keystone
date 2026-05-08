---
tags:
  - CS326
---
Lambda calculus is a formal system in mathematic logic for expressing computation based on function abstraction and application using variable binding and substitution.

Lambda calculus consists of construction lambda terms and performing reduction operations on them. In the simplest form of lambda calculus, terms are built using only the following rules:
1. $x$: A variable is a character or string representing a parameter
2. ($\lambda x. M$): A lambda abstraction is a function definition, taking as input the bound variable $x$ and returning the body $M$.
3. ($M N$): An application, applying a function $M$ to an argument $N$. Both $M$ and $N$ are lambda terms.