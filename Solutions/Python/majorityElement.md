## Problem

Given an array of size n, find the majority element. The majority element is the element that appears more than ⌊ n/2 ⌋ times.

You may assume that the array is non-empty and the majority element always exist in the array.

### Example 1:

Input: [3,2,3]

Output: 3

### Example 2:

Input: [2,2,1,1,1,2,2]

Output: 2

**First Solution:**
```python
class Solution(object):
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        counter = {}
        for num in nums:
            if num in counter:
                counter[num] += 1
            else:
                counter[num] = 1
        for key, value in counter.items():
            if value > (len(nums)//2):
                return key
```