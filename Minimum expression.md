---
tags:
  - CPE201
---
The minimum expression of a boolean function is that which cannot be simplified any further.

## Minimum SOP Expression Using a Karnaugh Map
The steps for determining the minimum SOP expression of a boolean function using [[Karnaugh maps]] are as follows:
1. Determine the [[Sum-of-products method]] for the unsimplified function
2. Input the SOP into the Karnaugh map to determine all cells which equal $1$
3. Group the corresponding cells where a group contains either $1$, $2$, $4$, $8$, or $16$ cells and where each cell in a group is adjacent to $\ge 1$ other cell in that same group.
4. Determine the minimum product term for each group
	1. For a 3-variable map:
		1. A 1-cell group yields a $3$ variable product term
		2. A 2-cell group yields a $2$ variable product term
		3. A 4-cell group yields a $1$ variable product term
		4. An 8-cell group yields a value of $1$ for the expression
	2. For a 4-variable map:
		1. A 1-cell group yields a $4$ variable product term
		2. A 2-cell group yields a $3$ variable product term
		3. A 4-cell group yields a $2$ variable product term
		4. An 8-cell group yields a $1$ variable product term
		5. A 16-cell group yields a value of $1$ for the expression
5. Sum the minimum products for each group to determine the minimum SOP expression

## Minimum POS Expression Using a Karnaugh Map
The steps for determining the minimum POS expression of a boolean function using [[Karnaugh maps]] are as follows:
1. Determine the [[Product-of-sums method]] for the unsimplified function
2. Input the POS into the Karnaugh map, to determine all cells which equal $0$.
3. Group the corresponding cells where a group contains either $1$, $2$, $4$, $8$, or $16$ cells and where each cell in a group is adjacent to $\ge 1$ other cell in that same group.
4. Determine the minimum product term for each group
	1. For a 3-variable map:
		1. A 1-cell group yields a $3$ variable product term
		2. A 2-cell group yields a $2$ variable product term
		3. A 4-cell group yields a $1$ variable product term
		4. An 8-cell group yields a value of $1$ for the expression
	2. For a 4-variable map:
		1. A 1-cell group yields a $4$ variable product term
		2. A 2-cell group yields a $3$ variable product term
		3. A 4-cell group yields a $2$ variable product term
		4. An 8-cell group yields a $1$ variable product term
		5. A 16-cell group yields a value of $1$ for the expression
5. Product the sums products for each group to determine the minimum POS expression