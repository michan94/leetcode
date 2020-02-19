## Problem

Given an integer, write a function to determine if it is a power of two.

### Example 1:

Input: 1

Output: true 

Explanation: 20 = 1

### Example 2:

Input: 16

Output: true

Explanation: 24 = 16

### Example 3:

Input: 218

Output: false

**First Solution:**
```python
class Solution(object):
    def isPowerOfTwo(self, n):
        tracker = 1;
        counter = 1;
        if n == 1:
            return True;
        else:
            while tracker <= n:
                temp = 2**(counter);
                if temp == n:
                    return True;
                else:
                    tracker = temp;
                    counter += 1;
            return False;
```