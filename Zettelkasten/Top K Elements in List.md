# Top K Elements in List

#### Problem statement
Given an integer array `nums` and an integer `k`, return the `k` most frequent elements within the array.
The test cases are generated such that the answer is always **unique**.
You may return the output in **any order**.

##### Example 1
```
Input: nums = [1,2,2,3,3,3], k = 2
Output: [2,3]
```
##### Example 2
```
Input: nums = [7,7], k = 1
Output: [7]
```
#### Solution
```
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        counts = {}
        freq = [[] for i in range(len(nums) + 1)]
        for i in nums:
            counts[i] = 1 + counts.get(i, 0)
        for num, count in counts.items():
            freq[count].append(num)
        res = []
        for i in range(len(freq) - 1, 0, -1):
            for num in freq[i]:
                res.append(num)
                if len(res) == k:
                    return res
```

###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:
- [[Python Dictionary]]
- [[hashmap]]
#### Important Subdetails

- Utilizes [[Bucketsort]]
- Alternative option is to use a [[Heap]]

#### Runtime of Optimal Solution

- O(n) run time
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-02 16:12
