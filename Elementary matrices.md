---
tags:
  - MATH330
---
Elementary matrices are matrices which differ from the identity matrix by a single [[Elementary row operations|Elementary row operation]].

```
Elementary row operations can expressed as the matrix product EA where E is an elementary matrix.
```

> [!example]
> $$\begin{align}
EA &= \begin{pmatrix} 1 & 0 & 0 \\ 0 & 4 & 0 \\ 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} a & b & c \\ d & e & f \\ g & h& i \end{pmatrix} = \begin{pmatrix} a & b & c \\ 4d & 4e & 4f \\ g & h& i \end{pmatrix} \\\\
EA &= \begin{pmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ 1 & 0 & 0 \end{pmatrix} \begin{pmatrix} a & b & c \\ d & e & f \\ g & h & i \end{pmatrix} = \begin{pmatrix} g & h & i \\ d & e & f \\ a & b & c \end{pmatrix} \\\\
EA &= \begin{pmatrix} 1 & 0 & 0 \\ 2 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} a & b & c \\ d & e & f \\ g & h & i \end{pmatrix} = \begin{pmatrix} a & b & c \\ 2a + d & 2b + e & 2c + f \\ g & h & i \end{pmatrix}
\end{align}$$