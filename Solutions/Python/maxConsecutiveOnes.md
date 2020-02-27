## Problem

Given a binary array, find the maximum number of consecutive 1s in this array.

### Example 1:

Input: [1,1,0,1,1,1]

Output: 3

Explanation: The first two digits or the last three digits are consecutive 1s.

The maximum number of consecutive 1s is 3.

**First Solution:**
```python
class Solution(object):
    def findMaxConsecutiveOnes(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        currLongest = 0;
        curr = 0;
        for i in range(len(nums)):
            if nums[i] == 1:
                curr += 1;
                if curr > currLongest:
                    currLongest = curr;
                i += 1;
            else:
                curr = 0;
                i += 1;
        return currLongest;
```

