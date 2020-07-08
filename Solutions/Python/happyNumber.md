## Problem

Write an algorithm to determine if a number is "happy".

A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

### Example: 

Input: 19

Output: true

Explanation: 

12 + 92 = 82

82 + 22 = 68

62 + 82 = 100

12 + 02 + 02 = 1


**First Solution:**
```python
class Solution(object):
    def isHappy(self, n):
        """
        :type n: int
        :rtype: bool
        """
        seen = set()
        while n != 1:
            n = sum([int(i) ** 2 for i in str(n)])
            if n in seen:
                return False
            else:
                seen.add(n)
        return True 
```

**Second Solution:**
```python
class Solution(object):
    def isHappy(self, n):
        """
        :type n: int
        :rtype: bool
        """
        seen = set()
        result = 0
        while n != 1:
            n = str(n);
            for digit in n:
                result += int(digit)**2;
            if result != 1:
                n = result;
                if result in seen:
                    return False
                else:
                    seen.add(result)
        return True;
```

**Third Solution:**
```python
class Solution(object):
    def isHappy(self, n):
        """
        :type n: int
        :rtype: bool
        """
        seen = set()
        while n != 1:
            temp = 0
            num = str(n)
            for digit in num:
                temp += int(digit)**2
            if temp in seen:
                return False
            else:
                seen.add(temp)
                n = temp
        return True
```