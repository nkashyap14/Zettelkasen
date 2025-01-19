# Reverse Integer

#### Problem statement

You are given a signed 32-bit integer `x`.

Return `x` after reversing each of its digits. After reversing, if `x` goes outside the signed 32-bit integer range `[-2^31, 2^31 - 1]`, then return `0` instead.

Solve the problem without using integers that are outside the signed 32-bit integer range.
##### Example 1
```
Input: x = 1234

Output: 4321
```
##### Example 2
```
Input: x = -1234

Output: -4321
```
#### Solution
```
class Solution:
    def reverse(self, x: int) -> int:

        MIN, MAX = -2147483648, 2147483647
        res = 0

        while x:
	        #reversing just involves getting the 1st digit and putting it at the biggest spot
            digit = int(math.fmod(x, 10)) #in python -1 % 10 = 9
            x = int(x / 10) # in python -1 // 10 = -1

			#check if res has been built to be outside of bounds specified so return 0
            if (res > MAX // 10 or (res == MAX // 10 and digit >= MAX % 10)):
                return 0

            if (res < MIN // 10 or (res == MIN // 10 and digit >= MIN % 10)):
                return 0

			# multiply by base 10 to constantly move the built up digits forward and then place the newly accounted for digit in its appropratei position
            res = (res * 10) + digit

  

        return res
```


#### Brute Force Solution
```
class Solution:
    def reverse(self, x: int) -> int:
        org = x
        x = abs(x)
        res = int(str(x)[::-1])
        if org < 0:
            res *= -1
        if res < -(1 << 31) or res > (1 << 31) - 1:
            return 0
        return res
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Bit Manipulation]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(1) time O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-18 20:27
