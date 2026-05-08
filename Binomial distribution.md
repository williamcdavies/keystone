---
tags:
  - STAT352
---
The binomial distribution is the discrete probability distribution of the number of successes in a sequence of $n$ independent [[Bernoulli trials]].

If $X$ is a binomially distributed [[Discrete random variables|Discrete random variable]], then the expected value of $X$ is written $E[X] = np$. Similarly, the variance of $X$ is written $V[X] = np(1 - p)$.

## Probability Mass Function
The probability of observing exactly $k$ successes in $n$ independent Bernoulli trials is given by the [[Probability mass functions|Probability mass function]]
$$f(k, n, p) = \pmatrix{n \\ k} p^k(1 - p)^{n - k}$$

```
The probability that a lab specimen contains high levels of contamination is 0.11. A group of 4 independent samples are checked.

Round your answers to four decimal places (e.g. 0.9876).
```

```
(a) What is the probability that none contain high levels of contamination?
```

> [!example]
> $$\begin{align}
f(0, 4, 0.11) &= \pmatrix{4 \\ 0} 0.11^0(1 - 0.11)^{4 - 0} \\\\
&= 0.89^4 \\\\ 
&= 0.6274
\end{align}$$

```
(b) What is the probability that exactly one contains high levels of contamination?
```

> [!example]
> $$\begin{align}
f(1, 4, 0.11) &= \pmatrix{4 \\ 1} 0.11^1(1 - 0.11)^{4 - 1} \\\\
&= 4 \cdot 0.11 \cdot 0.89^3 \\\\ 
&= 0.3102
\end{align}$$

```
(c) What is the probability that at least one contains high levels of contamination?
```

> [!example]
> $$\begin{align}
1 - f(0, 4, 0.11) &= 1 - 0.6274 \\\\
&= 0.3726
\end{align}$$