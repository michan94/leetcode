## Problem

Given a linked list, remove the n-th node from the end of list and return its head.

### Example:

Given linked list: 1->2->3->4->5, and n = 2.

After removing the second node from the end, the linked list becomes 1->2->3->5.


**First Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def removeNthFromEnd(self, head, n):
        """
        :type head: ListNode
        :type n: int
        :rtype: ListNode
        """
        if head is None:
            return head
        counter = 0
        curr = head
        while curr is not None:
            counter += 1
            curr = curr.next
        temp = ListNode(0)
        temp.next = head
        curr = temp
        steps = counter - n
        while steps > 0:
            curr = curr.next
            steps -= 1
        curr.next = curr.next.next
        return temp.next
```