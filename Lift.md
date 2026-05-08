---
tags:
  - CS658
---
Lift is a measure of the performance of a targeting mode (association rule) at predicting or classifying cases as having an enhanced response (with respect to the population as a whole), measured against a random choice targeting model. A targeting model is doing a good job if the response within the target ($T$) is much better than the baseline ($B$) average for the population as a whole. Lift is simply the ratio of these values: target response divided by average response. Mathematically,
$$\text{ lift } = \frac{P(T \text{ | } B)}{P(T)} = \frac{P(T \land B)}{P(T)P(B)}$$

For example, suppose a population has an average response rate of 5%, but a certain model (or rule) has identified a segment with a response rate of 20%. Then that segment would have a lift of 4.0 (20%/5%).