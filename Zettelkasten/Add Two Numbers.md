# Add Two Numbers

#### Problem statement

You are given two **non-empty** linked lists, `l1` and `l2`, where each represents a non-negative integer.

The digits are stored in **reverse order**, e.g. the number 123 is represented as `3 -> 2 -> 1 ->` in the linked list.

Each of the nodes contains a single digit. You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Return the sum of the two numbers as a linked list.
##### Example 1
```
```
##### Example 2
```
```
#### Solution
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next


class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
    
        dummy = ListNode()
        curr, carry = dummy, 0
        
        while l1 or l2 or carry:
            v1 = l1.val if l1 else 0
            v2 = l2.val if l2 else 0
  
            val = v1 + v2 + carry
            carry = val // 10
            val = val % 10
            curr.next = ListNode(val)

            curr = curr.next
            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None


        return dummy.next
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Linked List]]
#### Important Subdetails

- The carry is important
- Set a dummy node that points to nothing so that when we want to return the head we can just do return dummy.next
- set carry = to val // 10
	- this is integer division
	- even a 10 // 10 = 1
	- 9 + 9 = 18 // 10 = 1
	- sets carry appropriately
- for the calculation in order to handle the cases when a linked list is shorter than the other just use the python single line if else to set the value to 0 if either of the linked list is none
- similarly only set the linkedlist node value to the next if the value exists otherwise if its None set it to None which evaluates to false in if conditions

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
Date :: 2024-10-23 15:51
