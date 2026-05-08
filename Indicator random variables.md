---
tags:
  - CS477
---
An indicator random variable is the simplest kind of parametric [[Random variables|Random variable]]. It can take on two values, $1$ and $0$. It takes on a $1$ if an experiment with probability $p$ resulted in success and a $0$ otherwise. 

## Probability Mass function
The [[Probability mass functions|Probability mass function]] of an indicator random variable is
$$P(X = x) = 
\begin{cases} 
p \quad &\text{ if } x = 1 \\ 
1 - p \quad &\text{ if } x = 0
\end{cases}$$

## Expected Value
The [[Expected values|Expected value]] of an indicator random variable is
$$E[X] = p$$