---
title: "LookupError Exception in Python"
description: "How to handle LookupError Exception in Python?"
date: 2021-01-19T19:31:33+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
tags: ['Built-in exception class']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

The `LookupError` exception in Python forms the base class for all exceptions that are raised when an index or a key is not found for a sequence or dictionary respectively.

```bash
Exception
-> LookupError
--> IndexError
--> KeyError
```

This means, you can use `LookupError` exception class to handle both `IndexError` and `KeyError` exception classes.

##### Example 1 - Handling `IndexError` exception

**Code/Output**

```python3
# lists
x = [1, 2, 3, 4]
try:
    print(x[10])
except LookupError as e:
    print(f"{e}, {e.__class__}")

>>> list index out of range, <class 'IndexError'>

# strings
x = "Pylenin"
try:
    print(x[10])
except LookupError as e:
    print(f"{e}, {e.__class__}")

>>> string index out of range, <class 'IndexError'>    
    
# tuples
x = (1, 2, 3, 4)
try:
    print(x[10])
except LookupError as e:
    print(f"{e}, {e.__class__}")

>>> tuple index out of range, <class 'IndexError'>
```

As you can see, it is possible to catch `IndexError` exceptions using the `LookupError` exception class. By using `e.__class__` method also helps you to identify the type of `LookupError`. In the above example, it is an `IndexError`.

##### Example 2 - Handling `KeyError` exception

**Code**

```python3
pylenin_info = {'name': 'Lenin Mishra',
                'age': 28,
                'language': 'Python'}
user_input = input('What do you want to learn about Pylenin==> ')

try:
    print(f'{user_input} is {pylenin_info[user_input]}')
except LookupError as e:
    print(f'{e}, {e.__class__}')
```

**Output**

```bash
What do you want to learn about Pylenin==> wife
'wife', <class 'KeyError'>
```

Check out other [Python Built-in Exception classes in Python](https://www.pylenin.com/tags/built-in-exception-class/).

#### Related Articles

1. [Try, Except, Else and Finally in Python](https://www.pylenin.com/blogs/python-try-except-else-finally/)
2. [ZeroDivisionError Exception in Python](https://www.pylenin.com/blogs/zero-division-error-python/)
3. [OverflowError Exception in Python](https://www.pylenin.com/blogs/overflow-error-python/)
4. [ArithmeticError Exception in Python](https://www.pylenin.com/blogs/arithmetic-error-python/)
5. [KeyError Exception in Python](https://www.pylenin.com/blogs/key-error-python/)
6. [IndexError Exception in Python](https://www.pylenin.com/blogs/index-error-python/)
7. [StopIteration Exception in Python](https://www.pylenin.com/blogs/stop-iteration-error-python/)
8. [TypeError Exception in Python](https://www.pylenin.com/blogs/type-error-python/)
9. [NameError Exception in Python](https://www.pylenin.com/blogs/name-error-python/)
10. [FileNotFoundError Exception in Python](https://www.pylenin.com/blogs/file-not-found-error-python/)