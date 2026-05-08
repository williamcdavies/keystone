---
tags:
  - CPE201
---
Digital comparators or magnitude comparators are combinational logic circuits that takes two binary numbers as input and determines whether one value is $>$, $<$, or $=$ the other. 

## Implementation 
Consider two 4-bit binary numbers $A$ and $B$ so $A = A_3 A_2 A_1 A_0$ and $B = B_3 B_2 B_1 B_0$

### Equality
The binary numbers $A$ and $B$ will be equal if all significant pairs of both numbers are equal, i.e., $A_3 = B_3$, $A_2 = B_2$, $A_1 = B_1$, and $A_0 = B_0$.

Since the numbers are binary, the boolean function for equality of any two binary digits $A_i$ and $B_i$ can be expressed as $x_i = A_i B_i + A_i' B_i' = (A_i \oplus B_i)'$.

### Inequality
To determine the greater of two binary numbers, all significant pairs of both numbers must be inspected from the most significant to the least significant. As soon as an inequality is found, either $A > B$ or $A < B$ is returned.

This sequential comparison can be expressed logically as: 
$(A > B) = A_3 B_3' + x_3 A_2 B_2' + x_3 x_2 A_1 B_1' + x_3 x_2 x_1 A_0 B_0'$ 
$(A < B) = A_3' B_3 + x_3 A_2' B_2 + x_3 x_2 A_1' B_1 + x_3 x_2 x_1 A_0' B_0$