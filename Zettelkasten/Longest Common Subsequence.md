# Longest Common Subsequence

#### Problem statement

Given two strings `text1` and `text2`, return the length of the _longest common subsequence_ between the two strings if one exists, otherwise return `0`.

A **subsequence** is a sequence that can be derived from the given sequence by deleting some or no elements without changing the relative order of the remaining characters.

- For example, `"cat"` is a subsequence of `"crabt"`.

A **common subsequence** of two strings is a subsequence that exists in both strings.
##### Example 1
```
Input: text1 = "cat", text2 = "crabt" 

Output: 3 
```
##### Example 2
```
Input: text1 = "abcd", text2 = "abcd"

Output: 4
```
#### Solution
```
class Solution:
    def longestCommonSubsequence(self, text1: str, text2: str) -> int:


        #m x n matrix
        # where m is number of rows whichis = length of first string + 1
        # n is number of columns which is = lenght of second string + 1
        # 0th row represents ann intance wher we are using 0 characters from text 1
        # 0th column represents an instance where we are using 0 characters from text 2
        # in that case we know there is 0 matches
        # each i, j represents by text1[i] and text2[j] chracters what is the length of the longest commmon
        # subsequence so far

        dp = [[0] * (len(text2) + 1) for _ in range(len(text1) + 1)]

  
        for i in range(1, len(text1) + 1):
            for j in range(1, len(text2) + 1):
                if text1[i - 1] == text2[j - 1]:
                    #increment by 1 because charracters match
                    #if they match then we know we need to go to the subproblem of adding the max of
                    #the substring that doesn't include this character
                    dp[i][j] = 1 + dp[i - 1][j - 1]
                else:
                    #if the characters don't match then we have to take the max of the matching subsequences
                    #which occurs between subtracting one character from either of the substrings
                    dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])

        return dp[len(text1)][len(text2)]
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(m * n) runtime and O(m * n) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-07 16:20
