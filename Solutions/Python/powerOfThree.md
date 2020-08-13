## Problem

Given an integer, write a function to determine if it is a power of three.

### Example 1:

Input: 27

Output: true

### Example 2:

Input: 0

Output: false

### Example 3:

Input: 9

Output: true

### Example 4:

Input: 45

Output: false



**First Solution:**
```python
class Solution(object):
    def isPowerOfThree(self, n):
        """
        :type n: int
        :rtype: bool
        """
        while n > 1.0:
            n /= 3.0
        if n == 1.0:
            return True
        return False
```