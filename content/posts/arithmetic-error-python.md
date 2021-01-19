---
title: "ArithmeticError Exception in Python"
description: "How to handle ArithmeticError Exception in Python?"
date: 2021-01-19T18:28:23+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
tags: ['Built-in exception class']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

The `ArithmeticError` Exception is the base class for all errors associated with [arithmetic operation](https://www.pylenin.com/blogs/python-arithmetic-operators/).

```bash
Exception
-> ArithmeticError
--> ZeroDivisionError
--> OverflowError
--> FloatingPointError
```

##### Example 1 - Handling `ZeroDivisionError`

**Code**

```python3
try:
    1/0
except ArithmeticError as e:
    print(f"{e}, {e.__class__}")
```

**Output**

```bash
division by zero, <class 'ZeroDivisionError'>
```

As you can see, the `ArithmeticError` exception class is able to handle `ZeroDivisionError` exception. The `e.__class__` method tells you that it was a `ZeroDivisionError`.

##### Example 2 - Handling `OverflowError`

**Code**

```python3
j = 5.0

try:
    for i in range(1, 1000):
        j = j**i
except ArithmeticError as e:
    print(f"{e}, {e.__class__}")
```

**Output**

```bash
(34, 'Result too large'), <class 'OverflowError'>
```

As you can see, by using the `ArithmeticError` exception class, you can handle both `ZeroDivisionError` and `OverflowError` exceptions.

Use this exception class, anytime you are unsure of any arithmetic operations and the errors that it might result in.

Check out other [Python Built-in Exception classes in Python](https://www.pylenin.com/tags/built-in-exception-class/).

#### Related Articles

1. [Try, Except, Else and Finally in Python](https://www.pylenin.com/blogs/python-try-except-else-finally/)
2. [ZeroDivisionError Exception in Python](https://www.pylenin.com/blogs/zero-division-error-python/)
3. [OverflowError Exception in Python](https://www.pylenin.com/blogs/overflow-error-python/)   
4. [KeyError Exception in Python](https://www.pylenin.com/blogs/key-error-python/)