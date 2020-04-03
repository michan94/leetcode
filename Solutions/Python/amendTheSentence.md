## Problem

You have been given a string s, which is supposed to be a sentence. However, someone forgot to put spaces between the different words, and for some reason they capitalized the first letter of every word. Return the sentence after making the following amendments:

Put a single space between the words.

Convert the uppercase letters to lowercase.

### Example

For s = "CodesignalIsAwesome", the output should be

amendTheSentence(s) = "codesignal is awesome";


For s = "Hello", the output should be

amendTheSentence(s) = "hello".


**First Solution:**
```python
class Solution(object):
    def amendTheSentence(s):
        s = list(s)
        temp = ""
        for i in range(len(s)):
            if i == 0 and s[i] == s[i].upper():
                temp += s[i].lower()
            elif s[i] == s[i].upper():
                temp += " " + s[i].lower()
            else:
                temp += s[i]
        return temp



    print(amendTheSentence("CodesignalIsAwesome"))
```