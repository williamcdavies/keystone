---
tags:
  - CS658
---
Gini Impurity is a metric used to gauge the degree of probability that a randomly chosen element from the dataset would be classified incorrectly if it were randomly labeled according to the distribution of labels in the subset.

At its core, the Gini Impurity quantifies the level of heterogeneity of a dataset. Consider a dataset where all elements belong to the same class. In such a case, there i no uncertainty; hence the impurity is $0$. Conversely, if the labels are uniformly distributed across classes, the impurity is at its highest because any new sample has an equal chance of belonging to any class. This insight makes Gini Impurity particularly useful for decision tree algorithms that require efficient splitting of nodes.

## Importance in the Context of Decision Trees
Decision tree algorithms, such as CART, depend on splitting decisions at each node to increase the overall homogeneity of subsets. During these splitting operations, a candidate feature threshold is evaluated by computing the resulting impurity on each child node. Gini Impurity is frequently chosen as the splitting criterion because of its computational efficiency and intuitive interpretation. Splits that result in lower impurity values indicate that the data in the child nodes are more homogeneous, which tends to lead to improved classification accuracy.

The algorithm seeks to minimise the weighted sum of the Gini Impurity of the resulting subsets. In this sense, Gini Impurity functions as a guide for the tree construction process. Its rapid computation also makes it more suited for real-time application and large datasets compared to some other measures like [[Entropy (information theory)]].

## Contrast with Other Impurity Measures
While Gini Impurity is a popular choice in many scenarios, it is not the only impurity measure at one's disposal. Entropy, which originates from information theory, is another deeply-rooted metric. The formulation of entropy is derived from the concept of information gain, which quantifies how much uncertainty in the target variable is reduced by knowing the value of a predictor.

A mathematical comparison can be interesting here. While entropy is calculated as
$$\text{ Entropy } (D) = -\sum_{i = 1}^C{p_i \log_2{p_i} }$$

where $p_i$ is the proportion of samples of class $i$, Gini Impurity is computed as
$$\text{ Gini } (D) = 1 - \sum_{i = 1}^C{p_i^2}$$

Both measures favour splits that result in clean, homogeneous leaves. However, Gini Impurity tends to be computationally simpler because it avoids the logarithm operation, making it faster to computer especially in high-dimensional data.

## Step-by-Step Breakdown of the Calculation
1. Determine Class Proportions: For a given node containing a set of samples, calculate the proportion of samples belonging to each class. For a dataset $D$ with $C$ classes, let the proportion of samples in class $i$ be $p_i$. This is simply calculated as: $$p_i = \frac{ \text{ Number of samples in class } i}{ \text{ Total number of samples in } D}$$
2. Square the Proportions: Compute $p_i^2$ for each class. Squaring reinforces the dominance of classes that have higher proportions.
3. Sum the Squared Proportions: Sum all the squared proportions: $$S = \sum_{i = 1}^C{p_i^2}$$
4. Calculate the Impurity: Finally, subtract this sum from one to obtain the Gini Impurity: $$\text{ Gini } (D) = 1 - S = 1 - \sum_{i = 1}^C{p_i^2}$$

This metric effectively measures how often a randomly chosen element would be misclassified if it were labeled according to the distribution in $D$.

## Interpreting the Results in Model SPlits
When building a decision tree, the goal is to split the data such that each resulting node is as pure as possible (i.e., the samples in the node predominantly belong to a single class).  Suppose a particular split divides a node into two child nodes, $D_1$ and $D_2$. The overall impurity after the split can be evaluated using a weighted average:
$$\text{ Gini }_\text{ split } = \frac{N_1}{N} \text{ Gini } (D_1) + \frac{N_2}{N} \text{ Gini } (D_2)$$

where $N_1$ and $N_2$ are the number of samples in $D_1$ and $D_2$, respectively, and $N = N_1 + N_2$. A successful split will have a significantly lower Gini Impurity compared to the unspilt parent node, indicating that the classes are better separated.

For example, consider a split where:
- Parent node Gini Impurity is $0.42$.
- After the split, $D_1$ has $80$ samples with a Gini of $0.25$, and $D_2$ has $20$ samples with a Gini of $0.15$.

The weighted impurity would be calculated as:
$$\text{ Gini }_\text{ split } = \frac{80}{100} (0.25) + \frac{20}{100} (0.15) = 0.20 + 0.03 = 0.23$$

Since $0.23$ is significantly lower that $0.42$, this split is considered effective in increasing the node's purity.