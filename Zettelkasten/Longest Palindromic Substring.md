# Longest Palindromic Substring

#### Problem statement
Given a string `s`, return the longest palindromic substring in `s`.

##### Example 1
```
**Input:** s = "babad"
**Output:** "bab"
**Explanation:** "aba" is also a valid answer.
```
##### Example 2
```
**Input:** s = "cbbd"
**Output:** "bb"
```
#### Solution
```
class Solution(object):

    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        longest = ''
        # creates a 2d array: [0] * len(s) is one row of len(s) columns with 0 populated
        # and then for _ in range(len(s)) makes it so that for len(s) rows are created
        dp = [[0] * len(s) for _ in range(len(s))]
        
        for i in range(len(s)):
            #each individual character by itself is a palindrome
            #dp[i][j] represents the substring or the sliice of the array
            dp[i][i] = True
            longest = s[i]
            
        #filling dp table
        for i in range(len(s) - 1, -1 , -1):
            #j starts from the i location. only iterates over the upper side of the diagonal as we don't take
            #reverse slices
            for j in range(i + 1, len(s)):
                if s[i] == s[j]: #characters match
                    #if the lenght of the sliced substring is one letter and characters are equal
                    #or if sliced substring is longer than one need to check if the inner string is a palindrome
                    #i + 1 because the i is left and j is right so we are taking the inner substring slice and checking
                    #its truth
                    if j - i == 1 or dp[i + 1][j - 1]:
                        dp[i][j] = True
                        if len(longest) < len(s[i: j + 1]):
                            longest = s[i:j + 1]
        return longest
```

#### Inefficient Solution O(n^2)
```
class Solution(object):
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """

        longest = ''
        for i in range(len(s)):
            for j in range(i + 1, len(s) + 1):
                word = s[i:j]
                if word == word[::-1]:
                    if len(word) > len(longest):
                        longest = word
        return longest
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

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
Date :: 2024-12-03 05:51
