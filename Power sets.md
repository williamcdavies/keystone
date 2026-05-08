---
tags:
  - CS365
aliases:
  - Power set
---
The set of all subsets of a set $S$ is called the power set of $S$ and is denoted by $2^S$.

> [!example]
If $S$ is the set $\{ a, b, c \}$, then its power set is
$$2^S = \{ \emptyset , \{ a \} , \{ b \} , \{ c \} , \{ a, b \} , \{ b, c \} , \{ a, c \} , \{ a, b, c \} \}$$
>
Here $\text{ | } S \text{ | } = 3$ and $\text{ | } 2^S \text{ | } = 8$. This is an instance of a general result; if $S$ is finite, then
$$\text{ | } 2^S \text{ | } = 2^{ \text{ | } S \text{ | } }$$

The power set of any denumerable set is not denumerable ([[Cantor's theorem]]).

---
## References
Discrete Mathematics and Its Applications Sec. 2.1.5 - Kenneth H. Rosen
> "Given a set $S$, the *power set* of $S$ is the set of all subsets of the set $S$. The power set of $S$ is denoted by $\mathcal{P}(S)$."