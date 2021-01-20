---
title: "IndexError Exception in Python"
description: "How to handle IndexError Exception in Python?"
date: 2021-01-19T18:44:04+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
tags: ['Built-in exception class']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

The `IndexError` exception in Python means that you are trying to access an index that doesn't exist. For example you are trying to access the 5th index of a list, but there are only 4 elements present. It is part of the [LookupError Exception class](https://www.pylenin.com/blogs/lookup-error-python). 

This error can happen with any object that is indexable, like - **Lists, Tuples, Strings etc.**

##### Example 1

**Code**

```python3
x = [1, 2, 3, 4]

print(x[5])
```

**Output**

```bash
Traceback (most recent call last):
  File "some_file_location", line 3, in <module>
    print(x[5])
IndexError: list index out of range
```

You can handle the above exception using the `IndexError` exception class.

##### Example 2

**Code/Output**

```python3
# lists
x = [1, 2, 3, 4]
try:
    print(x[10])
except IndexError as e:
    print(f"{e}")
    
>>> list index out of range
    
# strings
x = "Pylenin"
try:
    print(x[10])
except IndexError as e:
    print(f"{e}")

>>> string index out of range

# tuples
x = (1, 2, 3, 4)
try:
    print(x[10])
except IndexError as e:
    print(f"{e}")

>>> tuple index out of range
```

Use the `IndexError` Exception class, when you are working with indexable objects like strings, lists and Tuples.

Check out other [Python Built-in Exception classes in Python](https://www.pylenin.com/tags/built-in-exception-class/).

#### Related Articles

1. [Try, Except, Else and Finally in Python](https://www.pylenin.com/blogs/python-try-except-else-finally/)
2. [ZeroDivisionError Exception in Python](https://www.pylenin.com/blogs/zero-division-error-python/)
3. [OverflowError Exception in Python](https://www.pylenin.com/blogs/overflow-error-python/)
4. [ArithmeticError Exception in Python](https://www.pylenin.com/blogs/arithmetic-error-python/)
5. [KeyError Exception in Python](https://www.pylenin.com/blogs/key-error-python/)
6. [LookupError Exception in Python](https://www.pylenin.com/blogs/lookup-error-python/)
7. [StopIteration Exception in Python](https://www.pylenin.com/blogs/stop-iteration-error-python/)
8. [TypeError Exception in Python](https://www.pylenin.com/blogs/type-error-python/)