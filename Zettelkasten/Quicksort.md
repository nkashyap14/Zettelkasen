# Quicksort

- [[Divide and Conquer Algorithm]]
	- Breaks a problem down into multiple subproblems recursively until they become simple to solve
- Quicksort works on the idea that an element is in its sorted position when all the elements to the left of it are smaller than it and all the elements greater than it are to the right of it
- Two pointers: Working from both sides of the array
	- Iterate until you find an element on left side greater than the pivot and on the right less than the pivot. Swap them
	- Pivot gets swapped to the position of j at the end of the iteration
	- Then quick sort gets recursively performed on the left side and the right side
#### General Algorithm:
- 1.
	- Choose pivot (last or random)
- 2.
	- Store elements less than the pivot in left subarray
	- Store elements greater than pivot in right subarray
- 3.
	- Call quicksort recursively on the left subarray
	- Call quicksort recursively on the right subarray

#### Code
```
def quicksort(nums, left, right):
	if left < right:
		partition_pos = partition(arr, left, right)
		quicksort(arr, left, partition_pos - 1)
		quicksort(arr, partition_pos + 1, right)

	def partition(arr, left, right):
		i = left
		j = right - 1
		pivot = arr[right]

		while i < j:
			while i < right and arr[i] < pivot:
				i += 1
			while j > left and arr[j] >= pivot:
				j -= 1

			if i < j:
				arr[i], arr[j] = arr[j], arr[i]

		if arr[i] > pivot:
			arr[i], arr[right] = arr[right], arr[i]

		return i
	
```


##### Runtime:
- Quicksort has an n log n run time on average/best
- O(n^2) worst case if poor pivot chosen
---
Links :: [[Computer Science]] [[Algorithm]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-13 19:54
