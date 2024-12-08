# Palindromic Substring

#### Problem statement


##### Example 1
```
```
##### Example 2
```
```
#### Solution
```
class Solution:
    def countSubstrings(self, s: str) -> int:
        res = 0
        for i in range(len(s)):
            # count the palindromes for odd length palindromes with the current index as the middle character
            res += self.countPalindromes(s, i, i)
            # count the palindromes for odd length palindromes with the 2 adjacent characters as the middle
            res += self.countPalindromes(s, i, i + 1)
        return res

  

    def countPalindromes(self, s, l, r):
        res = 0
        while l >= 0 and r < len(s) and s[l] == s[r]:
            res += 1
            l -= 1
            r += 1
        return res

========================================================================================
class Solution:
    def countSubstrings(self, s: str) -> int:
        res = 0
        
        for i in range(len(s)):
            # odd length
            l, r = i, i
            while l >= 0 and r < len(s) and s[l] == s[r]:
                res += 1
                l -= 1
                r += 1

            # even length
            l, r = i, i + 1
            while l >= 0 and r < len(s) and s[l] == s[r]:
                res += 1
                l -= 1
                r += 1
        
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
- [[Two Pointers]]
#### Important Subdetails

- Instead of starting at the outer ends of the palindrome and checking inwards to see if the condition matches start at each individual character which we know is a palindrome always and branch outwards
#### Runtime of Optimal Solution

- O(n^2) runtime
- O(1) space complexity as only 2 pointers are used
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-05 06:51
