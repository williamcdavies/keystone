---
tags:
  - CS477
---
A Huffman code is a particular type of optimal [[Prefix code]] that is commonly used for lossless data compression.

The output from Huffman's algorithm can be viewed as a variable-length code table for encoding a source symbol. The algorithm derives this table fro the estimated probability or frequency of occurrence for each possible value of the source symbol.

```
Encode {a_1, a_2, a_3, a_4} with respective probabilities {0.4, 0.35, 0.2, 0.05}.
```

> [!example]
A source generates $4$ different symbols $\{ a_1, a_2, a_3, a_4 \}$ with probability $\{ 0.4, 0.35, 0.2, 0,05 \}$. A binary tree is generated from left to right taking the two least probably symbols and putting them together to form another equivalent symbol having a probability that equals the sum of the two symbols. The process is repeated until there is just one symbol. The tree can then be read backwards, from right to left, assigning different bits to different branches. The final Huffman code is:
>
| $\text{ Symbol }$ | $\text{ Code }$ |
|:-----------------:|:---------------:|
|       $a_1$       |       $0$       |
|       $a_2$       |      $10$       |
|       $a_3$       |      $110$      |
|       $a_4$       |      $111$      |