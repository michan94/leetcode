## Problem

Given an array of integers arr, write a function that returns true if and only if the number of occurrences of each value in the array is unique.


**First Solution:**
```python
class Solution(object):
    def uniqueOccurrences(self, arr):
        numbers = {};
        result = [];
        for num in arr:
            if num not in numbers:
                numbers[num] = 1;
            else:
                numbers[num] += 1;
        for count in numbers.values():
            if count not in result:
                result.append(count);
            else:
                return False;
        return True;
```