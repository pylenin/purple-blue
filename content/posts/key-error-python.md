---
title: "KeyError Exception in Python"
description: "How to handle KeyError Exception in Python?"
date: 2021-01-19T13:02:42+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
tags: ['Built-in exception class']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

A `KeyError` exception is raised when you are trying to access an invalid key in a [python dictionary](https://www.pylenin.com/blogs/python-dictionary/). It tells you that there was an issue retrieving the key you were trying to access. It is part of the [LookupError Exception class](https://www.pylenin.com/blogs/lookup-error-python). 

##### Example 1

**Code**

```python3
pylenin_info = {'name': 'Lenin Mishra',
                'age': 28,
                'language': 'Python'}
user_input = input('What do you want to learn about Pylenin==> ')

if user_input:
    print(f'{user_input} is {pylenin_info[user_input]}')
else:
    print(f'{user_input} is unknown')
```

> The above code uses [input()](https://www.pylenin.com/blogs/how-input-works-python/) function and [f-strings](https://www.pylenin.com/blogs/f-strings-python/). Check them out.

**Output**

```bash
What do you want to learn about Pylenin==> wife
Traceback (most recent call last):
  File "some_file_location", line 7, in <module>
    print(f'{user_input} is {pylenin_info[user_input]}')
KeyError: 'wife'
```

As you can see, when you are trying to access an unavailable key, Python throws you a `KeyError`.
You can handle this error using the `KeyError` Exception class in Python.

##### Example 2 - Handling `KeyError` in Python

**Code**

```python3
pylenin_info = {'name': 'Lenin Mishra',
                'age': 28,
                'language': 'Python'}
user_input = input('What do you want to learn about Pylenin==> ')

try:
    print(f'{user_input} is {pylenin_info[user_input]}')
except KeyError as e:
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
5. [IndexError Exception in Python](https://www.pylenin.com/blogs/index-error-python/)
6. [LookupError Exception in Python](https://www.pylenin.com/blogs/lookup-error-python/)
7. [StopIteration Exception in Python](https://www.pylenin.com/blogs/stop-iteration-error-python/)
8. [TypeError Exception in Python](https://www.pylenin.com/blogs/type-error-python/)
9. [NameError Exception in Python](https://www.pylenin.com/blogs/name-error-python/)