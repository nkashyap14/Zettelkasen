# Longest Common Prefix

#### Problem statement


##### Example 1
```
```
##### Example 2
```
```
#### Solution
```
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """

        if not strs:
            return ""
        prefix = strs[0]

        for i in range(1, len(strs)):
            while strs[i].find(prefix) != 0:
                prefix = prefix[:-1]
                if not prefix:
                    return ""                

        return prefix
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Python String Find]]
#### Important Subdetails

- Use the find function to check if the index of the prefix is the 0 function or not
- keep shortening the prefix until it matches on each string

#### Runtime of Optimal Solution

- Time complexity: O(n * m) n is the number of string in the array and m is the length of longest string
- Space complexity: O(m) if we store the prefix string starting as 0 as the longest string
---
Links :: [[#Example Code]] [[Computer Science]] [[Amazon Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-04 14:27
