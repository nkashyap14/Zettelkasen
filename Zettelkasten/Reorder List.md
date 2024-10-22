# Reorder List

#### Problem statement


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
    def reorderList(self, head: Optional[ListNode]) -> None:
        slow, fast = head, head.next
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        #at this point second has reached the half point of the array aka next node points to the
        #point in the linked list that we need to start reversing the links for
        second = slow.next
        #set slow.next to None because the last node in the first list is poitning to null
        prev = slow.next = None
        while second:
            tmp = second.next
            second.next = prev
            prev = second
            second = tmp

        #at this point prev now points to a reversed second half of the list. this is hte proper order we are going to add in

        first, second = head, prev
        while second:
            tmp1, tmp2 = first.next, second.next
            first.next = second
            second.next = tmp1
            first, second = tmp1, tmp2
```

###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:

- [[Linked List]]
#### Important Subdetails

- Reversing the links of the second half of the linked list to reflect the actual order you insert in
- 2 phases of alogrithm:
	- -reverse second half of linked list
	- then merge first half and second half
- How to know when you reach the second half:
	- slow and fast pointer
		- shift slow by 1
		- fast by 2
		- keep going until the fast pointer reaches none or the last value of the list
			- while fast and fast.next

#### Runtime of Optimal Solution

- O(n)
- O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 11:10
