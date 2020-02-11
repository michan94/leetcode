## Problem

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

**First Solution:**
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] result = new int[2];
        for (int i = 0; i < nums.length - 1; i ++) {
            for (int j = i + 1; j < nums.length; j++) {
                if ((target - nums[i]) == nums[j]) {
                        result[0] = i;
                        result[1] = j;
                }
            }
        }
        return result;
    }
}
```
