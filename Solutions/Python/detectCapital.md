## Problem

Given a word, you need to judge whether the usage of capitals in it is right or not.

We define the usage of capitals in a word to be right when one of the following cases holds:

All letters in this word are capitals, like "USA".

All letters in this word are not capitals, like "leetcode".

Only the first letter in this word is capital, like "Google".

Otherwise, we define that this word doesn't use capitals in a right way.
 

###Example 1:

Input: "USA"

Output: True
 

### Example 2:

Input: "FlaG"

Output: False



**First Solution:**
```python
class Solution(object):
    def detectCapitalUse(self, word):
        """
        :type word: str
        :rtype: bool
        """
        if len(word) < 2:
            return True
        if len(word) < 3:
            if word[0] != word[0].upper():
                if word[1] == word[1].upper():
                    return False
            return True
            return True
        if word[0] == word[0].upper():
            # First letter of word capitalized
            if word[1] != word[1].upper():
                for s in range(2,len(word)):
                    if word[s] == word[s].upper():
                        return False
                return True
            # All capitalized
            for letter in word:
                if letter != letter.upper():
                    return False
            return True
        for s in range(1,len(word)):
            print(word[s])
            if word[s] == word[s].upper():
                return False
        return True
```