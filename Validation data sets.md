---
tags:
  - CS658
---
A validation data set is a data set of examples used to tune the architecture of a model.

In order to avoid [[Overfitting]], when any classification parameter needs to be adjusted, ti is necessary to have a validation data set in addition to the training and test data sets. For example, if the most suitable classifier for the problem is sought, the training set is used to train the difference candidate classifiers, the validation data set is used to compare their performance and decide which one to take and, finally, the test data set is used to obtain the performance.