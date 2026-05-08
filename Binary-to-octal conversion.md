---
tags:
  - CPE201
---
To convert a number from binary to octal, deconstruct a binary number into 3-bit partitions and replace each partition with the corresponding octal symbol.

```
Convert 1011 1010 to octal.
```

> [!example]
> $$\begin{align}
1011 \quad 1010 &= 0 \quad 1011 \quad 1010 \\\\
&= 010 \quad 111 \quad 010 \\\\
&= 4(0) + 2(1) + 1(0) \quad 4(1) + 2(1) + 1(1) \quad 4(0) + 2(1) + 1(0) \\\\
&= 0 + 2 + 0 \quad 4 + 2 + 1 \quad 0 + 2 + 0 \\\\
&= 2 \quad 7 \quad 2 \\\\
&= 272
\end{align}$$