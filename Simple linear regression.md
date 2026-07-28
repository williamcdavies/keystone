---
tags:
  - STAT352
---
Simple linear regression is a linear regression model that concerns two-dimensional sample points with one independent variable and one dependent variable and finds a linear function that, as accurately as possible, predicts the dependent variable values as a function of the independent variable.

Under simple linear regression, the relationship between the independent $x_i$ and the dependent variable $y_i$ is described by the line
$$y_i = \alpha + \beta x_i + \epsilon_i$$

with $\epsilon_i$ serving as an error term approximated by a [[Normal distributions|Normal distribution]].

To find the line which best approximates $y_i = \alpha + \beta x_i + \epsilon_i$, estimates for $\alpha$ and $\beta$ must be found which best minimise $\epsilon_i$. These estimates, denoted $\widehat{ \alpha }$ and $\widehat{ \beta }$ respectively, are given by the following equations:
$$\widehat{ \alpha } = \overline{y} - ( \widehat{ \beta } \overline{x} )$$
$$\widehat{ \beta } = \frac{S_{xy}}{S_{xx}} = \frac{ \sum{(x_i - \overline{x} )(y_i - \overline{y} )} }{ \sum{(x_i - \overline{x} )^2} } = \frac{ \sum{x_iy_i} - \frac{ \sum{x_i} \sum{y_i} }{n} }{ \sum{x_i^2} - \frac{ \sum{x_i}^2 }{n} }$$

An estimate for the variance of $\epsilon_i$, denoted $\widehat{ \sigma^2 }$, is given by the following equation:
$$\widehat{ \sigma^2 } = \frac{SS_E}{n - 2} = \frac{SS_T - \widehat{ \beta } S_{xy}}{n - 2} = \frac{ \sum{y_i^2} - n \overline{y}^2 - \widehat{ \beta } S_{xy}}{n - 2}$$