# Merge K Sorted Linked Lists

#### Problem statement

You are given an array of `k` linked lists `lists`, where each list is sorted in ascending order.

Return the **sorted** linked list that is the result of merging all of the individual linked lists.
##### Example 1
```
Input: lists = [[1,2,4],[1,3,5],[3,6]]

Output: [1,1,2,3,3,4,5,6]
```
##### Example 2
```
Input: lists = []

Output: []
```
#### Solution
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next


class Solution:    
    def mergeKLists(self, lists: List[Optional[ListNode]]) -> Optional[ListNode]:
        if not lists or len(lists) == 0:
            return None
        while len(lists) > 1:
            mergedList = []

            for i in range(0, len(lists), 2):
                l1 = lists[i]
                l2 = lists[i + 1] if (i + 1) < len(lists) else None
                mergedList.append(self.mergeList(l1, l2))

            lists = mergedList

        return lists[0]

    def mergeList(self, l1, l2):
        dummy = curr = ListNode()

        while l1 and l2:
            if l1.val < l2.val:
                curr.next = l1
                l1 = l1.next
            else:
                curr.next = l2
                l2 = l2.next
            curr = curr.next
        if l1:
            curr.next = l1
  
        if l2:
            curr.next = l2

        return dummy.next
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Linked List]]
- [[Divide and Conquer Algorithm]]
#### Important Subdetails

- We divide k lists into two every time so thats why its log k
- we go through the k linked lists and merge two of theme ach time
#### Runtime of Optimal Solution

- O(n * log k) time complexity
	- Log k is the nummber of times we repeat the o(n) merge
- O(log k ) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-25 18:10
