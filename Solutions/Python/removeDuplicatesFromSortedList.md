## Problem

Given the head of a sorted linked list, delete all duplicates such that each element appears only once. Return the linked list sorted as well.

### Example:

Input: head = [1,1,2]
Output: [1,2]

Input: head = [1,1,2,3,3]
Output: [1,2,3]

**First Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def deleteDuplicates(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        prev = head
        curr = head
        while curr is not None:
            #Duplicate
            while curr is not None and curr.val == prev.val:
                curr = curr.next
            #Not duplicate
            prev.next = curr
            prev = curr
        return head
```
