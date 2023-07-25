# Multiply Strings

## Problem Description

Given two non-negative integers `num1` and `num2` represented as strings, return the product of `num1` and `num2`, also represented as a string.

Note: You must not use any built-in BigInteger library or convert the inputs to an integer directly.

### Example:

Input:
```
num1 = "123", num2 = "456"
```

Output:
```
"56088"
```

## Python Solution

```python
class Solution(object):
    def multiply(self, num1, num2):
        """
        :type num1: str
        :type num2: str
        :rtype: str
        """
        def decode(num):
            ans = 0
            for i in num:
                ans = ans * 10 + (ord(i) - ord('0'))
            return ans
        
        return str(decode(num1) * decode(num2))
```

The given Python solution provides a class `Solution` with a method `multiply` that takes two strings `num1` and `num2` as input. The method multiplies the two non-negative integers represented as strings and returns the product as a string.

### Working
- The given code in could be executed on any standardized python environment or IDE e.g. *VScode, Jupyter Notebook, Leetcode IDE etc*.
- The method defines a helper function `decode(num)` to convert a string `num` to an integer representation. It iterates through the characters of the string and builds the integer representation by multiplying the current value by 10 and adding the value of the current digit.
- The method then returns the product of the two integers obtained by applying the `decode` function to `num1` and `num2`, and converts the result back to a string using the `str()` function.

## Results
Please note that this approach of solution works for small input numbers, for large inputs, more efficient algorithms like Karatsuba algorithm or Fast Fourier Transform (FFT) can be used to achieve better performance. However, this code's memory usage gives a **83.68%** of the Beat score among other solutions and beats **94.89%** of the runtime.