---
tags:
  - CS658
---
In a binary classification task, the terms `positive` and `negative` refer to the classifier’s prediction, and the terms `true` and `false` refer to whether that prediction corresponds to the external judgment (sometimes known as the `observation`). Given these definitions, we can formulate the following table:


| ~                             | Actual class (observation)         | -                                            |
|:----------------------------- |:---------------------------------- |:-------------------------------------------- |
| Predicted class (expectation) | tp (true positive) Correct result  | fp (false positive) Unexpected result        |
| -                             | fn (false negative) Missing result | tn (true negative) Correct absence of result |

In this context, we can define the notions of precision and recall:
$$\begin{align}
\text{ precision } &= \frac{ \text{ tp } }{ \text{ tp } + \text{ fp } } \\ \space \\
\text{ recall } &= \frac{ \text{ tp } }{ \text{ tp } + \text{ fn } } \\ \space \\
\end{align}$$

F-measure is the weighted harmonic mean of precision and recall, with precision's contribution to the mean weighted by some parameter $\beta$:
$$F_\beta = (1 + \beta^2 ) \frac{ \text{ precision } \times \text{ recall } }{ \beta^2 \text{ precision } + \text{ recall } }$$

This formula is undefined when there are no true positives, false positives, or false negative.