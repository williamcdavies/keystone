---
tags:
  - CS477
---
Selection sort is a sorting algorithm that works by dividing an input list into two parts: a sorted sublist of items which is built up from left to right at the front of the list and a sublist of the remaining unsorted items that occupy the rest of the list. The algorithm proceeds by finding the smallest element in the unsorted sublist, exchanging it with the leftmost unsorted element, and moving the sublist boundaries one element to the right. Selection sort has a worst-case complexity of $O(n^2)$.

```
SELECTION-SORT(A):
	n <- length[A]
	for j <- 1 to n - 1
		do smallest <- j
			for i <- j + 1 to n
				do if A[i] < A[smallest]
					then smallest <- i
			exchange A[j] <=> A[smallest]
```