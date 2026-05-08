---
tags:
  - CS456
---
If a language $L$ is a [[Context-free languages|Context-free language]], then there exists some integer $p \geq 1$ (called a "pumping length") such that every string $s$ in $L$ that has a length of $p$ or more symbols (i.e., with $\text{ | } s \text{ | } \geq p$) can be written as
$$s = uvwxy$$

with substrings $u$, $v$, $w$, $x$, and $y$, such that 
1. $\text{ | } vx \text{ | } \geq 1$,
2. $\text{ | } vwx \text{ | } \leq p$, and
3. $uv^nwx^ny \in L \forall n \geq 0$