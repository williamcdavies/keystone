---
tags:
  - CPE201
---
Grey code is an unweighted and non-arithmetic code that exhibits only a single bit change from one code word to the next in sequence.

| $\text{ Decimal }$ | $\text{ Binary }$ | $\text{ Grey Code }$ |
|:------------------:|:-----------------:|:--------------------:|
|         00         |       0000        |         0000         |
|         01         |       0001        |         0001         |
|         02         |       0010        |         0011         |
|         03         |       0011        |         0010         |
|         04         |       0100        |         0110         |
|         05         |       0101        |         0111         |
|         06         |       0110        |         0101         |
|         07         |       0111        |         0100         |
|         08         |       1000        |         1100         |
|         09         |       1001        |         1101         |
|         10         |       1010        |         1111         |
|         11         |       1011        |         1110         |
|         12         |       1100        |         1010         |
|         13         |       1101        |         1011         |
|         14         |       1110        |         1001         |
|         15         |       1111        |         1000         |

To convert from binary code to grey code:
1. If there are an even number of bits in the binary number, append a $0$ to the left of the MSB.
2. From right-to-left, determine the $\oplus$ value for each pair of digits to construct the series of bits that represent the grey code representation of the binary number.