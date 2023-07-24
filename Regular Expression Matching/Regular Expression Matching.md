# Regular Expression Matching

## Problem Description

Given an input string `s` and a pattern `p`, implement regular expression matching with support for '.' and '*' where:

- '.' matches any single character.
- '*' matches zero or more of the preceding element.

The matching should cover the entire input string (not partial).

### Example:
Input:
```
s = "mississippi", p = "mis*is*p*."
```

Output:
```
False
```

## Python Solution

```python
import re

class Solution(object):
    def isMatch(self, s, p):
        """
        :type s: str
        :type p: str
        :rtype: bool
        """
        try:
            return s == re.findall(p, s)[0]
        except:
            return False
```

The given Python solution provides a class `Solution` with a method `isMatch` that takes two strings `s` and `p` as input. The method implements regular expression matching with support for '.' (matches any single character) and '*' (matches zero or more of the preceding element) and returns True if the entire input string `s` matches the pattern `p`, otherwise returns False.

### Working
- The given code in could be executed on any standardized python environment or IDE e.g. *VScode, Jupyter Notebook, Leetcode IDE etc*.
- The method uses Python's `re.findall()` function from the `re` module to find all occurrences of the pattern `p` in the string `s`.
- It then checks if the first occurrence returned by `re.findall()` is equal to the input string `s`. If it is, then the method returns True; otherwise, it returns False.
- In case there is an exception (e.g., if there are no matches), the method also returns False.

## Results
Please note that this solution might work for some cases, it may not be an efficient or optimal solution for all scenarios. Regular expression matching can be a complex problem, and other algorithms such as backtracking or dynamic programming are often used to achieve better performance. However, This code's memory usage gives a **93.45%** of the Beat score among other solutions.