---
title: "ZeroDivisionError Exception in Python"
description: "How to handle ZeroDivision Exception in Python?"
date: 2021-01-19T12:14:53+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
tags: ['Built-in exception class']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

A `ZeroDivisionError` is raised when you try to **divide by 0.** This is part of the `ArithmeticError` Exception class.

##### Example 1

**Code/Output**

```python3
# integers
1/0
>>> ZeroDivisionError: division by zero

# floats
5.3/0
>>> ZeroDivisionError: float division by zero

# complex numbers
(1+2j)/0
>>> ZeroDivisionError: complex division by zero
``` 

##### Example 2 - `decimal` library

If you are working with a decimal library and you perform the division operation with a `0`, you get a `DivisionByZero` error.

The `DivisionByZero` eexception is `decimal` libraries own exception type that derives from the `ZeroDivisionError` exception.

**Code**

```python3
from decimal import Decimal

x = Decimal(1)
print(x/0)
``` 

**Output**

```bash
decimal.DivisionByZero: [<class 'decimal.DivisionByZero'>]
```

##### Handling `ZeroDivisionError` in Python

You can handle `ZeroDivisionError` errors by using the same exception class in your [except](https://www.pylenin.com/blogs/python-try-except-else-finally/) block.

**Code**
```python3
# integers
try:
    1/0
except ZeroDivisionError as e:
    print(e)


# floats
try:
    5.3/0
except ZeroDivisionError as e:
    print(e)

# complex numbers
try:
    (1+2j)/0
except ZeroDivisionError as e:
    print(e)
```

**Output**

```bash
division by zero
float division by zero
complex division by zero
```

##### Hierarchy of ZeroDivisionError

The `ZeroDivisionError` inherits from the `ArithmeticError` class, which in turn inherits from the generic `Exception` class.

> * Exception
>    * ArithmeticError
>        * ZeroDivisionError

So you can catch all `ZeroDivisionError` exceptions using the `ArithmeticError` exception class.

**Code**

```python3
# integers
try:
    1/0
except ArithmeticError as e:
    print(e, e.__class__)


# floats
try:
    5.3/0
except ArithmeticError as e:
    print(e, e.__class__)

# complex numbers
try:
    (1+2j)/0
except ArithmeticError as e:
    print(e, e.__class__)
```

**Output**

```bash
division by zero <class 'ZeroDivisionError'>
float division by zero <class 'ZeroDivisionError'>
complex division by zero <class 'ZeroDivisionError'>
```

Check out other [Python Built-in Exception classes in Python](https://www.pylenin.com/tags/built-in-exception-class/).

#### Related Articles

1. [Try, Except, Else and Finally in Python](https://www.pylenin.com/blogs/python-try-except-else-finally/)
2. [KeyError Exception in Python](https://www.pylenin.com/blogs/key-error-python/)
2. [OverflowError Exception in Python](https://www.pylenin.com/blogs/overflow-error-python/)