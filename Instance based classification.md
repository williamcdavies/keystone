---
tags:
  - CS658
---
Basic Idea of Instance-Based Classification:
- Store the training records
- Use training records to predict the class label of unseen cases

## Nearest-Neighbour Classifier
Nearest-Neighbour Classifier requires three things:
1. The set of stored records

Scaling issues: Attributes may have to be scaled to prevent distance measures from being dominated by one of the attributes

2. Distance Metric to compute distance between records

Problem with Euclidean measure: High dimensional data may encounter [[Curse of dimensionality]]. To solve this problem, we can produce counter-intuitive results by normalising the vectors to unit length.

3. The value of k, the number of nearest neighbours to retrieve
- If $k$ is too small, sensitive to noise points
- If $k$ is too large, neighbourhood may include points from other classes

With the above three things, Nearest-Neighbour Classifier classifies an unknown record following the below steps:
1. Compute distance between the unknown record and other training records
2. Identify $k$ nearest neighbours
3. Use class labels of nearest neighbours to determine the class label of unknown record
    - by taking majority vote
    - by weighting the vote according to distance $w = \frac{1}{d^2}$

Unlike eager learners such as decision tree induction and [[Rule based classification]] systems, $k$-NN classifiers does not build models explicitly. As a result, classifying unknown records are relatively expensive.

## PEBLS: Parallel Examplar-Based Learning System
PEBLS (Parallel Exemplar-Based Learning System) is a nearest-neighbour learning system ($k = 1$) designed for applications where the instances have symbolic feature values. PEBLS has been applied to the prediction of protein secondary structure and to the identification of DNA promoter sequences.

### Distance Between Nominal Attribute Values
For nominal features, distance between two nominal values is computed using modified value difference metric (MVDM)
$$d(V_1, V_2) = \sum_i{ \left| \frac{n_{1_i}}{n_1} - \frac{n_{2_i}}{n_2} \right|}$$

Where $n_1$ is the number of records that consists of nominal attribute value $V_1$ and $n_{1_i}$ is the number of records whose target label is class $i$.

### Distance Between Records
$$\delta{(X, Y)} = w_Xw_Y \sum_{i = 1}^d{d(X_i, Y_i)}$$

Each record $X$ is assigned a weight factor $w_X$ , which represents the reliability of the certain record.
$$w_x = \frac{N_{X_{ \text{ predict } }}}{N_{X_{ \text{ correct predict } }}}$$

where $N_{X_{ \text{ predict } }}$ is the number of times $X$ is used for prediction and $$N_{X_{ \text{ correct predict } }}$$ is the number of times the prediction using $X$ is correct.

We can see that if $w_X > 1$, then $X$ is not reliable for making predictions. High $w_X > 1$ would result in high distance, which makes it less possible to use $X$ to make predictions.