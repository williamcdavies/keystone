---
tags:
  - CS365
---
Modular Arithmetic is a system of arithmetic for integers where numbers "wrap around" when reaching a certain value, called the modulus. The modulus operator is written $\bmod$.

There are two notations for which the modulus operator is used. The first represents the remainder when an integer $a$ is divided by the positive integer $m$: $a \bmod m$. The second indicates that two integers have the same remainder when they are divided by the positive integer $m$. $a \bmod m = b \bmod m$.

---
## References
Discrete Mathematics and Its Applications Sec. 4.1.4 - Kenneth H. Rosen
> "If $a$ and $b$ are integers and $m$ is a positive integer, then $a$ is *congruent to* $b$ *modulo* $m$ if $m$ divides $a - b$. We use the notation $a \equiv b \pmod{m}$ to indicate that $a$ is congruent to $b$ modulo $m$. We say that $a \equiv b \pmod{m}$ is a congruence and that $m$ is its **modulus** (plural **moduli**). If $a$ and$ $b$ are not congruent modulo $m$, we write a $\not\equiv b \pmod{m}$."

>"Let $m$ be a positive integer and let $a$ and $b$ be integers. Then $(a + b) \bmod m = ((a \bmod m) + (b \bmod m)) \bmod m$ and $ab \bmod m = ((a \bmod m)(b \bmod m)) \bmod m$."