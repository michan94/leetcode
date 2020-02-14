## Problem

Given an array of integers A sorted in non-decreasing order, return an array of the squares of each number, also in sorted non-decreasing order.

**First Solution:**
```python
class Solution(object):
    def sortedSquares(self, A):
        result = [];
        for num in A:
            num = num**2;
            result.append(num);
        result.sort();
        return result;   
```