---
tags:
  - CS658
---
Some data analysis algorithms require categorical input data instead of numeric input data. In this case, the data must be preprocessed through a discretisation step in which numeric values are mapped to discrete values. Moments are quantities that describe some aspects of continuous attribute distributions. Of particular interest are central moments or moments around the mean.

Discretisation algorithms are divided in the following categories:

## Unsupervised Discretisation
The target concept or class attribute is not used for setting the interval bounds. Typically, unsupervised algorithms are applied when discretisation is done without the intention of later using the data for classification, or when different classification tasks can be considered for the same data set. Here, different attributes are used as the target concept.

## Supervised Discretisation
The target concept or class attribute is used for setting the most appropriate interval bounds. Conceptually and computationally more complex than unsupervised algorithms.