---
tags:
  - CPE201
---
## Binary Addition
There are four cases that can occur when two signed binary numbers are added.
1. Both numbers are positive
2. The positive number has a magnitude larger than the negative number
3. The negative number has a magnitude larger than the positive number
4. Both numbers are negative

## Binary Multiplication
The basic steps in the partial products method are:
1. Determine if the signs of the multiplicand and multiplier are the same or different. This determines what the sign of the product will be.
2. Change any negative number to true form. Since most computers store negative numbers using the [[Two's complement]], a two's complement operation is required to get the negative number into true form.
3. Starting with the least significant multiplier bit, generate the partial products. When the multiplier bit is $1$, the partial product is the same as the multiplicand. When the multiplier bit is $0$, the partial product is $0$. Shift each successive partial product one bit to the left.
4. Add each successive partial product to the sum of the previous partial products to get the final product.
5. If the sign bit that was determined in step 1, is $< 0$, take the two's complement of the product. If it is $> 0$, leave the product in true from. Attach the sign bit to the product.

## Binary Division
The basic steps in the division process are:
1. Determine if the signs of the dividend and divisor are the same or different. This determines what the sign of the quotient will be. Initialise the quotient to $0$.
2. Subtract the divisor from the dividend using two's complement addition to get the first partial remainder and add $1$ to the quotient. If this partial remainder is positive, go to step 3. If the partial remainder is $0$ or $< 0$, the division is complete.
3. Subtract the divisor from the partial remainder and add $1$ to the quotient. If the result is $0$ or $< 0$, the division is complete.