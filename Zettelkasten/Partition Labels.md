# Partition Labels

#### Problem statement

You are given a string `s` consisting of lowercase English letters.

We want to split the string into as many substrings as possible, while ensuring that each letter appears in at most one substring.

Return a list of integers representing the size of these substrings in the order they appear in the string.

##### Example 1
```
Input: s = "xyxxyzbzbbisl"

Output: [5, 5, 1, 1, 1]
```
##### Example 2
```
Input: s = "abcabc"

Output: [6]
```
#### Solution
```
class Solution:
    def partitionLabels(self, s: str) -> List[int]:
    
        lastIndex = {}
        for i, c in enumerate(s):
            lastIndex[c] = i

        res = []

        size = end = 0

        for i, c in enumerate(s):
            size += 1
            end = max(end, lastIndex[c])
  
            if i == end:
                res.append(size)
                size = 0
  
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[hashmap]]
#### Important Subdetails

- To partition it such that each letter appears in at most one substring that means each substring has to include all the characters up until the last index of which ever character we've seen so far that has the farthest index
- So we iterate over characters in the string, keep a track of the farthest last index of all characters seen. 
- Once the index we are at equals the farthest last index we know we have reached the end of one partition. So we add the size variable we have been using to track the size of each partition to the result array. Then we reset size to 0. We know end will be reset on the next character as it will be a new character with a greater lastindex value.
- The greedy approach is because we are optimizing for the smallest possible partition that contains all occurences of its characters
#### Runtime of Optimal Solution

- Time complexity O(n)
- Space complexity O(m) where m is number of unique charactesr
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-06 14:21
