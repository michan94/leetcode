## Problem

Given a singly linked list of integers, determine whether or not it's a palindrome

### Examples

For l = [0, 1, 0], the output should be:

isListPalindrome(l) = true;

For l = [1, 2, 2, 3], the output should be:

isListPalindrome(l) = false


**First Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def isPalindrome(self, head):
        """
        :type head: ListNode
        :rtype: bool
        """
        curr = head
        temp = []
        while curr is not None:
            temp.append(curr.val)
            curr = curr.next
        left = 0
        right = len(temp) - 1
        while left <= right:
            if temp[left] != temp[right]:
                return False
            else:
                left += 1
                right -= 1
        return True
```