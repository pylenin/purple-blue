---
title: "How to replace characters in a string in Python?"
description: "Learn if you can replace characters in strings in Python"
date: 2021-01-09T23:44:41+05:30
draft: false
image: /img/pylenin_logo.png
tags: ['python strings']
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

> If you prefer to watch Youtube videos over reading blogs, check out our [video on Python strings here](https://youtu.be/MXdNMo_f95I). 

#### Can we replace characters in a string in Python?

In Python, strings are **immutable**.

This means, elements of a string cannot be changed or replaced once they have been assigned.

**Code**
```python3
x = "Pylenin"
x[0] = "L"
```

**Output**
```bash
Traceback (most recent call last):
  File "file_location", line 2, in <module>
    x[0] = "L"
TypeError: 'str' object does not support item assignment
```

**However, we can certainly create a copy of our string with our necessary replacements.**

#### Method 1 - Python string replace() method

The `replace()` method replaces a specified character/phrase with another.

**Syntax of replace()**
```bash
string.replace(oldstring, newstring, count)

oldstring - The string to replace(required)
newstring - The string to replace with(required)
count - A number specifying how many occurrences 
        of the old value you want to replace. 
        Default is all occurrences (optional)
```

##### Example 1

Replace all occurences of the word `Pylenin`.

**Code**

```python3
txt = "I like Pylenin"

x = txt.replace("Pylenin", "Python")

print(x)
```

**Output**

```python3
I like Python
```

##### Example 2

Replace the first two occurrence of the word `Python`.

**Code**

```python3
txt = "Python is the best. " \
      "I love Python. " \
      "I enjoy Python"

x = txt.replace("Python", "Pylenin", 2)

print(x)
```

**Output**

```python3
Pylenin is the best. I love Pylenin. I enjoy Python
```

#### Method 2 - Python list() method

Another solution would be to convert a string to a python list and then make necessary changes. 
Unlike Python strings, **Python lists are mutable**.

**Code**

```python3
old_str = "foofoo"

str_list = list(old_str)
str_list[0] = 'd'
new_string = "".join(str_list)

print(new_string)
```

**Output**

```python3
doofoo
```

#### Related Articles

1. [How to create a string in Python?](https://www.pylenin.com/blogs/create-string-python/)
2. [How to access characters in a Python string?](https://www.pylenin.com/blogs/access-characters-in-string/)
3. [How to concatenate strings in Python?](https://www.pylenin.com/blogs/concatenate-strings-in-python/)
4. [How to iterate through a string in Python?](https://www.pylenin.com/blogs/iterating-through-python-string/)
5. [Check if a Substring is Present in a Given String](https://www.pylenin.com/blogs/check-substring-in-a-string-python/)
