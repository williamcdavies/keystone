---
tags:
  - CS658
---
Youden's J statistic is a single statistic that captures the performance of a dichotomous diagnostic test.

## Definition
Youden's J statistic is
$$J = \text{ TPR } - \text{ FPR } = \frac{ \text{ TP } }{ \text{ TP } + \text{ FN } } - \frac{ \text{ FP } }{ \text{ FP } + \text{ TN } }$$

Youden's J statistic is often used in conjunction [[Receiver operating characteristic (ROC)]] analysis. The index is defined for all points of an ROC curve, and the maximum value of the index may be used as a criterion for selecting the optimum cut-off point when a diagnostic test gives a numeric rather than a dichotomous result. The index is represented graphically as the height above the chance line, and it is also equivalent to the area under the curve subtended by a single operating point. Because the ROC curve almost always forms a convex curve, the line of this maximum statistic value is likely to intersect the ROC curve at the point where the ROC curve is closest to the point in the top left corner (i.e. the point closest to no false positive or false negative results).