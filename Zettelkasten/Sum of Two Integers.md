# Sum of Two Integers

#### Problem statement

Given two integers `a` and `b`, return the sum of the two integers without using the `+` and `-` operators.
##### Example 1
```
Input: a = 1, b = 1

Output: 2
```
##### Example 2
```
Input: a = 4, b = 7

Output: 11
```
#### Solution
```
class Solution:
    def getSum(self, a: int, b: int) -> int:
        res = 0
        carry = 0

        mask = 0xFFFFFFFF

  
  

        for i in range(32):

			#this is how we generally get the ith bit value of an integer
			# you just shift hte number over i places and then & it with 1
			# anding it with a 1 is equiaveltn to  retaining the value of that digit
			#as if its 0 / false than it evaluates to 0 and if its true it evalutes to true
            a_bit = (a >> i) & 1
            b_bit = (b >> i) & 1

			#this is how we account for carry if both bits are 1 than we xor them to be 0 but then if theres a carry we account for it by xoring 1 with a 0 so it becomes 1
            cur_bit = a_bit ^ b_bit ^ carry

			#as long as there is two 1's out of the two bit fields and the carry then we need a carry for the next valeu
            carry = (a_bit + b_bit + carry) >= 2

  

            #set the ith bit of res to be 1 as per the cur_bit
            #otherwise if cur_bit evaluates to false aka 0 than leave it
            #as res was initialized to 0 so that bit should already be 0
            if cur_bit:
				#this is how we initilate the ith bit of a number.
				#we shift one over say 2 spaces so it becomes 0100
				#all other digits are padded with 0's and thne we or it with
				#the number in question so any other digits retain their value
				#as oring it with a 0 means it will retain whatever was already there
				#while oring it with a 1 at the ith digit essentially means we flip the ith digit/set it to 1
                res |= (1 << i)

  

        #figure out with claude why this is needed in terms of a mask
        if res > 0x7FFFFFFF:
            res = ~(res ^ mask)

  
  

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized

- [[Bit Manipulation]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(1) constant time as the constaint was for numbers > -1000 and < 1000 so constant time loops
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-18 20:13
