## Problem

Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).

Return the running sum of nums.

### Example 1:

Input: nums = [1,2,3,4]

Output: [1,3,6,10]

Explanation: Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].

### Example 2:

Input: nums = [1,1,1,1,1]

Output: [1,2,3,4,5]

Explanation: Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].

### Example 3:

Input: nums = [3,1,2,10,1]

Output: [3,4,6,16,17]
 
Constraints:

1 <= nums.length <= 1000

-10^6 <= nums[i] <= 10^6

**First Solution:**
```python
class Solution(object):
    def runningSum(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        temp = []
        left = 0
        right = 0
        while right < len(nums):
            total = 0
            left = 0
            while left <= right:
                total += nums[left]
                left += 1
            temp.append(total)
            right += 1
        return temp
```