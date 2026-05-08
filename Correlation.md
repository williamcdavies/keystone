---
tags:
  - CS658
---
The population correlation coefficient $\rho_{X, Y}$ between two [[Random variables]] $X$ and $Y$ with [[Expected values]] $\mu_X$ and $\mu_Y$ and standard deviations $\sum_X$ and $\sum_Y$ is defined as:
$$\begin{align}
\rho_{X, Y} &= \text{ corr } (X, Y) \\ \space \\
&= \frac{\text{ cov } (X, Y)}{ \sum_X \sum_Y } \\ \space \\
&= \frac{E[(X - \mu_X )(Y - \mu_Y )]}{ \sum_X \sum_Y }
\end{align}$$

where 
- $E$ is the expected value operator
- $$\text{ cov } (x, y) = s_{xy} = \frac{1}{n - 1} \sum_{k = 1}^n{(x_k - \overline{x} )(y_k - \overline{y} )}$$
- $$\sum_x = s_x = \sqrt{ \frac{1}{n - 1} \sum_{k = 1}^n{(x_k - \overline{x} )^2} }$$
- $$\sum_y = s_y = \sqrt{ \frac{1}{n - 1} \sum_{k = 1}^n{(y_k - \overline{y} )^2} }$$
- $$\overline{x} = \frac{1}{n} \sum_{k = 1}^n{x_k}$$
- $$\overline{y} = \frac{1}{n} \sum_{k = 1}^n{y_k}$$