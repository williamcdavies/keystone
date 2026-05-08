---
tags:
  - CPE201
---
Binary-coded decimal (BCD) is a class of decimal-to-binary encoding where each digit is represented by a fixed number of bits.

## Natural BCD
Natural BCD is a class of binary-coded decimal and is the most intuitive way to encode digits. Natural BCD is also called "8421" BCD, where the designation "8421" indicates the binary weights of the first four bits. 

Addition using Natural BCD is performed with the following:
1. Add two BCD numbers, using the rules for [[Binary addition]]
2. If $\sum_{ \text{ 4-bit } } \leq 9_{10}$, it is a valid
3. If $\sum_{ \text{ 4-bit } } > 9_{10}$, it is invalid 
4. If $\sum_{ \text{ 4-bit } }$ generates a carry bit, it is invalid
5. If $\sum_{ \text{ 4-bit } }$ is invalid, add $6_{10}$ to $\sum_{ \text{ 4-bit } }$ to skip the six invalid states $( \text{ A } - \text{ F } )$ and return to the ten valid states $(0 - 9)$. If a carry bit is generated when $6_{10}$ is added, add the carry to the next 4-bit group.

---
## References
Digital Fundamentals Sec. 2.10 - Thomas L. Floyd
> "BCD is sometimes used for arithmetic operations in processors. To represent BCD numbers in a processor, they usually are “packed,” so that eight bits have two BCD digits. Normally, a processor will add numbers as if they were straight binary. Special instructions are available for computer programmers to correct the results when BCD numbers are added or subtracted. For example, in Assembly Language, the programmer will include a DAA (Decimal Adjust for Addition) instruction to automatically correct the answer to BCD following an addition."