## Problem

Given an array of integers, find if the array contains any duplicates.

Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

### Example 1:

Input: [1,2,3,1]

Output: true

### Example 2:

Input: [1,2,3,4]

Output: false

### Example 3:

Input: [1,1,1,3,3,4,3,2,4,2]

Output: true


**First Solution:**
```python
class Solution(object):
    def reverseString(self, s):
        """
        :type s: List[str]
        :rtype: None Do not return anything, modify s in-place instead.
        """
        left = 0
        right = len(s)-1
        while left <= right:
            temp = s[left]
            s[left] = s[right]
            s[right] = temp
            left += 1
            right -= 1
```