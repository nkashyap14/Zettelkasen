# Reorganize String

#### Problem statement

Given a string `s`, rearrange the characters of `s` so that any two adjacent characters are not the same.

Return _any possible rearrangement of_ `s` _or return_ `""` _if not possible_.
##### Example 1
```
Example 1:

Input: s = "aab"
Output: "aba"
```
##### Example 2
```
Example 2:

Input: s = "aaba"
Output: ""
```
#### Solution
```
class Solution(object):
    def reorganizeString(self, s):
        """
        :type s: str
        :rtype: str
        """
        count = Counter(s)
        maxHeap = [(-count, value) for value, count in count.items()]
        heapq.heapify(maxHeap)
        res = ""
        if -maxHeap[0][0] > ((len(s) + 1) // 2):
            return ""
        while len(maxHeap) >= 2:
            freq1, ch1 = heapq.heappop(maxHeap)
            freq2, ch2 = heapq.heappop(maxHeap)

            res += ch1
            res += ch2
            if freq1 < -1:
                heapq.heappush(maxHeap, (freq1 + 1, ch1))
            if freq2 < -1:
                heapq.heappush(maxHeap, (freq2 + 1, ch2))
        if maxHeap:
            res += maxHeap[0][1]
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
- [[MaxHeap]]
#### Important Subdetails

- Space complexity is O(n) as result string builds up to lenght n
- Time complexity is O(n log k) k being the alphabet size and n coming from the fact that each pop from the heap is log k  and push and we pop n times
#### Runtime of Optimal Solution

- Space Complexity is O(n)
- Time complexity is O(n log n)
---
Links :: [[#Example Code]] [[Computer Science]] [[Amazon Leetcode]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-02 09:21
