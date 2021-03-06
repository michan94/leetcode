## Problem

Given a fixed length array arr of integers, duplicate each occurrence of zero, shifting the remaining elements to the right.

Note that elements beyond the length of the original array are not written.

Do the above modifications to the input array in place, do not return anything from your function.

 

### Example 1:

Input: [1,0,2,3,0,4,5,0]

Output: null

Explanation: After calling your function, the input array is modified to: [1,0,0,2,3,0,0,4]

### Example 2:

Input: [1,2,3]

Output: null

Explanation: After calling your function, the input array is modified to: [1,2,3]


**First Solution:**
```python
class Solution(object):
    def duplicateZeros(self, arr):
        """
        :type arr: List[int]
        :rtype: None Do not return anything, modify arr in-place instead.
        """
        numNums = len(arr);
        result = [];
        while len(result) < numNums:
            for num in arr:
                result.append(num);
                if num == 0:
                    result.append(num);
        for i in range(len(arr)):
            arr[i] = result[i];
```

**Second Solution:**
```python
class Solution(object):
    def duplicateZeros(self, arr):
        """
        :type arr: List[int]
        :rtype: None Do not return anything, modify arr in-place instead.
        """
        numZero = arr.count(0)
        for i in range(len(arr) - 1, -1, -1):
            if i + numZero < len(arr):
                arr[i + numZero] = arr[i]
            if arr[i] == 0: 
                numZero -= 1
                if i + numZero < len(arr):
                    arr[i + numZero] = 0
```