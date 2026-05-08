---
tags:
  - CPE201
---
The karnaugh map provides a systematic method for simplifying boolean expressions to the simplest [[Sum-of-products method]] or [[Product-of-sums method]] expression possible, known as the [[Minimum expression]], by manipulating min-terms ($0$s) and max-terms ($1$s). 

## SOP Simplification:

```
ABC' + AB'C' + A'B' + A'BC
110    100     000    011
               001   

AB / C
---- 0   1
00 | 1 | 1 |
01 |   | 1 |
11 | 1 |   |
10 | 1 |   |

A'B' + A'C + AC'
```

## POS Simplification:

```
(A + B + C')(A + B' + C')(A' + B')(A' + B + C)
 001         011          110      100
                          111

AB / C
---- 0   1
00 |   | 0 |
01 |   | 0 |
11 | 0 | 0 |
10 | 0 |   |

(A' + C)(A' + B')(A + C)
```

The number of cells in a Karnaugh map is equal to the number of total possible input variable combinations. 

Cells in a Karnaugh map are arranged so there is only a single-variable change between adjacent cells (The cells in column $0$ are adjacent to the cells in column $n - 1$ and cells in row $0$ are adjacent to the cells in row $n - 1$).

Since $> 3$ dimensions are required to perform logic simplification on a Karnaugh map with $> 5$ variables, when dealing with such quantities, the [[Quine-McCluskey method]] becomes more practical for logic simplification.