---
title: "Python String join() Method"
description: "Learn to use join() method on Python strings"
date: 2021-01-15T09:13:43+05:30
draft: false
image: /img/pylenin_logo.png
categories: ['python strings']
tags: ['python string methods']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

##### Python String `join()` method

The `join()` method in Python returns a string in which all the elements of an iterable have been joined by the provided string separator.

**If the iterable contains any non-string values, it raises a `TypeError` exception.**

##### Syntax of `join()` method

```bash
separator.join(iterable)

iterable	Any iterable object where 
            all the values are strings.
```

**List, Tuple, String, Dictionary and Sets - all qualify as iterables for the `join()` method.**

**Code/Output**
##### Example 1

```python3
# list
x = ["Pylenin", "loves", "Python"]
sep = " "
print(sep.join(x))
>>> Pylenin loves Python

# dictionary
x = {"name": "Pylenin",
     "language":"Python"}
sep = "-"
print(sep.join(x.values()))
>>> Pylenin-Python

# dictionary
x = {"name": "Pylenin",
     "language":"Python"}
sep = " loves "
print(sep.join(x.values()))
>>> Pylenin loves Python

# tuple
x = ("p", "y", "l", "e", "n", "i", "n")
sep =""
print(sep.join(x))
>>> pylenin

# sets
x = {"1", "2", "3", "3"}
sep ="-"
print(sep.join(x))
>>> 1-3-2
```

**Can you explain why the `join()` method for sets, doesn't return both the `3`s in the final string? Comment below.**

##### Example 2 - `TypeError` Exception with `join()` method

If any of the elements of the iterable are not string, Python will return a `TypeError` exception.

**Code/Output**

```python3
x = ["Pylenin", "eats", 12, "apples"]
sep = " "
print(sep.join(x))
>>> TypeError: sequence item 2: expected str instance, int found
```

You can fix it by using list comprehension and converting elements to a string first hand.

**Code/Output**

```python3
x = ["Pylenin", "eats", 12, "apples"]
sep = " "
print(sep.join([str(y) for y in x]))
>>> Pylenin eats 12 apples
```

Check out other [commonly used Python string methods](https://www.pylenin.com/blogs/common-python-string-methods).

#### Related Articles

1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
3. [How to replace characters in a string in Python?](https://www.pylenin.com/blogs/replace-string-characters-python/)
4. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
5. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
6. [Check if a Substring is Present in a Given String in Python](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
7. [Escape sequences in Python String](https://www.pylenin.com/blogs/escape-sequences-python-string/)
8. [Python String Formatting - The Definitive Guide](https://www.pylenin.com/blogs/python-string-formatting/)
