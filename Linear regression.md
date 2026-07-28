---
tags:
  - Mathematics
---
Linear regression is a model that estimates the relationship between a scalar response (dependent variable) and one or more explanatory variables (regressor or independent variable). A model with exactly one explanatory variable is a [[Simple linear regression]]; a model with two or more explanatory variables is a multiple linear regression.

## Formulation
Given a data set $\{ y_i, x_{i1}, \dots, x_{ip} \}^n_{i = 1}$ of $n$ [[Statistical units]], a linear regression model assumes that the relationship between the dependent variable $y$ and the vector of regressors $\mathbf{x}$ is linear. This relationship is modelled through a disturbance term or error variable $\epsilon$-an unobserved random variable that adds extra "noise" to the linear relationship between the dependent variable and regressors. Thus the model takes its form
$$y_i = \beta_0 + \beta_1 x_{i1} + \cdots + \beta_p x_{ip} + \epsilon_i = \mathbf{x}_i^T \boldsymbol{ \beta } + \epsilon_i$$

where $^T$ denotes the transpose, so that $\mathbf{x}_i^T \boldsymbol{ \beta }$ is the inner product between vectors $\mathbf{x}_i$ and $\boldsymbol{ \beta }$.

Often these $n$ equations are stacked together and written in matrix notation as $\mathbf{y} = \mathbf{X} \boldsymbol{ \beta } + \boldsymbol{ \epsilon }$.