---
tags:
  - MATH181
---
If a real-valued function $f$ is continuous on a proper closed interval $[a,b]$, differentiable on the open interval $(a,b)$, and $f(a) = f(b)$, then there exists at least on $c$ in the open interval $(a,b)$ such that $f'(c) = 0$.

This version of Rolle's theorem is used to prove the [[Mean value theorem]], of which Rolle's theorem is a special case. It is also the basis for the proof of [[Taylor's theorem]].

### Generalisation
Consider a real-valued function $f$ that is continuous on a proper closed interval $[a,b]$ with $f(a) = f(b)$. If for every $x$ in the open interval $(a,b)$, the right-hand limit 
$$f'(x^+) := \lim_{h \to 0^+} \frac{(x + h) - f(x)}{h}$$

and the left-hand limit
$$f'(x^-) := \lim_{h \to 0^-} \frac{(x + h) - f(x)}{h}$$ 

exist in the extended real line $[-\infty,\infty]$, then there is some number $c$ in the open interval $(a,b)$ such that one of the two limits is $\geq 0$ and the other is $\leq 0$. If the right- and left-handed limits agree for every $x$, then they agree in particular for $c$, hence the derivative of $f$ exists at $c$ and is equal to $0$.

## Proof
If it is assumed that $f$ is continuous on $[a,b]$ and attains its absolute maximum and its absolute minimum at the endpoints $[a,b]$, then the derivative of $f$ is $0$ at every point in $(a,b)$.

Suppose that the absolute maximum is attained at an interior point $c$ of $(a,b)$.

For a real $h$ such that $c + h$ is in $[a,b]$, the value $f(c + h)$ is similar or equal to $f(c)$ since $f$ attains maximum at $c$. Therefore, for every $h > 0$, 
$$f'(x^+) := \lim_{h \to 0^+} \frac{(x + h) - f(x)}{h} \leq 0$$

Similarly, for every $h < 0$, the inequality flips since the denominator becomes negative. Therefore, for every $h < 0$, 
$$f'(x^-) := \lim_{h \to 0^-} \frac{(x + h) - f(x)}{h} \geq 0$$

Therefore, when the above right- and left-hand limits agree, then the derivative of $f$ at $c$ must be $0$.