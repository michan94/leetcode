## Problem

Given an integer number n, return the difference between the product of its digits and the sum of its digits.

**First Solution:**
```python
class Solution(object):
    def subtractProductAndSum(self, n):
        """
        :type n: int
        :rtype: int
        """
        total = 0;
        product = 1;
        n = str(n);
        for digit in n:
            total += int(digit);
            product *= int(digit);
        return product - total;
```
