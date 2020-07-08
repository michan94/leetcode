## Problem

Given a binary array, find the maximum number of consecutive 1s in this array.

### Example 1:

Input: [1,1,0,1,1,1]

Output: 3

Explanation: The first two digits or the last three digits are consecutive 1s.

The maximum number of consecutive 1s is 3.

**First Solution:**
```java
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int currLongest = 0;
        int curr = 0;
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] == 1) {
                curr += 1;
                if (curr > currLongest) {
                    currLongest = curr;
                }
            }
            else {
                curr = 0;
            }
        }
        return currLongest;
    }
}
```

