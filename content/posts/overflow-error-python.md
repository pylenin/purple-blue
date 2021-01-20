---
title: "OverflowError Exception in Python"
description: "How to handle OverflowError Exception in Python?"
date: 2021-01-19T13:25:21+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
tags: ['Built-in exception class']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

An `OverflowError` exception is raised when an [arithmetic operation](https://www.pylenin.com/blogs/python-arithmetic-operators/) exceeds the limits to be represented. This is part of the [ArithmeticError Exception class](https://www.pylenin.com/blogs/arithmetic-error-python/).

##### Example 1

**Code**

```python3
j = 5.0

for i in range(1, 1000):
    j = j**i
    print(j)
```

**Output**

```bash
5.0
25.0
15625.0
5.960464477539062e+16
7.52316384526264e+83
Traceback (most recent call last):
  File "some_file_location", line 4, in <module>
    j = j**i
OverflowError: (34, 'Result too large')
```

As you can see, when you are trying to calculate the exponent of a floating point number, it fails at a certain stage with `OverflowError` exception.
You can handle this error using the `OverflowError` Exception class in Python.

##### Example 2 - Handling `OverflowError` in Python

**Code**

```python3
j = 5.0

try:
    for i in range(1, 1000):
        j = j**i
        print(j)
except OverflowError as e:
    print("Overflow error happened")
    print(f"{e}, {e.__class__}")
```

**Output**

```bash
5.0
25.0
15625.0
5.960464477539062e+16
7.52316384526264e+83
Overflow error happened
(34, 'Result too large'), <class 'OverflowError'>
```

Check out other [Python Built-in Exception classes in Python](https://www.pylenin.com/tags/built-in-exception-class/).

#### Related Articles

1. [Try, Except, Else and Finally in Python](https://www.pylenin.com/blogs/python-try-except-else-finally/)
2. [ZeroDivisionError Exception in Python](https://www.pylenin.com/blogs/zero-division-error-python/)
3. [KeyError Exception in Python](https://www.pylenin.com/blogs/key-error-python/)
4. [ArithmeticError Exception in Python](https://www.pylenin.com/blogs/arithmetic-error-python/)
5. [IndexError Exception in Python](https://www.pylenin.com/blogs/index-error-python/)
6. [LookupError Exception in Python](https://www.pylenin.com/blogs/lookup-error-python/)
7. [StopIteration Exception in Python](https://www.pylenin.com/blogs/stop-iteration-error-python/)
8. [TypeError Exception in Python](https://www.pylenin.com/blogs/type-error-python/)
9. [NameError Exception in Python](https://www.pylenin.com/blogs/name-error-python/)
10. [FileNotFoundError Exception in Python](https://www.pylenin.com/blogs/file-not-found-error-python/)
11. [Catch Multiple Exceptions in Python](https://www.pylenin.com/blogs/catch-multiple-exceptions-python/)