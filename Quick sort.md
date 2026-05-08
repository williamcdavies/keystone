---
tags:
  - CS477
---
Quick sort is a sorting algorithm that works by selecting a pivot element from an array and partitioning the other elements into two sub-arrays, according to whether they are less than or greater than the pivot. These sub-arrays are then sorted recursively. Quick sort has a worst-case complexity of $O(n^2)$.

```
QUICK-SORT(A, p, r):
	if p < r
		then q <- PARTITION(A, p, r)
			QUICKSORT(A, p, q)
			QUICKSORT(A, q + 1, r)

PARTITION(A, p, r):
	x <- A[p]
	i <- p - 1
	j <- r + 1
	while TRUE
		do repeat j <- j - 1 
				until A[j] <= x
			repeat i <- i + 1 
				until A[i] >= x
			if i < j
				then exchange A[i] <=> A[j]
			else return j
		
```