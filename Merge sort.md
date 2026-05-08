---
tags:
  - CS477
---
Merge sort is a sorting algorithm that works by dividing an unsorted list into $n$ sublists, each containing one element and repeatedly merging sublists until there is only one sublist remaining. This will be the sorted list. Merge sort has a worst-case complexity of $O(n \log{n} )$.

```
MERGE-SORT(A, p, r):
	if p < r
		then q < (p + r) >> 1
			MERGE-SORT(A, p, q)
			MERGE-SORT(A, q +. 1, r)
			MERGE(A, p, q, r)

MERGE(A, p, q, r):
	compute n1 and n2
	copy the first n1 elements into L[1 ... n1 + 1] and the next n2 elements into R[1 ... n2 + 1]
	L[n1 + 1] <- infty
	R[n2 + 1] <- infty
	i <- 1
	j <1 1
	for k <- p to r
		do if L[i] <= R[j]
			then A[k] <- L[i]
				i <- i + 1
			else A[k] <- R[j]
				j <- j + 1
```