# Multiply Strings

#### Problem statement

You are given two strings `num1` and `num2` that represent non-negative integers.

Return the product of `num1` and `num2` in the form of a string.

Assume that neither `num1` nor `num2` contain any leading zero, unless they are the number `0` itself.

**Note**: You can not use any built-in library to convert the inputs directly into integers.
##### Example 1
```
Input: num1 = "3", num2 = "4"

Output: "12"
```
##### Example 2
```
Input: num1 = "111", num2 = "222"

Output: "24642"
```
#### Solution
```
class Solution:
    def multiply(self, num1: str, num2: str) -> str:

        if "0" in [num1, num2]:
            return "0"

        res = [0] * (len(num1) + len(num2))
        num1, num2 = num1[::-1], num2[::-1]

        for i1 in range(len(num1)):
            for i2 in range(len(num2)):
                digit = int(num1[i1]) * int(num2[i2])
                res[i1 + i2] += digit
                res[i1 + i2 + 1] += (res[i1 + i2] // 10)
                res[i1 + i2] = res[i1 + i2] % 10

        #we iterated the two strings in reverse so we have a reversed number
        #where if output is 120 it will be 021, reverse that back
        res, beg = res[::-1], 0

        #while we have leading zeros incrememnt pointer

        while beg < len(res) and res[beg] == 0:
            beg += 1

        res = map(str, res[beg:])

  

        return "".join(res)
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
#### Important Subdetails

#### Runtime of Optimal Solution

- O(m * n) runtime and O(m + n) space complexity where m and n are the length of the two strings
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-20 10:07
