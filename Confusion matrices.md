---
tags:
  - CS658
---
A confusion matrix is a specific table layout that allows visualisation of the performance of an algorithm, typically a [[Supervised learning]].

Each row of the matrix represents the instances in an actual class while each column represents the instances in a predicated class, or vice versa. The diagonal of the matrix therefore represents all instances that are correctly predicted.

| ~                | Predicted condition        | -                     | -                     |
|:---------------- |:-------------------------- |:--------------------- |:--------------------- |
| Actual condition | Total population $= P + N$ | Positive ($PP$)       | Negative ($NN$)       |
| -                | Positive ($P$)             | True positive ($TP$)  | False negative ($FN$) |
| -                | Negative ($N$)             | False positive ($FP$) | True negative ($TN$)  |
