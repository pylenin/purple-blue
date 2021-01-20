---
title: "StopIteration Exception in Python"
description: "How to handle StopIteration Exception in Python?"
date: 2021-01-19T19:55:23+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
tags: ['Built-in exception class']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

To understand `StopIteration` Exception, you need to understand how **iterators work in Python**.

1. Iterator is an object that holds values which can be iterated upon.
2. It uses the `__next__()` method to move to the next value in the iterator.
3. When the `__next__()` method tries to move to the next value, but there are no new values, a `StopIteration` Exception is raised.

##### Example 1

**Code**

```python3
y = [1, 2, 3]
x = iter(y)
print(x.__next__())
print(x.__next__())
print(x.__next__())
print(x.__next__())
```

**Output**

```bash
1
2
3
Traceback (most recent call last):
  File "some_file_location", line 6, in <module>
    print(x.__next__())
StopIteration
```

You can catch such errors using the `StopIteration` Exception class.

##### Example 2

**Code**

```python3
y = [1, 2, 3]
x = iter(y)
try:
    print(x.__next__())
    print(x.__next__())
    print(x.__next__())
    print(x.__next__())
except StopIteration as e:
    print("StopIteration error handled successfully")
```

**Output**

```bash
1
2
3
StopIteration error handled successfully
```

Check out other [Python Built-in Exception classes in Python](https://www.pylenin.com/tags/built-in-exception-class/).

#### Related Articles

1. [Try, Except, Else and Finally in Python](https://www.pylenin.com/blogs/python-try-except-else-finally/)
2. [ZeroDivisionError Exception in Python](https://www.pylenin.com/blogs/zero-division-error-python/)
3. [OverflowError Exception in Python](https://www.pylenin.com/blogs/overflow-error-python/)
4. [ArithmeticError Exception in Python](https://www.pylenin.com/blogs/arithmetic-error-python/)
5. [KeyError Exception in Python](https://www.pylenin.com/blogs/key-error-python/)
6. [IndexError Exception in Python](https://www.pylenin.com/blogs/index-error-python/)
7. [LookupError Exception in Python](https://www.pylenin.com/blogs/lookup-error-python/)
8. [TypeError Exception in Python](https://www.pylenin.com/blogs/type-error-python/)
9. [NameError Exception in Python](https://www.pylenin.com/blogs/name-error-python/)
10. [FileNotFoundError Exception in Python](https://www.pylenin.com/blogs/file-not-found-error-python/)