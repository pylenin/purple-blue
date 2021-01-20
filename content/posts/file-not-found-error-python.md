---
title: "FileNotFoundError Exception in Python"
description: "How to handle FileNotFoundError Exception in Python?"
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

The `FileNotFoundError` Exception in Python is raised when you are trying to access a file or a directory that doesn't exist.

##### Example 1

**Code/Output**

```python3
x = open("random_file.txt")
>>> FileNotFoundError: [Errno 2] No such file or directory: 'random_file.txt'
```

You can deal with such errors by using the `FileNotFoundError` Exception class.

##### Example 2

**Code**

```python3
try:
    x = open('random.txt')
except FileNotFoundError as e:
    print(f"FileNotFoundError successfully handled\n"
          f"{e}")
```

**Output**

```bash
FileNotFoundError successfully handled
[Errno 2] No such file or directory: 'random.txt'
```

> The above code uses [f-strings](https://www.pylenin.com/blogs/f-strings-python/). Check out that article and other [string formatting techniques](https://www.pylenin.com/blogs/python-string-formatting/).

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
10. [NameError Exception in Python](https://www.pylenin.com/blogs/name-error-python/)
11. [Catch Multiple Exceptions in Python](https://www.pylenin.com/blogs/catch-multiple-exceptions-python/)