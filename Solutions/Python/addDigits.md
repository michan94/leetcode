## Problem

Given a non-negative integer num, repeatedly add all its digits until the result has only one digit.

### Example:

Input: 38

Output: 2 

Explanation: The process is like: 3 + 8 = 11, 1 + 1 = 2. 

Since 2 has only one digit, return it.


**First Solution:**
```python
class Solution(object):
    def addDigits(self, num):
        """
        :type num: int
        :rtype: int
        """
        result = 0;
        while num > 0:
            result += num % 10;
            num /= 10;
        while result >= 10:
            return self.addDigits(result);
        return result
```

**Second Solution:**
```python
class Solution(object):
    def addDigits(self, num):
        """
        :type num: int
        :rtype: int
        """
        result = 0;
        num = str(num);
        for digit in num:
            result += int(digit)
        if result >= 10:
            return self.addDigits(result);
        else:
            return result;
```