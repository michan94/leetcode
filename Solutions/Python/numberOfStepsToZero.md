## Problem

Given a non-negative integer num, return the number of steps to reduce it to zero. If the current number is even, you have to divide it by 2, otherwise, you have to subtract 1 from it.

**First Solution:**
```python
class Solution(object):
    def numberOfSteps(self, num):
        count = 0;
        if (num == 0):
            return count;
        if (num % 2 == 0):
            return 1 + self.numberOfSteps(num/2);
        else:
            return 1 + self.numberOfSteps( num-1); 
```
