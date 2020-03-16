## Problem

Given a 32-bit signed integer, reverse digits of an integer.

### Example 1:

Input: 123

Output: 321

### Example 2:

Input: -123

Output: -321

### Example 3:

Input: 120

Output: 21

Note:

Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−231,  231 − 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.


**First Solution:**
```python
class Solution(object):
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        temp = ""
        x = str(x)
        x.rstrip("0")
        # Input is negative
        if int(x) < 0:
            temp += "-"
            for digit in x[:0:-1]:
                temp += digit
        # Input is positive
        else:
            for digit in x[::-1]:
                temp += digit
        # Check if reversed num is within boundaries
        if int(temp) < (-2)**31 or int(temp) > ((2**31) - 1):
            return 0
        return int(temp)
```