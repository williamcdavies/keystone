---
tags:
  - CS477
---
Bucket sort is a sorting algorithm that works by distributing the elements of an array into a number of buckets. Each bucket is then sorted individually, either using a different sorting algorithm, or by recursively applying the bucket sorting algorithm. Bucket sort has a worst-case complexity of $O(n^2)$.

```
BUCKET-SORT(A, n)
	for i <- 1 to n
		do insert A[i] into list B[floor{nA[i]}]
	for i <- 0 to n - 1
		do sort list B[i] with insertion sort
	concatenate lists B[0], B[1], ..., B[n - 1]
		together in order
	return the concatenated lists
```