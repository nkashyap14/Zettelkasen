# Kth Largest Integer in a Stream

#### Problem statement

Design a class to find the `kth` largest integer in a stream of values, including duplicates. E.g. the `2nd` largest from [1, 2, 3, 3] is `3`. The stream is not necessarily sorted.

Implement the following methods:

- `constructor(int k, int[] nums)` Initializes the object given an integer `k` and the stream of integers `nums`.
- `int add(int val)` Adds the integer `val` to the stream and returns the `kth` largest integer in the stream.
##### Example 1
```
Input:
["KthLargest", [3, [1, 2, 3, 3]], "add", [3], "add", [5], "add", [6], "add", [7], "add", [8]]

Output:
[null, 3, 3, 3, 5, 6]

Explanation:
KthLargest kthLargest = new KthLargest(3, [1, 2, 3, 3]);
kthLargest.add(3);   // return 3
kthLargest.add(5);   // return 3
kthLargest.add(6);   // return 3
kthLargest.add(7);   // return 5
kthLargest.add(8);   // return 6
```
#### Solution
```
class KthLargest:
    def __init__(self, k: int, nums: List[int]):
        self.minheap, self.k  = nums, k
        heapq.heapify(self.minHeap)
        while.len(self.minHeap) > k:
            heapq.heappop(self.minHeap)  

    def add(self, val: int) -> int:
        heapq.heappush(self.minHeap, val)
        if len(self.minHeap) > self.k:
            heapq.heappop(self.minHeap)
        return self.minHeap[0]
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Heap]]
#### Important Subdetails

- heapq is a binary [[heap]]
	- O(log n) push
	- O(log n) pop
	- heapify is a O(n) call to build the heap
		- O((n - k) * log n) to make the heap into a correct state
	- Get min value from a heap in O(1) time
- heapq.heapify turns it into a minheap
	- If we want a max heap negate the values of the keys

#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-13 07:12
