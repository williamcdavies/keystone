---
tags:
  - MATH182
---
Partial fraction decomposition is an operation that consists of expressing a fraction as a sum of a polynomial and one or several fractions with a simpler denominator.

The importance of the partial fraction decomposition lies in the fact that it provides algorithms for various computations with rational functions, including the explicit computation of antiderivatives, [[Taylor series expansions]], inverse [[Z-transforms]], and inverse [[Laplace transforms]].

In symbols, the partial fraction decomposition of a rational fraction of the form $\frac{f(x)}{g(x)}$, where $f$ and $g$ are polynomials, is expressed as 
$$\frac{f(x)}{g(x)} = p(x) + \sum_{j} \frac{f_j(x)}{g_j(x)}$$

where $p(x)$ is a polynomial, and for each $j$, the denominator $g_j(x)$ is a power of an irreducible polynomial, and the numerator $f_j(x)$ is a polynomial of a smaller $\deg$ than the degree of this irreducible polynomial.

## Procedure
Given two polynomials $P(x)$ and $Q(x) = (x - \alpha_1)(x - \alpha_2) \cdot \cdot \cdot (x - a_n)$, where the $a_n$ are distinct constants and degree $P < n$, explicit expressions for partial fractions can be obtained by supposing that 
$$\frac{P(x)}{Q(x)} = \frac{c_1}{x - \alpha_1} + \frac{c_2}{x - \alpha_2} + \cdot \cdot \cdot + \frac{c_n}{x - \alpha_n}$$ 

and supposing for the $c_i$ constants, by substitution, by equating the coefficients of terms involving the powers of $x$, or otherwise.

If $P \geq \deg Q$, then it is necessary to perform the [[Euclidean division]] of $P$ by $Q$, using polynomial long division, giving $P(x) = E(x)Q(x) + R(x)$ with $\deg R < n$. Dividing by $Q(x)$ this gives 
$$\frac{P(x)}{Q(x)} = E(x) + \frac{R(x)}{Q(x)}$$ 

and then seek partial fractions for the remainder fraction (which by definition satisfies $\deg R < \deg Q$).
 
