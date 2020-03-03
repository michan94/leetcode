## Problem

Given a positive integer num, write a function which returns True if num is a perfect square else False.

Note: Do not use any built-in library function such as sqrt.

### Example 1:

Input: 16

Output: true

### Example 2:

Input: 14

Output: false

**First Solution:**
```python
class Solution(object):
    def isPerfectSquare(self, num):
        """
        :type num: int
        :rtype: bool
        """
        if num < 0:
            return -1;
        left = 0;
        right = num;
        while (left + 1) < right:
            mid = (left + right) // 2;
            if mid**2 == num:
                return mid;
            elif mid**2 < num:
                left = mid
            else:
                right = mid;
        #left + 1 == right
        if left**2 == num:
            return left;
        if right**2 == num:
            return right;        
        return False;
```

