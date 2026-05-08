---
tags:
  - CPE201
---
Method 1:
1. Convert a given hexadecimal number to binary
2. Take the [[Two's complement]] of the binary number
3. Convert the result to the new hexadecimal number

Method 2:
1. Subtract the hexadecimal number from the greatest hexadecimal number possible given the quantity of digits
2. Using [[Hexadecimal addition]], add $1$ to the new number

Method 3:
1. Write out the sequence of single hexadecimal digits
2. Write the sequence in reverse below the initial sequence
	1. The [[One's complement]] of each hex digit is the digit directly below it
3. Using hexadecimal addition, add $1$ to the resulting number to get the two's complement