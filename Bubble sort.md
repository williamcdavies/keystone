---
tags:
  - CS477
---
Bubble sort is a sorting algorithm that works by repeatedly steps through the input list element by element, comparing the current element with the one after it, swapping their values if needed. These passes through the list are repeated until no swaps have to be performed during a pass, meaning that the list has become fully sorted. Bubble sort has a worst-case complexity of $O(n^2)$.

```
BUBBLE-SORT(A):
	for i <- 1 to length[A]
		do for j <- length[A] downto i + 1
			do if A[j] < A[j - 1]
				then exchange A[j] <=> A[j - 1]
```