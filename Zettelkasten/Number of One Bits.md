# Number of One Bits

#### Problem statement

You are given an unsigned integer `n`. Return the number of `1` bits in its binary representation.

You may assume `n` is a non-negative integer which fits within 32-bits.
##### Example 1
```
Input: n = 00000000000000000000000000010111

Output: 4
```
##### Example 2
```
Input: n = 01111111111111111111111111111101

Output: 30
```
#### Solution 1
```
class Solution:
	def hammingWeight(self, n: int) -> int:
		res = 0
		while n:
			res += n % 2
			n = n >> 1
		return res
```

#### Solution 2
```
class Solution:
    def hammingWeight(self, n: int) -> int:
        res = 0
        while n:
            n &= (n - 1)
            res += 1

        return res
```
###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:
- [[Bit Manipulation]]
#### Important Subdetails

- Solution one involves us just modding by 2 and bits are in base 2 format anyways as such we are always grabbing that first 1 digit. Its either going to be 0 or 1 so we are basically incrementing res by 1 each time we have a 1 in the first bit and then we remove that bit by shifting n by 1
- Solution 2 involves just removing 1 from the number. This removes one bit each time. So therefore the amount of times you can subtract 1 and run a logical and on the number and once it ='s 0 represents the amount of bits you have in the number

#### Runtime of Optimal Solution

- Solution one runtime is O(32)
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 14:24
