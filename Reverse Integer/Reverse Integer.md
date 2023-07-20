# Reverse Integer
This is a **Medium Level** Leetcode problem.
## Problem Description
Given a signed 32-bit integer x, you need to reverse its digits. If reversing x causes the value to go outside the signed 32-bit integer range [-2^31, 2^31 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

## Python Solution
```py
class Solution(object):
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        s = 1
        if x < 0: s = -1
        x = str(abs(x))
        x = x[::-1]
        x = s * int(x)
        if x < -2**31 or x > 2**31 - 1:
            return 0 
        else:
            return x
```
The given Python solution provides a class Solution with a method reverse that takes in a signed 32-bit integer x. The method reverses the digits of x and checks if the reversed value falls within the signed 32-bit integer range.
### Working
- The given code in could be executed on any standardized python environment or IDE e.g. *VScode, Jupyter Notebook, Leetcode IDE etc*, by typing the following command in the terminal:
```py
python streamlit.py
```
- The method first checks if x is negative (x < 0) and stores the sign in the variable s.
It then takes the absolute value of x using abs(x) to handle negative integers and converts it to a string.
- The string is reversed using slicing (x[::-1]).
- The reversed string is converted back to an integer and multiplied by the sign s to retain the original sign of x.
- The method then checks if the reversed value x falls outside the range [-2^31, 2^31 - 1]. If it does, the method returns 0.
- If the reversed value x is within the range, the method returns x.
## Results
This solution efficiently reverses the digits of the input integer and handles the range restriction of the signed 32-bit integer. This code's memory usage gives a **94.16%** of the Beat score among other solutions and beats **83.49%** of the runtime.

