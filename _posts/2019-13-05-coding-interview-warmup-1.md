---
layout: post
title:  "Coding Interview: Warm Up - 01"
date:   2018-01-26
comments: true
---

# Problem

### FizzBuzz

[Link to original Problem on LeetCode](https://leetcode.com/problems/fizz-buzz/)
Write a program that outputs the string representation of numbers from 1 to n.

But for multiples of three it should output “Fizz” instead of the number and for the multiples of five output “Buzz”. For numbers which are multiples of both three and five output “FizzBuzz”.

> Example:
>
> n = 15,
>
> Return:
> [
>     "1",
>     "2",
>     "Fizz",
>     "4",
>     "Buzz",
>     "Fizz",
>     "7",
>     "8",
>     "Fizz",
>     "Buzz",
>     "11",
>     "Fizz",
>     "13",
>     "14",
>     "FizzBuzz"
> ]

**My Solution:**
```python
class Solution(object):
    def fizzBuzz(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        return ['Fizz' * (not i % 3) + 'Buzz' * (not i % 5) or str(i) for i in range(1, n + 1)]
```

**Explanation**

In python if you multiply any string to integer you will get the same string repeated the same number of the you multiplied it.
```python
>>>'Fizz' * 3
'FizzFizzFizz'
```

Now, in arithmetic, python treats booleans as integers. **True** is treated as *1* and **False** is treated as *0*.

In the code ```not i % 3``` will return a boolean which then can be multipled with **Fizz**. Depending on whether the number is divisible by 3 or not we will get the output. Same goes for **Buzz**. If the number is divisible by both 3 and 5 then we are using string concatenation to get **FizzBuzz**.

Empty string are considered False. That's why when we are using **or** in between to make sure if the number is not divisible by either 3 or 5 then use the string typecast version of the number.

We have use string comprehension to do all this in one line.
