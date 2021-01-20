---
title: "TypeError Exception in Python"
description: "How to handle TypeError Exception in Python?"
date: 2021-01-20T05:16:57+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python exceptions']
tags: ['Built-in exception class']
categories_weight: 2
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> This is the part of the 9th day in the Python 30 series. [Check out the series here.](https://www.youtube.com/playlist?list=PLqEbL1vopgvuI-3wzwHqftEkH3AILozS5)

The `TypeError` Exception in Python is raised when you try to apply any operation or function call to an inappropriate type of object.

For example - 
1. Trying to concatentate a list and a number
2. calling a variable as a function
3. Passing an argument to a function of the wrong type etc.

##### Example 1

**Code/Output**

```python3
# concatenating list with an integer
x = [1, 2, 3]
y = 2

print(x+y)
>>> TypeError: can only concatenate list (not "int") to list

# passing an unsupported index
x = [1, 2, 3]
print(x[0.5])
>>> TypeError: list indices must be integers or slices, not float

# calling a variable as a function
x = "Pylenin"
x()
>>> TypeError: 'str' object is not callable

# Passing wrong argument
def addition(x, y):
    return x+y

print(addition(10, [1, 2]))
>>> TypeError: unsupported operand type(s) for +: 'int' and 'list'
```

You can handle these errors using the `TypeError` Exception class.

##### Example 2

**Code**

```python3
# concatenating list with an integer
x = [1, 2, 3]
y = 2
try:
    print(x+y)
except TypeError as e:
    print(f"TypeError handled."
          f"Error reason - {e}")

# passing an unsupported index
x = [1, 2, 3]
try:
    print(x[0.5])
except TypeError as e:
    print(f"TypeError handled."
          f"Error reason - {e}")


# calling a variable as a function
x = "Pylenin"
try:
    x()
except TypeError as e:
    print(f"TypeError handled."
          f"Error reason - {e}")


# Passing wrong argument
def addition(x, y):
    return x+y

try:
    print(addition(10, [1, 2]))
except TypeError as e:
    print(f"TypeError handled."
          f"Error reason - {e}")
```

**Output**

```bash
TypeError handled.Error reason - can only concatenate list (not "int") to list
TypeError handled.Error reason - list indices must be integers or slices, not float
TypeError handled.Error reason - 'str' object is not callable
TypeError handled.Error reason - unsupported operand type(s) for +: 'int' and 'list'
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
8. [StopIteration Exception in Python](https://www.pylenin.com/blogs/stop-iteration-error-python/)
9. [NameError Exception in Python](https://www.pylenin.com/blogs/name-error-python/)
