---
tags:
  - MATH182
---
The Taylor series or Taylor expansion of a function is a polynomial represented by an [[Series|Infinite series]] of terms that are expressed in terms of the function's derivatives centred at a single point. For most common functions, the Taylor series and the function are equal near this point. A Taylor series is also called a [[Maclaurin series]] when $0$ is the point where the derivatives are considered.

The partial sum formed by the first $n + 1$ terms of a Taylor series is a polynomial of degree $n$ that is called the *n*th Taylor polynomial of the function. Taylor polynomials are approximations of a function which become more accurate as $n$ approaches infinity.

## Definition
The Taylor series of a real or complex-valued function $f(x)$, which is infinitely differentiable at a real or complex number $a$, is the [[Power series]]
$$f(a) + \frac{f'(a)}{1!} (x - a) + \frac{f''(a)}{2!} (x - a)^2 + \frac{f'''(a)}{3!} (x - a)^2 + \dots = \sum_{n = 0}^{ \infty }{ \frac{f^{(n)}(a)}{n!} (x - a)^n }$$

---
## References
[Taylor series | Chapter 11, Essence of calculus](https://www.youtube.com/watch?v=3d6DsjIBzJ4)
> "The study of Taylor series is largely about taking non-polynomial functions and finding polynomials that approximate them near some input. The motive here is that polynomials tend to be much easier to deal with than other functions."

> "When you take $n$ successive derivatives of the function $x^n$, letting the power rule keep cascading on down, what you'll be left with is $1$ times $2$ times $3$ on and on up to whatever $n$ is."