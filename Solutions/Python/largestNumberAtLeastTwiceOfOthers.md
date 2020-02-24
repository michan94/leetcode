## Problem

In a given integer array nums, there is always exactly one largest element.

Find whether the largest element in the array is at least twice as much as every other number in the array.

If it is, return the index of the largest element, otherwise return -1.

### Example 1:

Input: nums = [3, 6, 1, 0]

Output: 1

Explanation: 6 is the largest integer, and for every other number in the array x,

6 is more than twice as big as x.  The index of value 6 is 1, so we return 1.
 

### Example 2:

Input: nums = [1, 2, 3, 4]

Output: -1

Explanation: 4 isn't at least as big as twice the value of 3, so we return -1.

**First Solution:**
```python
class Solution(object):
    def dominantIndex(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        largestIndex = 0;
        largest = 0;
        for num in nums:
            if num > largest:
                largest = num
                largestIndex = nums.index(num);
        for num in nums:
            if num != largest:
                if 2*num > largest:
                    return -1;
        return largestIndex;
```