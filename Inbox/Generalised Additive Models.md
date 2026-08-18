---
tags:
---
A generalised additive model (GAM) is a [[Generalised linear models|Generalised linear model]] in which the linear response variable depends linearly on unknown smooth functions of some predictor variables.

GAMs were developed to blend properties of generalised linear models with additive models. They can be interpreted as the discriminative generalisation of the naive Bayes generative model.

The model relates a univariate response variable, $Y$, to some predictor variables, $x_i$. An exponential family distribution is specified for $Y$ (for example, [[Normal distributions]], [[Binomial distributions]], or [[Poisson distributions]]) along with a [[Link functions|Link function]] $g$ (for example the identity or log functions) relating the expected value of $Y$ to the predictor variables via a structure such as
$$g(E(Y)) = \beta_0 + f_1(x_1) + f_2(x_2) + \cdots + f_m(x_m)$$

The functions $f_i$ may be functions with a specified parametric form (for example a polynomial, or an un-penalised regression spline of a variable) or may be specified parametrically, or semi-parametrically, simply as 'smooth functions', to be estimated by non-parametric means. So a typical GAM might use a scatterplot smoothing function, such as a locally weighted mean, for $f_1(x_1)$ and then use a factor model for $f_2(x_2)$. This flexibility to allow non-parametric fits with relaxed assumptions on the actual relationship between response and predictor, provides the potential for better fits to data than purely parametric models, but arguably with some loss of interpretability.