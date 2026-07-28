---
tags:
  - STAT352
---
A continuity correction is an adjustment made when a [[Discrete random variables|Discrete random variable]] is approximated using a [[Continuous random variables|Continuous random variable]].

## [[Binomial distributions|Binomial distribution]]
If a discrete random variable $X$ has a binomial distribution with parameters $n$ and $p$, then
$$P(X \leq x) = P(X < x + 1)$$

for any $x \in \{ 0, 1, 2, \dots n \}$. If $E[X] = np$ and $V[X] = np(1 -p)$ are sufficiently large, then the probability above is fairly well approximated by
$$P(Y \leq x + \frac{1}{2})$$

where $Y$ is a normally distributed random variable with the same [[Expected values|Expected value]] and the same [[Variance]] as $X$.