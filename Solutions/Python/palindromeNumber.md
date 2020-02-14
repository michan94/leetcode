## Problem

Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

**First Solution:**
```python
class Solution(object):
    def isPalindrome(self, x):
        result = "";
        if x < 0:
            return False;
        else:
            x = str(x);
            for digit in x[::-1]:
                result += digit;
            if result == x:
                return True;
            else:
                return False;
```