# Hand of Straights

#### Problem statement

You are given an integer array `hand` where `hand[i]` is the value written on the `ith` card and an integer `groupSize`.

You want to rearrange the cards into groups so that each group is of size `groupSize`, and card values are consecutively increasing by `1`.

Return `true` if it's possible to rearrange the cards in this way, otherwise, return `false`.
##### Example 1
```
Input: hand = [1,2,4,2,3,5,3,4], groupSize = 4

Output: true
```
##### Example 2
```
Input: hand = [1,2,3,3,4,5,6,7], groupSize = 4

Output: false
```
#### Solution 1
```
class Solution:
    def isNStraightHand(self, hand: List[int], groupSize: int) -> bool:
        if len(hand) % groupSize != 0:
            return False
            
        hand.sort()
        count = Counter(hand)
  
        for num in hand:
            if count[num]:
                for i in range(num, num + groupSize):
                    if not count[i]:
                        return False
                    count[i] -= 1

        return True
```


#### Solution 2: MinHeap
```
class Solution:
    def isNStraightHand(self, hand: List[int], groupSize: int) -> bool:
        if len(hand) % groupSize:
            return False

        count = {}
        for n in hand:
            count[n] = 1 + count.get(n, 0)

        minH = list(count.keys())
        heapq.heapify(minH)
        while minH:
            first = minH[0]
            for i in range(first, first + groupSize):
                if i not in count:
                    return False
                count[i] -= 1
                if count[i] == 0:
                    if i != minH[0]:
                        return False
                    heapq.heappop(minH)
        return True
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Greedy]]
- [[Heap]]
#### Important Subdetails

- Sort the array as in typical greedy problems
- The greedy approach in this is based on the idea that we start each group with the minimum value available
- This is similar to leetcode problem [[divide array into k sized groups]]
- In the heap issue the minH[0] != i check happens because minH[0] for middle values will represent the start value of the next potential group so if a middle value is used up that means the next group will not be able to be made so we know we have falsified the condition


#### Runtime of Optimal Solution

- Runtime of First solujtion is O(n log n) due to sorting and O(n) due to the counter
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-06 13:52
