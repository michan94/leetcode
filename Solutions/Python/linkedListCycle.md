## Problem

Given a linked list, determine if it has a cycle in it.

To represent a cycle in the given linked list, we use an integer pos which represents the position (0-indexed) in the linked list where tail connects to. If pos is -1, then there is no cycle in the linked list.

### Example 1:

Input: head = [3,2,0,-4], pos = 1

Output: true

Explanation: There is a cycle in the linked list, where tail connects to the second node.


### Example 2:

Input: head = [1,2], pos = 0

Output: true

Explanation: There is a cycle in the linked list, where tail connects to the first node.


### Example 3:

Input: head = [1], pos = -1

Output: false

Explanation: There is no cycle in the linked list.


**First Solution:**
```python
# Tortoise and the Hare Solution

# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def hasCycle(self, head):
        """
        :type head: ListNode
        :rtype: bool
        """
        try:
            slow = head;
            fast = head.next; 
            while slow != fast:
                slow = slow.next;
                fast = fast.next.next;
            return True;
        except:
            return False;
```

**Second Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def hasCycle(self, head):
        """
        :type head: ListNode
        :rtype: bool
        """
        slow = head;
        fast = head;
        while fast is not None and fast.next is not None:
            slow = slow.next;
            fast = fast.next.next;
            if fast == slow:
                return True;
        return False;
```