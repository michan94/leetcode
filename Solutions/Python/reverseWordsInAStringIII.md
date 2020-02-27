## Problem

Given a string, you need to reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

### Example 1:

Input: "Let's take LeetCode contest"

Output: "s'teL ekat edoCteeL tsetnoc"

Note: In the string, each word is separated by single space and there will not be any extra space in the string.

**First Solution:**
```python
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
        text = s.split();
        tempResult = []
        for word in text:
            temp = ""
            index = len(word) - 1
            while index >= 0:
                temp += word[index];
                index -= 1;
            tempResult.append(temp);
        result = " ".join(tempResult);
        return result;
```

