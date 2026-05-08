---
tags:
  - CS658
---
Information gain is the reduction in [[Entropy (information theory)]] $H$ from a prior state to a state that takes some information as given:
$$\text{ IG } (T, a) = H(T) - H(T \text{ | } a)$$

where $H(T \text{ | } a)$ is the [[Conditional entropy]] of $T$ given the value of attribute $a$.

## Split Information Calculation
The split information value for a test is defined as follows:
$$\text{ SplitInformation } (x) = -\sum_{i = 1}^n{ \frac{N(x_i)}{N(x)} \log{ \frac{N(x_i)}{N(x)} }}$$

where $X$ is a discrete random variable with possible values $x_1, x_2, \dots, x_i$ and $N(x_i)$ being the number of times that $x_i$ occurs divided by the total count of events $N(x)$ where $x$ is the set of events.

The split information value is a positive number that describes the potential worth of splitting a branch from a node. This in turn is the intrinsic value that the random variable possesses and will be used to remove the bias in the information gain ratio calculation.

## Information Gain Ratio Calculation
The information gain ratio is the ratio between the information gain and the split information value:
$$\text{ IGR } (T, a) = \frac{ \text{ IG } (T, a)}{ \text{ SplitInformation } (T)}$$