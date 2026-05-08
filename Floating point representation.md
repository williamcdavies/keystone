---
tags:
  - CPE201
---
Floating point numbers are used to concisely represent large numbers in a format that can be easily understood by a computer. Floating point numbers are described by the IEEE-754 standard which defines five internal formats for floating-point numbers.

## Single-precision (4-byte)
keyword: $\text{ float }$
- 23-bit. mantissa
- 8-bit exponent
- 1-bit sign

## Double-precision (8-byte)
keyword: $\text{ double }$
- 52-bit mantissa
- 11-bit exponent
- 1-bit sign

## Half-precision (2-byte)
keyword: - $\text{ N/A }$

## Quadruple-precision (16-byte)
keyword: - $\text{ N/A }$

## Double-extended-precision (10-byte)
keyword: $\text{ long double }$

Floating point numbers follow the format $-1_{10}^S \cdot (1 + M) \cdot (2_{10}^{E - 127})$ where: $S$ represents the sign of the value, $M$, the mantissa, and $E$, the exponent - limited to $255_{10}$ -.

```
Ex.

218.65234375                                 <--- determine input
1101 1010.1010 0111                          <--- convert to binary
1.101 1010 1010 0111 x 2^7                   <--- convert to E notation
0                                            <--- determine sign bit
101 1010 1010 0111 0000 0000                 <--- determine mantissa
101 1010 1010 0111 0000 0000                 <--- append to 23 bits
(7 + 127) = 134 = 1000 0110                  <--- determine exponent
0 | 1000 0110 | 101 1010 1010 0111 0000 0000 <--- concatenate
0100 0011 0101 1010 1010 0111 0000 0000      <--- rearrange

0x 4 3 5 A A 7 0 0                           <--- convert to hexadecimal
0x43 5A A7 00
```