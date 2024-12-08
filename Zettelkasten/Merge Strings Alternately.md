# Merge Strings Alternately

#### Problem statement

You are given two strings `word1` and `word2`. Merge the strings by adding letters in alternating order, starting with `word1`. If a string is longer than the other, append the additional letters onto the end of the merged string.

Return _the merged string._
##### Example 1
```
**Input:** word1 = "abc", word2 = "pqr"
**Output:** "apbqcr"
**Explanation:** The merged string will be merged as so:
word1:  a   b   c
word2:    p   q   r
merged: a p b q c r
```
##### Example 2
```
**Input:** word1 = "ab", word2 = "pqrs"
**Output:** "apbqrs"
**Explanation:** Notice that as word2 is longer, "rs" is appended to the end.
word1:  a   b 
word2:    p   q   r   s
merged: a p b q   r   s
```
#### Solution
```
class Solution(object):
    def mergeAlternately(self, word1, word2):
        """
        :type word1: str
        :type word2: str
        :rtype: str
        """

        l1, l2 = len(word1), len(word2)
        res = ""
        for i in range(min(l1, l2)):
            res += word1[i]
            res += word2[i]

        res += word1[l2:] if l1 > l2 else word2[l1:]

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
#### Important Subdetails

- A more efficient solution would be to use arrays and then join them as with concatenation a new string is created each time which is less efficient
#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Amazon Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-02 11:41
