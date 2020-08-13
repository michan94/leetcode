## Problem

Given an integer (signed 32 bits), write a function to check whether it is a power of 4.

### Example 1:

Input: 16

Output: true

### Example 2:

Input: 5

Output: false



**First Solution:**
```python
class Solution(object):
    def isPowerOfFour(self, num):
        """
        :type num: int
        :rtype: bool
        """
        while num > 1.0:
            num = num/4.0
        if num == 1.0:
            return True
        else:
            return False
```