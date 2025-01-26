# Make Lexicographically Smallest Array by Swapping Elements

#### Problem statement

You are given a **0-indexed** array of **positive** integers `nums` and a **positive** integer `limit`.

In one operation, you can choose any two indices `i` and `j` and swap `nums[i]` and `nums[j]` **if** `|nums[i] - nums[j]| <= limit`.

Return _the **lexicographically smallest array** that can be obtained by performing the operation any number of times_.

An array `a` is lexicographically smaller than an array `b` if in the first position where `a` and `b` differ, array `a` has an element that is less than the corresponding element in `b`. For example, the array `[2,10,3]` is lexicographically smaller than the array `[10,2,3]` because they differ at index `0` and `2 < 10`.
##### Example 1
```
```
##### Example 2
```
```
#### Solution
```
class Solution(object):
    def lexicographicallySmallestArray(self, nums, limit):
        """
        :type nums: List[int]
        :type limit: int
        :rtype: List[int]
        """

		#get a copy of the nums array but sorted
        numsSorted = sorted(nums)
        currGroup, numToGroup, groupToList = 0, {}, defaultdict(lambda : deque())

		#set up the first number to be in the first group
        numToGroup[numsSorted[0]] = currGroup
        groupToList[currGroup].append(numsSorted[0])

  
        for i in range(1, len(nums)):
	        #check if the number is in the group with the previous number or if its the start of its own number
            if abs(numsSorted[i] - numsSorted[i - 1]) > limit:
                currGroup += 1

			#allocate the number to its group
            numToGroup[numsSorted[i]] = currGroup

			#add it to the queue of the ngroup
            groupToList[currGroup].append(numsSorted[i])

          for i in range(len(nums)):
            num = nums[i]
            #get the group the number belongs to
            group = numToGroup[num]
            #pop from the front of the queue of the group the number belongs to. this position should have the smallest number of its group
            nums[i] = groupToList[group].popleft()

         return nums
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Sorting]]
- [[Greedy]]
- [[Hand of Straights]]
	- Similar to this problem as we are organizing into groups except isntead of this being sequential we are organizing them as long as they fall within the limit of the number before it
#### Important Subdetails

- Idea here is that because we know we can swap numbers we can get a number into any position as long as the numbers before it fall within the limit of the number before it. so a, b ,c can be swapped across their positions as long as abs(a - b) < limit and abs(b - c) < limit
- So we just get a copy of the array, sort it by increasing numbers and then for each number check if the number can be swapped with the number before it. if it can then its part of the same group as the number before it otherwise it starts its own group
- maintain a queue mapping the numbers to their group because you want to pop the min value aka popleft and if you try to pop from an array its a far more expensive operation

#### Runtime of Optimal Solution

- Runtime is O(n log n ) as its domintaed by the sorting
- O(n) space complexity as we maintain a mapping of all the numbers. 
---
Links :: [[#Example Code]] [[Computer Science]] [[leetcode]] [[Leetcode Daily Contests]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-25 18:21
