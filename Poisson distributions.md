---
tags:
  - STAT352
---
The Poisson distribution is the discrete probability distribution of a specific number of independent events occurring over a fixed time interval given an average occurrence rate.

If $X$ is a Poisson-distributed [[Discrete random variables|Discrete random variable]], then the expected value of $X$ is written $E[X] = \lambda$. Similarly, the variance of $X$ is written $V[X] = \lambda$.

## Probability Mass Function
The probability of observing exactly $k$ events over an interval given an average occurrence rate $\lambda$ is given by the [[Probability mass functions|Probability mass function]]
$$f(k; \lambda) = \frac{ \lambda^k e^{ -\lambda }}{k!}$$