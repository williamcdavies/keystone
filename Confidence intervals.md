---
tags:
  - STAT352
---
A confidence interval is an interval that is expected to contain a population parameter within a certain level of confidence. 

The confidence level for a confidence interval is defined as $1 - \alpha$, where $\alpha$ is the threshold for statistical significance. In most cases, $\alpha = 0.05$.

## Confidence Interval for the Mean
The confidence interval for the [[Population mean]] is:
$$P_{ \mu }\left( \overline{X} - Z_{ \frac{ \alpha }{2} } \frac{s}{ \sqrt{n} } \leq \mu \leq \overline{X} + Z_{ \frac{ \alpha }{2} } \frac{s}{ \sqrt{n} } \right) = 1 - \alpha$$

where $\mu$ is the population mean, $\overline{X}$ is the sample distribution, $Z_{ \frac{ \alpha }{2} }$ is the critical value for a two-tailed confidence interval, $s$ is the sample standard deviation, $n$ is the sample size, and $\alpha$ is the threshold for statistical significance.

## Confidence Interval for the Variance
The confidence interval for the [[Population variance]] is:
$$P_{ \sigma^2 } \left( \frac{(n - 1)s^2}{ \chi_{ \frac{ \alpha }{2 } , n - 1}^2 } \leq \sigma^2 \leq \frac{(n - 1)s^2}{ \chi_{1 - \frac{ \alpha }{2} , n - 1}^2 } \right) = 1 - \alpha$$

where $\sigma^2$ is the population variance, $s^2$ is the sample variance, $\chi_{ \frac{ \alpha }{2} , n - 1}^2$ is the lower critical value for a two-tailed chi-squared interval, $\chi_{1 - \frac{ \alpha }{2} , n - 1}^2$ is the upper critical value for a two-tailed interval, $n$ is the sample size, and $\alpha$ is the threshold for statistical significance.

## Confidence Interval for the Proportion
The confidence interval for the population proportion is:
$$P_p \left( \widehat{p} - Z_{ \frac{ \alpha }{2} } \sqrt{ \frac{ \widehat{p} (1 - \widehat{p} )}{n} } \leq p \leq \widehat{p} + Z_{ \frac{ \alpha }{2} } \sqrt{ \frac{ \widehat{p} (1 - \widehat{p} )}{n} } \right) = 1 - \alpha$$

where $p$ is the population proportion, $\widehat{p}$ is the sample proportion, $Z_{ \frac{ \alpha }{2} }$ is the critical value for a two-tailed confidence interval, $n$ is the sample deviation, and $\alpha$ is the threshold for statistical significance.

