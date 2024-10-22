# Merge Two Sorted Linked Lists

#### Problem statement

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists into one **sorted** linked list and return the head of the new sorted linked list.

The new list should be made up of nodes from `list1` and `list2`.
##### Example 1
```
Input: list1 = [1,2,4], list2 = [1,3,5]

Output: [1,1,2,3,4,5]
```
##### Example 2
```
Input: list1 = [], list2 = [1,2]

Output: [1,2]
```
#### Solution
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
  
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:

		//because we are told to return the head of the new node. keep a  pointer to the beginning of the list with a dummy node
        dummy = node = ListNode()
  
        while list1 and list2:
            if list1.val < list2.val:
                node.next = list1
                list1 = list1.next
            else:
                node.next = list2
                list2 = list2.next
            node = node.next
        if list1:
            node.next = list1
        if list2:
            node.next = list2

		//return the head of the new merged list
        return dummy.next
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Linked List]]
#### Important Subdetails

#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 10:35
