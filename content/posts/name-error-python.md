---
title: "NameError Exception in Python"
description: "How to handle NameError Exception in Python?"
date: 2021-01-20T06:53:45+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
tags: ['Built-in exception class']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

The `NameError` Exception in Python is raised when the object being accessed is not defined in the local or global scope of your python program.

A few examples of `NameError` Exception in Python:-

1. Trying to access a variable that doesn't exist
2. Trying to access a variable in the global scope but it is defined in the local scope.

**To learn more about local and global scope of variables, check out the video below.**

[![](https://img.youtube.com/vi/Dnm2IWh_kxE/0.jpg)](https://youtu.be/Dnm2IWh_kxE "Variable Scope and Namespace in Python")

You can handle such errors using the `NameError` Exception class.

##### Example 1 - Accessing a variable that doesn't exist

**Code**

```python3
try:
    print(name)
except NameError as e:
    print(e)
```

**Output**

```bash
name 'name' is not defined
```

##### Example 2 - Accessing variables not present in global scope

**Code**

```python3
def random_func():
    name = "Pylenin"

try:
    print(name)
except NameError as e:
    print(e)
```

**Output**

```bash
name 'name' is not defined
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
9. [StopIteration Exception in Python](https://www.pylenin.com/blogs/stop-iteration-error-python/)