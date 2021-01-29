---
title: "Python Booleans"
description: "Learn about booleans in Python 3 and how to use them."
date: 2021-01-29T09:06:36+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['Getting Started with Python']
categories_weight: 7
---
<div class="sharethis-inline-follow-buttons"></div>

There are 2 types of Booleans - `True` and `False`.

When you evaluate any expression or compare values in Python, Python returns `True` or `False`.

**Example**

```python3
print(100 > 9)
>>> True

print(-1 < -10)
>>> False

print(100 == 100)
>>> True
```

#### `bool()` function in Python

The `bool()` function in Python lets you to evaluate any value, and returns `True` or `False`.

Any object in Python that is not empty, is evaluated as `True`.

**Example**

```python3
# Pass an integer other than 0
print(bool(1))
>>> True

# Pass a string
print(bool("Pylenin"))
>>> True

# Pass a list
print(bool([1, 2, 3]))
>>> True

# Pass a dictionary
my_dict = {"name":"Pylenin"}
print(bool(my_dict))
>>> True

# Pass a tuple
print(bool((1, 2, 3)))
>>> True

# Pass a set
print(bool({1, 2, 3}))
>>> True
```

Each of the above statements are evaluated as **True**.

**Empty objects and 0** are always evaluated as False.

**Example**

```python3
# Pass an integer other than 0
print(bool(0))
>>> False

# Pass a string
print(bool(""))
>>> False

# Pass a list
print(bool([]))
>>> False

# Pass a dictionary
my_dict = {}
print(bool(my_dict))
>>> False

# Pass a tuple
print(bool(tuple())) # You can't define an empty tuple with parenthesis
>>> False

# Pass a set
print(bool(set()))
>>> False
```

